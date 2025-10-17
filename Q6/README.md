# Question 6: Multi-Site Network with VLANs, Router-on-a-Stick, and RIP

## Overview

Design and implement a multi-site network with inter-VLAN routing using Router-on-a-Stick configuration and RIP routing protocol.

**Tool:** Cisco Packet Tracer

---

## Network Topology

Please refer to the **diagram.jpg** file for the network topology you need to implement.

![Network Diagram](diagram.jpg)

---

## Requirements

### 1. VLAN Configuration

**Each site must have:**

- **VLAN 10** (e.g., Sales/User network)
- **VLAN 20** (e.g., Management network)

**Requirements:**

- Configure VLANs on switches at each site
- Assign appropriate ports to each VLAN
- Configure trunk ports between switches and routers
- Ensure proper VLAN naming and labeling

### 2. Router-on-a-Stick (Inter-VLAN Routing)

**Implementation at each site:**

- Configure **Router-on-a-Stick** on the site router
- Create sub-interfaces for each VLAN
- Enable 802.1Q encapsulation on sub-interfaces
- Assign IP addresses as gateway for each VLAN

**Example Configuration:**

```cisco
interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
```

### 3. RIP Routing Protocol

**Configure RIP between routers:**

- Use **RIP (Routing Information Protocol)** for routing between site routers
- Enable RIP on all routers
- Advertise all networks
- Ensure all sites can communicate with each other

**Example Configuration:**

```cisco
router rip
 version 2
 network 192.168.10.0
 network 192.168.20.0
 network 10.0.0.0
 no auto-summary
```

### 4. Default Route to ISP

**ISP Connectivity:**

- Configure a **default route** pointing to the ISP
- This allows all internal networks to access the Internet/ISP
- Propagate the default route through RIP if needed

**Example Configuration:**

```cisco
ip route 0.0.0.0 0.0.0.0 [ISP-next-hop-IP]

! Optionally propagate default route in RIP
router rip
 default-information originate
```

### 5. Internet Access Requirement

**Critical Requirement:**

- **All devices** in all VLANs at all sites must have access to the **Internet (ISP)**
- Test connectivity from:
  - VLAN 10 devices to ISP
  - VLAN 20 devices to ISP
  - All sites to ISP

### 6. Device Configuration

- **Label all devices** appropriately (Site1-Router, Site2-Router, Site1-Switch, etc.)
- **Change hostnames** on all routers and switches
- **VLAN naming**: Give descriptive names to VLANs
- Use clear and consistent naming conventions

---

## Network Design Guidelines

### IP Addressing Scheme

**Site 1:**

- VLAN 10: `192.168.10.0/24` (Gateway: `192.168.10.1`)
- VLAN 20: `192.168.20.0/24` (Gateway: `192.168.20.1`)

**Site 2:**

- VLAN 10: `192.168.30.0/24` (Gateway: `192.168.30.1`)
- VLAN 20: `192.168.40.0/24` (Gateway: `192.168.40.1`)

**Inter-site Links:**

- Use appropriate point-to-point addressing (e.g., `10.0.x.0/30`)

**ISP Link:**

- Use public or simulated public IP addressing

### Trunk Configuration

**On switches:**

```cisco
interface GigabitEthernet0/1
 switchport mode trunk
 switchport trunk allowed vlan 10,20
```

---

## Key Concepts

### Router-on-a-Stick

- Single physical router interface
- Multiple logical sub-interfaces (one per VLAN)
- 802.1Q VLAN tagging
- Enables inter-VLAN routing without multiple physical interfaces

### RIP (Routing Information Protocol)

- Distance vector routing protocol
- Uses hop count as metric
- Maximum 15 hops
- Version 2 supports VLSM and CIDR

---

## Deliverables

1. **Cisco Packet Tracer file (.pkt)** with complete network implementation
2. **Screenshots** showing:
   - Full network topology matching diagram.jpg
   - VLAN configurations (`show vlan brief`)
   - Router-on-a-Stick sub-interface configurations
   - RIP routing table (`show ip route`)
   - Successful ping from VLAN 10 device to ISP
   - Successful ping from VLAN 20 device to ISP
   - Ping between different sites
3. **Configuration files** or documentation including:
   - Switch VLAN configurations
   - Router sub-interface configurations
   - RIP configuration
   - Default route configuration

---

## Testing Checklist

- [ ] VLANs 10 and 20 created on all site switches
- [ ] Trunk links configured between switches and routers
- [ ] Router-on-a-Stick configured at each site
- [ ] Devices in VLAN 10 can communicate within their VLAN
- [ ] Devices in VLAN 20 can communicate within their VLAN
- [ ] Devices in VLAN 10 can reach VLAN 20 (inter-VLAN routing works)
- [ ] RIP configured and routes visible in routing tables
- [ ] Sites can communicate with each other
- [ ] Default route to ISP configured
- [ ] All devices can ping ISP
- [ ] All devices properly labeled and named

---

## Submission Guidelines

- Submit your completed .pkt file
- Include all required screenshots

---

## Tips for Success

- Start with VLAN configuration on switches
- Configure trunk links before Router-on-a-Stick
- Ensure sub-interface numbers match VLAN IDs (best practice)
- Test inter-VLAN routing before configuring RIP
- Use RIP version 2 and disable auto-summary
- Verify RIP routes with `show ip route` and `show ip protocols`
- Test connectivity incrementally (intra-VLAN → inter-VLAN → inter-site → ISP)
- Use `no shutdown` on main interface and all sub-interfaces
