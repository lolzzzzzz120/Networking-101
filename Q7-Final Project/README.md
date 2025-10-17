# Final Project: Network Programming - Malware & Antivirus Simulation

## Introduction to Network Programming

---

## ⚠️ Important Disclaimer

This project is designed for **EDUCATIONAL PURPOSES ONLY**. You will simulate a simple malware and antivirus system to understand network programming concepts.

**Critical Notes:**

- This project focuses on **learning**, NOT security evasion
- **NO** attempt to bypass firewalls or real antivirus software is expected
- **Disable** your firewall and antivirus during testing and execution
- **NEVER** use these techniques outside of your controlled lab environment
- Unauthorized use of these techniques may be illegal

---

## Introduction

In this project, you will learn how to implement simple network communication between systems using **socket programming**. One of the most important aspects of network programming is understanding how systems within a network communicate with each other.

**Inspiration:**
You can review the **Metasploit Framework** for ideas and concepts.

---

## Project Description

You must develop **3 separate binary programs** to complete this project.

### Scenario 1: Remote Access Tool (RAT) Simulation

Develop two binaries:

1. **Attacker Binary** (C2 Server - Command and Control)
2. **Victim Binary** (Agent/Implant)

**Requirements:**

- Run these binaries on two different computers
- The victim binary grants the attacker access to the victim computer
- Access level: Limited to the user privileges running the victim binary

---

## Core Requirements

### Part 1: Attacker Binary Capabilities

The attacker binary must support the following commands:

#### 1. File Download

- **Retrieve files** from the victim computer from various paths
- Support multiple file types
- Handle different file sizes

#### 2. Screenshot Capture

- **Capture screenshots** from the victim's display
- Retrieve and display on attacker machine

#### 3. Mouse Control

- **Control the victim's mouse** remotely
- Send mouse movement and click commands

### Part 2: Session Management

**Multi-Target Management:**

- The attacker binary must handle **multiple victims simultaneously**
- Manage different sessions for each victim
- Session switching and identification capabilities

**Heartbeat Mechanism:**

- All victim binaries must send a **heartbeat (keep-alive)** signal to the attacker
- Frequency: **Every 1 minute**
- Indicates the victim binary is still active

---

## Scenario 2: Antivirus Detection

Develop the third binary: **Antivirus/IDS (Intrusion Detection System)**

**Requirements:**

- After establishing the connection in Scenario 1, this program should detect the attack
- **Analyze network traffic** passing through the victim system
- **Identify suspicious traffic** patterns
- **Alert the user** about detected threats

**Implementation:**

- Build a simple antivirus that can detect the threat YOU created
- Use packet inspection techniques
- Pattern matching for suspicious communication

---

## Bonus Features (Ordered by Importance)

Extra credit will be awarded for implementing the following features:

### 1. Creativity ⭐

- Creative implementation of the binaries
- Innovative approaches to solving problems

### 2. Performance Optimization ⭐

- Increase data transfer speed between victim and attacker
- Efficient network communication protocols

### 3. File Upload & Execution ⭐

- Send files from attacker to victim
- Execute uploaded files on victim machine

### 4. Persistence & Stability ⭐

- Prevent victim binary from crashing
- Automatic startup on system boot
- Auto-restart mechanism if process terminates

### 5. Direct Shell Access ⭐

- Attacker gains direct shell/command prompt access to victim system
- Execute arbitrary commands

### 6. File Binding ⭐

- Combine victim binary with legitimate files (e.g., PDF documents)
- Trojan horse implementation

### 7. Evasion Techniques ⭐

- Encrypt binaries to evade antivirus detection
- Obfuscation techniques

### 8. Testing & Validation ⭐

- Implement comprehensive tests
- Test different scenarios and conditions
- Performance benchmarking

---

## Project Constraints

### Attacker Binary

- **No restrictions** on programming language or libraries
- Use any language: Python, Go, Rust, C/C++, etc.

### Victim Binary

- **Must be written in C/C++**
- Standard libraries allowed
- Cross-platform support recommended

### Antivirus Binary

- **Must be written in C/C++**
- **Cannot use** ready-made tools like `tcpdump`, `dumpcap`, or similar utilities
- **Must use** packet capture libraries:
  - `libpcap` (Linux/Unix)
  - `pcapplusplus` (Cross-platform)
  - `WinPcap` or `Npcap` (Windows)
  - Similar low-level packet capture libraries

---

## Project Objectives

### Learning Goals

1. **Socket Programming**
   - TCP/UDP communication
   - Client-server architecture
   - Network protocols

2. **Packet Capture with libpcap**
   - Traffic analysis
   - Packet inspection
   - Protocol dissection

3. **Documentation**
   - Document your development process
   - Explain design decisions
   - Share lessons learned

4. **Cross-Platform Development**
   - Implementation for **Linux** and **Windows**
   - Handle OS-specific differences
   - Portable code practices

---

## Technical Requirements

### Network Communication

- Use **socket programming** (TCP or UDP)
- Protocol design for commands and data transfer
- Error handling and reconnection logic

### Packet Capture (Antivirus)

```c
// Example using libpcap
#include <pcap.h>

pcap_t *handle;
char errbuf[PCAP_ERRBUF_SIZE];
struct bpf_program fp;

// Open network device
handle = pcap_open_live(dev, BUFSIZ, 1, 1000, errbuf);

// Capture packets
pcap_loop(handle, num_packets, packet_handler, NULL);
```

### File Transfer Protocol

- Design efficient file transfer mechanism
- Chunking for large files
- Integrity checks (checksums/hashes)

### Screenshot Capture

- Platform-specific APIs:
  - **Linux**: X11 or Wayland APIs
  - **Windows**: GDI/GDI+ or Windows Graphics Capture API

---

## Deliverables

### 1. Source Code

- **Attacker binary** source code
- **Victim binary** source code (C/C++)
- **Antivirus binary** source code (C/C++)
- Compilation instructions (Makefile or CMake)

### 2. Documentation

- **Project report** (minimum 10 pages) including:
  - Architecture design
  - Protocol specification
  - Implementation details
  - Challenges faced and solutions
  - Testing methodology
  - Screenshots and demonstrations
  - Lessons learned

### 3. Demonstration Video

- Show the complete system in action
- Demonstrate all core features
- Show antivirus detection

### 4. Presentation

- Final presentation to class
- Live demonstration
- Q&A session

---

## Development Guidelines

### Phase 1: Basic Communication

1. Implement simple socket communication
2. Test connection between two machines
3. Implement heartbeat mechanism

### Phase 2: Core Features

1. File download functionality
2. Screenshot capture
3. Mouse control
4. Session management

### Phase 3: Antivirus Development

1. Packet capture setup
2. Traffic analysis
3. Pattern detection
4. Alert system

### Phase 4: Enhancement & Testing

1. Implement bonus features
2. Cross-platform testing
3. Performance optimization
4. Documentation

---

## Testing Environment

### Lab Setup

- Use **virtual machines** for safe testing
- Separate networks for isolation
- **Never test on production systems**

### Recommended Tools

- **Wireshark**: For traffic analysis
- **VirtualBox/VMware**: For virtual machines
- **GDB/LLDB**: For debugging
- **Valgrind**: For memory leak detection

---

## Grading Criteria

| Component | Weight |
|-----------|--------|
| Core Functionality (Attacker + Victim) | 40% |
| Antivirus Detection | 30% |
| Documentation | 15% |
| Code Quality & Design | 10% |
| Bonus Features | 5% |

---

## Resources

### Socket Programming

- Beej's Guide to Network Programming
- Stevens' "Unix Network Programming"

### Packet Capture

- libpcap documentation
- pcapplusplus examples
- Wireshark source code

### Security Concepts

- Metasploit Framework documentation
- MITRE ATT&CK Framework

---

## Submission Guidelines

- Submit via Git repository (GitHub/GitLab)
- Include README with build instructions
- Provide demo video link
- Schedule presentation slot

---

**Good luck with your final project! 🚀**
