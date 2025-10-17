# Question 4: Dual ISP Redundancy with Default Static Routes

## Overview

This assignment builds upon **Question 3**. You will design a network with **dual ISP connections** to ensure high availability and redundancy.

**Tool:** Cisco Packet Tracer

---

## Scenario

Connect your building network to **two ISPs (Internet Service Providers)**. Both ISPs should connect to a **data center-like network** that hosts a **web server**. The network must maintain connectivity to the web server even if one ISP fails.

---

## Requirements

### 1. Network Topology

**Building Network:**

- Use your existing network from **Question 3** (or create a simple client network if you didn't complete Q3)
- Connect the building to **two ISPs** for redundancy

**ISP Connections:**

- Configure **ISP 1** and **ISP 2**
- Both ISPs must connect to a central **data center network**

**Data Center:**

- Set up a data center network
- Include a **web server** with a working web page

### 2. Router Configuration

- You will need **4 routers** in addition to any switches from previous assignments:
  - Router(s) for the building network
  - Router for ISP 1
  - Router for ISP 2
  - Router for the data center network

### 3. Static Routing

- Configure **default static routes** where needed
- Ensure proper routing between:
  - Building → ISP 1 → Data Center
  - Building → ISP 2 → Data Center
- Routes should provide redundancy (failover capability)

### 4. Redundancy and Failover

**Critical Requirement:**

- If **either ISP fails**, the building must **still maintain access** to the web server
- Test failover by:
  - Disabling ISP 1 connection and verifying connectivity through ISP 2
  - Disabling ISP 2 connection and verifying connectivity through ISP 1

### 5. Web Server Configuration

- Set up a functional web server in the data center
- Configure a simple web page
- Ensure the web server is accessible from the building network through both ISPs

### 6. Device Configuration

- **Label all devices** clearly (Building Routers, ISP1, ISP2, Data Center Router, Web Server)
- **Change hostnames** on all routers
- Use descriptive names for easy identification

---

## Network Design Guidelines

### IP Addressing

- Use appropriate IP addressing schemes for:
  - Building internal network
  - Building ↔ ISP 1 link
  - Building ↔ ISP 2 link
  - ISP ↔ Data Center links
  - Data Center network

### Routing Configuration

- Primary path: Choose one ISP as primary (better metric)
- Backup path: Configure second ISP with higher metric
- Use default static routes: `ip route 0.0.0.0 0.0.0.0 [next-hop] [metric]`

---

## Note for Students

**If you didn't complete Question 3:**

- You can start fresh with a simple client setup
- Use just **one PC or laptop** as the building client
- Focus on the ISP redundancy and routing aspects

---

## Deliverables

1. **Cisco Packet Tracer file (.pkt)** with complete network implementation
2. **Screenshots** showing:
   - Full network topology
   - Successful web access through ISP 1
   - Successful web access through ISP 2
   - Failover test (one ISP disabled, connectivity maintained)
   - Router configurations (static routes)
   - Web server configuration
3. **Brief documentation** explaining:
   - Your IP addressing scheme
   - How redundancy is achieved
   - Default static route configuration

---

## Testing Checklist

- [ ] Web server is accessible from building network
- [ ] Access works through ISP 1
- [ ] Access works through ISP 2
- [ ] Disable ISP 1 → connectivity maintained through ISP 2
- [ ] Disable ISP 2 → connectivity maintained through ISP 1
- [ ] All routers have proper hostnames and labels
- [ ] Default static routes are properly configured

---

## Tips

- Use `show ip route` to verify routing tables
- Use `ping` to test connectivity
- Use `traceroute` to see which ISP path is being used
- Test failover by shutting down interfaces: `shutdown` command
- Configure floating static routes with different administrative distances for automatic failover
