<div align="center">

# 🌐 Network Fundamentals Lab

*Module 1: Foundation Level*

[![Foundation](https://img.shields.io/badge/Level-Foundation-green.svg)]()
[![Beginner](https://img.shields.io/badge/Difficulty-Beginner-brightgreen.svg)]()
[![Hands-on](https://img.shields.io/badge/Type-Hands--on-blue.svg)]()

**Master the essential building blocks of computer networks through interactive learning** 🎯

</div>

---

## 📚 Learning Objectives

By the end of this project, you will understand:

- 🏗️ **OSI Model**: The 7-layer conceptual framework for network communication
- 🌍 **Network Types**: LAN, WAN, and Internet distinctions
- 📧 **Addressing**: MAC and IP address concepts and differences
- 🚀 **Transport Protocols**: TCP vs UDP characteristics and use cases
- 🚪 **Port Management**: Understanding TCP/UDP ports and socket concepts
- 🔍 **Network Diagnostics**: Using ICMP and ping for network troubleshooting

## 📁 Project Structure

```
basics_0/
├── 0-OSI_model                    # OSI model quiz answers
├── 1-types_of_network             # Network types quiz answers  
├── 2-MAC_and_IP_address           # Addressing concepts quiz
├── 3-UDP_and_TCP                  # Transport protocols quiz
├── 4-TCP_and_UDP_ports            # Port listing script
├── 5-is_the_host_on_the_network   # Network connectivity script
└── README.md                      # This documentation
```

## 🔍 Detailed File Descriptions

### 🏗️ 0-OSI_model
**Purpose**: Understanding the OSI (Open Systems Interconnection) model

**Concepts Covered**:
- 🎯 OSI model as a conceptual framework (not physical implementation)
- 📊 Layer organization from lowest (Physical) to highest (Application)
- 🔢 7 layers: Physical → Data Link → Network → Transport → Session → Presentation → Application

**Key Points**:
- 🧠 The OSI model characterizes communication functions without regard to internal structure
- ⬆️ Organized from lowest level (Layer 1 - Physical) to highest level (Layer 7 - Application)
- 🎯 Focuses on Transport layer (TCP/UDP) and Network layer (IP/ICMP)

---

### 🌍 1-types_of_network
**Purpose**: Distinguishing between different network types

**Network Types**:
- 🏠 **LAN (Local Area Network)**: Connects local devices together
- 🌉 **WAN (Wide Area Network)**: Connects LANs together  
- 🌐 **Internet**: Global network of interconnected networks

**Real-world Applications**:
- 💻 Home/office computers connect to LAN
- 🏢 Different office locations connect via WAN
- 📱 Mobile data browsing uses Internet connectivity

---

### 📧 2-MAC_and_IP_address
**Purpose**: Understanding network addressing mechanisms

**MAC Address**:
- 🔖 **Definition**: Unique identifier of a network interface
- ⚙️ **Characteristics**: Hardware-based, burned into network cards
- 📊 **Scope**: Layer 2 (Data Link) addressing

**IP Address**:
- 🏠 **Definition**: Logical network address (like postal address for houses)
- 🔄 **Characteristics**: Software-assigned, can change
- 🌐 **Scope**: Layer 3 (Network) addressing

---

### 🚀 3-UDP_and_TCP
**Purpose**: Comparing transport layer protocols

**🐢 TCP (Transmission Control Protocol)**:
- ✅ **Characteristics**: Reliable, slower, connection-oriented
- 🔧 **Features**: Error checking, acknowledgments, retransmission
- 💎 **Use case**: When data integrity is critical

**🐰 UDP (User Datagram Protocol)**:
- ⚡ **Characteristics**: Fast, unreliable, connectionless
- 🎯 **Features**: No guarantees, minimal overhead
- 🏃 **Use case**: When speed is more important than reliability

**🤝 TCP Worker Behavior**:
- ❓ Asks for confirmations: "Have you received boxes x, y, z?"
- ✅ Ensures reliable delivery through acknowledgment system

---

### 🚪 4-TCP_and_UDP_ports
**Purpose**: Network port management and monitoring

**Script Functionality**:
```bash
#!/usr/bin/env bash
# Script that displays listening ports with PID and program names

netstat -lp
```

**Key Concepts**:
- 🚪 **Ports**: 65535 available ports per device
- 🔑 **Well-known ports**: 22 (SSH), 80 (HTTP), 443 (HTTPS)
- 🔌 **Socket**: Combination of IP address + port
- 👂 **Listening sockets**: Ports actively waiting for connections

**Command Flags**:
- 👂 `-l`: Show only listening sockets
- 🏷️ `-p`: Display PID and program names

**Usage**:
```bash
sudo ./4-TCP_and_UDP_ports
```
*⚠️ Note: sudo required to see process information for all users*

---

### 🔍 5-is_the_host_on_the_network
**Purpose**: Network connectivity testing using ICMP

**Script Functionality**:
```bash
#!/usr/bin/env bash
# Script that pings an IP address passed as an argument

if [ $# -eq 0 ]; then
    echo "Usage: 5-is_the_host_on_the_network {IP_ADDRESS}"
else
    ping -c 5 "$1"
fi
```

**📡 ICMP Protocol**:
- 🎯 **Purpose**: Internet Control Message Protocol for network diagnostics
- 🔍 **Function**: Check if network devices are available
- 🏹 **Tool**: `ping` command uses ICMP

**✨ Features**:
- ✅ Validates argument presence
- 📦 Sends exactly 5 ICMP packets
- ℹ️ Displays usage information when no argument provided
- ⏱️ Measures round-trip time (RTT) for network performance analysis

**📝 Usage Examples**:
```bash
./5-is_the_host_on_the_network 8.8.8.8  # Test Google DNS
./5-is_the_host_on_the_network           # Show usage
```

## 🛠️ Prerequisites

- 💻 **Operating System**: Unix-like system (Linux/macOS)
- 🐚 **Shell**: Bash
- ⚙️ **Commands**: `netstat`, `ping`
- 🔒 **Permissions**: Some scripts may require `sudo` for full functionality

## 🚀 Getting Started

1. ⚙️ **Make scripts executable**:
   ```bash
   chmod +x 4-TCP_and_UDP_ports
   chmod +x 5-is_the_host_on_the_network
   ```

2. 📝 **Run the quiz files** (contain answer numbers):
   ```bash
   cat 0-OSI_model
   cat 1-types_of_network  
   cat 2-MAC_and_IP_address
   cat 3-UDP_and_TCP
   ```

3. ▶️ **Execute scripts**:
   ```bash
   sudo ./4-TCP_and_UDP_ports
   ./5-is_the_host_on_the_network 8.8.8.8
   ```

## 📚 Additional Resources

### 🚪 Important Port Numbers
| Port | Protocol | Service |
|------|----------|---------|
| 22   | TCP      | 🔑 SSH (Secure Shell) |
| 80   | TCP      | 🌐 HTTP (Web) |
| 443  | TCP      | 🔒 HTTPS (Secure Web) |
| 53   | TCP/UDP  | 🌍 DNS |
| 25   | TCP      | 📧 SMTP (Email) |
| 110  | TCP      | 📨 POP3 (Email) |
| 143  | TCP      | 📩 IMAP (Email) |

### 🏗️ OSI Model Layers
1. ⚡ **Physical**: Electrical signals, cables, hardware
2. 🔗 **Data Link**: MAC addresses, switches, frames
3. 🌐 **Network**: IP addresses, routers, packets
4. 🚀 **Transport**: TCP/UDP, ports, segments
5. 🔗 **Session**: Connection management
6. 🔐 **Presentation**: Encryption, compression
7. 📱 **Application**: HTTP, FTP, SMTP

### 🔧 Network Troubleshooting Tips
- 🐌 **Slow connection**: Use `ping` to test latency
- 🔌 **Connection issues**: Check listening ports with `netstat`
- 🌍 **DNS problems**: Ping IP addresses directly (e.g., 8.8.8.8)
- ⚠️ **Port conflicts**: Identify processes using specific ports

## 🎯 Key Takeaways

1. 🏗️ **OSI Model**: Conceptual framework, not physical implementation
2. 🌍 **Network Types**: LAN (local), WAN (wide area), Internet (global)
3. 📧 **Addressing**: MAC (hardware) vs IP (logical) addresses
4. 🚀 **Protocols**: TCP (reliable) vs UDP (fast) trade-offs
5. 🚪 **Ports**: Entry points for network services (65535 per device)
6. 🔍 **ICMP**: Essential for network diagnostics and connectivity testing

## 👨‍💻 Author

**Héctor Soto** - [@hector17rock](https://github.com/hector17rock)

## 📝 Repository Information

- 📁 **Repository**: HBNB-Library
- 📂 **Directory**: Network_PROJECT/basics_0
- 📚 **Project**: Network Fundamentals
- 🎯 **Focus**: OSI Model, Network Types, Addressing, Protocols, Diagnostics
- 👨‍💻 **Author**: [Héctor Soto](https://github.com/hector17rock)

---

*🌟 This README provides comprehensive coverage of fundamental networking concepts essential for understanding computer networks and network administration.*
