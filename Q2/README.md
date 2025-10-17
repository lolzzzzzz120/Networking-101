# Question 2: Two-Floor Building Network Design with VLANs

## Scenario

You have a two-floor building and need to design a network infrastructure with the following requirements.

**Tool**: Use **Cisco Packet Tracer** to design and implement this network.

## Requirements

### Network Structure

- Each floor must have **2 separate networks**:
  - **VLAN 10**: Public network
  - **VLAN 20**: Management network

### Switches

- Each floor requires **1 Cisco 2960 switch**
- Both floor switches must connect to **1 central Cisco 2960 switch**

### Access Points (APs)

- Each floor needs **2 Access Points**:
  - 1 AP for the **Management** network
  - 1 AP for the **Public** network

### Connected Devices

- Each network on each floor must have at least:
  - **1 wireless device**
  - **1 wired device**

### DHCP Configuration

- The **Public network** must have a DHCP server
- DHCP IP range: **10.17.0.0/22**

### Documentation

- Please ensure proper **naming and labeling** of:
  - All devices
  - All VLANs

## Deliverables

- **Cisco Packet Tracer file (.pkt)** with complete network topology
- Device configurations (switches, APs, DHCP server)
- VLAN setup and trunk configurations
- DHCP configuration
