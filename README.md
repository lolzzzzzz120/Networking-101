# Networking 101

A comprehensive networking course covering fundamental concepts, practical implementations, and advanced topics.

## 📚 Course Overview

This repository contains assignments and projects designed to teach networking fundamentals, from basic DNS concepts to advanced network programming.

---

## 📋 Assignments

### [Question 1: DNS and SSH Fundamentals](Q1/)

**Topics Covered:**

- DNS record types
- Domain registration process
- DNS lookup process
- DNS aging and scavenging
- Passwordless SSH authentication
- DNS TTL (Time To Live)

**Type:** Theoretical questions

---

### [Question 2: Two-Floor Building Network Design with VLANs](Q2/)

**Topics Covered:**

- VLAN configuration (VLAN 10 - Public, VLAN 20 - Management)
- Cisco 2960 switch configuration
- Access Point (AP) setup
- DHCP configuration
- Network topology design

**Tool:** Cisco Packet Tracer  
**Deliverable:** `.pkt` file with configurations

---

### [Question 3: Static Routing Configuration](Q3/)

**Topics Covered:**

- Static routing implementation
- Route metrics and path selection
- Network topology design
- Router configuration
- Connectivity testing

**Tool:** Cisco Packet Tracer  
**Deliverable:** `.pkt` file with static routes  
**Note:** Includes network diagram reference

---

### [Question 4: Dual ISP Redundancy with Default Static Routes](Q4/)

**Topics Covered:**

- ISP redundancy and failover
- Default static routes
- Data center network design
- Web server configuration
- High availability concepts

**Tool:** Cisco Packet Tracer  
**Deliverable:** `.pkt` file demonstrating redundancy  
**Prerequisite:** Builds upon Q3

---

### [Question 5: Network Address Translation (NAT) Configuration](Q5/)

**Topics Covered:**

- Static NAT
- Dynamic NAT
- PAT (Port Address Translation)
- NAT vs no NAT comparison
- Practical lab implementation

**Tool:** Cisco Packet Tracer  
**Lab Source:** Keith Barker NAT Lab  
**Deliverable:** Completed lab + theoretical answers

---

### [Question 6: Multi-Site Network with VLANs, Router-on-a-Stick, and RIP](Q6/)

**Topics Covered:**

- Router-on-a-Stick configuration
- Inter-VLAN routing
- RIP routing protocol
- 802.1Q encapsulation
- Multi-site connectivity
- Default route to ISP

**Tool:** Cisco Packet Tracer  
**Deliverable:** `.pkt` file with complete multi-site setup  
**Note:** Includes network diagram reference

---

### [Final Project: Network Programming - Malware & Antivirus Simulation](Q7-Final%20Project/)

**Topics Covered:**

- Socket programming (TCP/UDP)
- Remote Access Tool (RAT) simulation
- Packet capture with libpcap
- Network traffic analysis
- Intrusion Detection System (IDS)
- Cross-platform development (Linux & Windows)

**Languages:** C/C++ (required), any language for attacker binary  
**Components:**

1. Attacker binary (C2 Server)
2. Victim binary (Agent)
3. Antivirus/IDS binary

**Deliverable:** Source code, documentation, demo video, presentation

---

## 🛠️ Tools & Technologies

- **Cisco Packet Tracer** - Network simulation and design
- **C/C++** - Low-level network programming
- **Socket Programming** - Network communication
- **libpcap/pcapplusplus** - Packet capture and analysis
- **Git** - Version control

---

## 📂 Repository Structure

```
Networking-101/
├── README.md                    # This file
├── LICENSE                      # Repository license
├── Q1/                          # DNS and SSH Fundamentals
│   └── README.md
├── Q2/                          # VLAN Network Design
│   ├── README.md
│   └── diagram.jpg (optional)
├── Q3/                          # Static Routing
│   ├── README.md
│   └── diagram.jpg
├── Q4/                          # Dual ISP Redundancy
│   └── README.md
├── Q5/                          # NAT Configuration
│   └── README.md
├── Q6/                          # Multi-Site with RIP
│   ├── README.md
│   └── diagram.jpg
└── Q7-Final Project/            # Network Programming Project
    └── README.md
```

---

## 🎯 Learning Objectives

By completing this course, students will:

1. **Understand networking fundamentals** - DNS, routing, switching, VLANs
2. **Configure network devices** - Routers, switches, access points
3. **Design network topologies** - Multi-site, redundant, scalable networks
4. **Implement routing protocols** - Static routing, RIP
5. **Configure advanced features** - NAT, PAT, inter-VLAN routing
6. **Program network applications** - Socket programming, packet analysis
7. **Apply security concepts** - Understanding attack/defense mechanisms

---

## 🚀 Getting Started

### Prerequisites

- Install **Cisco Packet Tracer** (for Q2-Q6)
- **C/C++ compiler** (gcc/g++ for Linux, MSVC for Windows)
- **libpcap** development libraries (for Final Project)
- Basic understanding of networking concepts
- Linux/Windows operating system

### Installation

#### Cisco Packet Tracer

1. Download from [Cisco Networking Academy](https://www.netacad.com/)
2. Create a free account
3. Install on your system

#### Development Tools (for Final Project)

```bash
# Linux (Debian/Ubuntu)
sudo apt-get update
sudo apt-get install build-essential libpcap-dev

# Linux (Fedora/RHEL)
sudo dnf install gcc gcc-c++ libpcap-devel

# macOS
brew install libpcap

# Windows
# Install Visual Studio with C++ support
# Download WinPcap or Npcap
```

---

## 📝 Assignment Submission Guidelines

1. **Packet Tracer Files**: Submit `.pkt` files with proper labeling
2. **Screenshots**: Include verification of successful configurations
3. **Documentation**: Provide configuration details and explanations
4. **Code Projects**: Include source code, compilation instructions, and README
5. **Reports**: Use clear formatting with diagrams where applicable

---

## 📖 Additional Resources

### Networking Concepts

- Cisco Networking Academy courses
- Computer Networking: A Top-Down Approach (Kurose & Ross)
- TCP/IP Illustrated (Stevens)

### Socket Programming

- Beej's Guide to Network Programming
- Unix Network Programming (Stevens)

### Packet Capture

- libpcap documentation
- Wireshark documentation
- pcapplusplus GitHub repository
