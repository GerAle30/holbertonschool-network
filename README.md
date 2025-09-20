<div align="center">

# 🌐 Network Mastery Lab

*Your Gateway to Network Engineering Excellence*

[![Made with ❤️](https://img.shields.io/badge/Made%20with-❤️-red.svg)]()
[![Network Engineering](https://img.shields.io/badge/Network-Engineering-blue.svg)]()
[![Linux](https://img.shields.io/badge/Platform-Linux-green.svg)]()
[![Bash](https://img.shields.io/badge/Shell-Bash-yellow.svg)]()
[![Open Source](https://img.shields.io/badge/Open-Source-orange.svg)]()

**Master the fundamentals of networking through hands-on practice and real-world scenarios** 🚀

</div>

---

## 🎯 **What You'll Become**

Transform from networking novice to network ninja with our comprehensive lab environment. This isn't just another tutorial – it's your complete training ground for mastering network fundamentals and system administration.

<table>
<tr>
<td width="50%">

### 🏆 **Core Competencies**
- ✨ **OSI Model Mastery** - Deep understanding of the 7-layer framework
- 🌍 **Network Architecture** - LAN, WAN, and Internet topologies
- 🔐 **Protocol Expertise** - TCP/UDP, ICMP, and addressing schemes
- ⚡ **Performance Optimization** - Port management and diagnostics
- 🛡️ **Security Fundamentals** - Network troubleshooting and hardening

</td>
<td width="50%">

### 🎓 **Learning Path**
1. **Foundation** → Network theory & concepts
2. **Application** → Hands-on scripting & tools
3. **Mastery** → Advanced administration tasks
4. **Expertise** → Real-world problem solving

</td>
</tr>
</table>

## 🏗️ **Lab Architecture**

```
🌐 Network Mastery Lab/
├── 📚 basics_0/                    ← Foundation Level
│   ├── 🧠 OSI Model Deep Dive
│   ├── 🌍 Network Types & Topologies
│   ├── 📧 MAC vs IP Addressing
│   ├── ⚡ TCP/UDP Protocol Wars
│   ├── 🚪 Port Scanning & Analysis
│   └── 🔍 Network Connectivity Testing
│
├── 🔧 basics_1/                    ← Advanced Level
│   ├── 🏠 DNS Hijacking Lab
│   ├── 📊 Network Interface Discovery
│   └── 🔊 Network Listener Creation
│
└── 📖 Complete Documentation
```

## 🚀 Learning Path & Modules

### 📚 Module 1: Network Fundamentals (basics_0)

**🎓 Learning Objectives:**
- Master the OSI model and its 7 layers
- Understand network types and their applications
- Differentiate between MAC and IP addressing
- Compare TCP vs UDP protocols
- Learn port management and socket concepts
- Practice network diagnostics with ICMP

**📝 Content Type:** Quiz-based learning with practical scripts
**⏱️ Estimated Time:** 2-3 hours
**🔧 Prerequisites:** Basic understanding of computers and internet

**🔍 Key Topics Covered:**
- 🏗️ **OSI Model**: 7-layer network communication framework
- 🌍 **Network Types**: LAN, WAN, and Internet distinctions
- 📧 **Addressing**: MAC vs IP address concepts
- 🚀 **Protocols**: TCP/UDP characteristics and use cases
- 🚪 **Ports**: Understanding network ports and sockets
- 🔍 **Diagnostics**: ICMP and ping for troubleshooting

---

### 🔧 Module 2: Network Administration (basics_1)

**🎓 Learning Objectives:**
- Implement DNS resolution modifications
- Discover and analyze network interfaces
- Create network listeners for debugging
- Practice system-level network configuration
- Develop network troubleshooting skills

**🛠️ Content Type:** Executable Bash scripts and practical exercises
**⏱️ Estimated Time:** 3-4 hours
**🔧 Prerequisites:** Module 1 completion, basic Unix/Linux knowledge

**🔍 Key Skills Developed:**
- 🏠 **DNS Management**: Modifying hosts file for custom resolution
- 📊 **Interface Analysis**: Discovering active network interfaces
- 🔊 **Network Debugging**: Creating listeners for connection testing
- 🛡️ **Security Practices**: Safe system configuration changes
- 📞 **Troubleshooting**: Practical network problem solving

## 🛠️ System Requirements

### 💻 Operating System Compatibility
- **Primary Support**: 🐧 Ubuntu/Linux distributions
- **Secondary Support**: 🍎 macOS (with some limitations)
- **Architecture**: 💪 x86_64, ARM64/Apple Silicon

### 🧰 Required Tools & Dependencies

**📜 Core Tools:**
- `bash` (version 4.0+)
- `grep` with Extended Regular Expression support
- `sed` for text processing

**🌐 Network Tools:**
- `ping` (ICMP utilities)
- `netstat` (network statistics)
- `ifconfig` (interface configuration)
- `netcat`/`nc` (network connections)
- `telnet` (network testing)

### 📦 Installation Commands

**🐧 Ubuntu/Debian:**
```bash
sudo apt update
sudo apt install net-tools netcat-openbsd iputils-ping telnet
```

**🍎 macOS:**
```bash
# Most tools are pre-installed
brew install gnu-sed  # Optional: for GNU sed compatibility
```

**🏭 CentOS/RHEL:**
```bash
sudo yum install net-tools nc iputils telnet
```

## 🚀 Quick Start Guide

### 1. 📥 Setup & Installation

```bash
# Navigate to the project directory
cd Network_PROJECT

# Make all scripts executable
find . -name "*.sh" -o -name "*-*" | grep -E "(4-TCP|5-is|0-change|1-show|2-port)" | xargs chmod +x
```

### 2. 📚 Start with Fundamentals (Recommended Path)

```bash
# Begin with networking theory
cd basics_0

# Review concept files (these contain quiz answers)
cat 0-OSI_model
cat 1-types_of_network
cat 2-MAC_and_IP_address
cat 3-UDP_and_TCP

# Practice with scripts
sudo ./4-TCP_and_UDP_ports        # View listening ports
./5-is_the_host_on_the_network 8.8.8.8  # Test connectivity
```

### 3. 🔧 Progress to Practical Tools

```bash
# Move to hands-on administration
cd ../basics_1

# Discover your network interfaces
./1-show_attached_IPs

# Test network listener (use two terminals)
# Terminal 1: Start listener
sudo ./2-port_listening_on_localhost

# Terminal 2: Connect to listener
telnet localhost 98
```

### 4. ⚠️ Advanced DNS Modification (Use with Caution)

```bash
# ⚠️ WARNING: This modifies system DNS resolution
# Only run in test environments or with full understanding

# Backup current hosts file
sudo cp /etc/hosts /etc/hosts.original

# Apply DNS changes
sudo ./0-change_your_home_IP

# Test changes
ping -c 1 localhost  # Should show 127.0.0.2
ping -c 1 facebook.com  # Should show 8.8.8.8

# Restore original (IMPORTANT!)
sudo cp /etc/hosts.original /etc/hosts
```

## 📋 Detailed Module Breakdown

### 📚 Module 1 Details: Network Fundamentals

| File | Type | Purpose | Difficulty |
|------|------|---------|------------|
| `0-OSI_model` | 📝 Quiz | Understanding 7-layer network model | 🟢 Beginner |
| `1-types_of_network` | 📝 Quiz | LAN vs WAN vs Internet concepts | 🟢 Beginner |
| `2-MAC_and_IP_address` | 📝 Quiz | Hardware vs logical addressing | 🟢 Beginner |
| `3-UDP_and_TCP` | 📝 Quiz | Transport protocol comparison | 🟡 Intermediate |
| `4-TCP_and_UDP_ports` | 🔧 Script | Port monitoring and analysis | 🟡 Intermediate |
| `5-is_the_host_on_the_network` | 🔧 Script | Network connectivity testing | 🟡 Intermediate |

### 🔧 Module 2 Details: Network Administration

| File | Type | Purpose | Difficulty | Risk Level |
|------|------|---------|------------|------------|
| `1-show_attached_IPs` | 🔧 Script | Interface IP discovery | 🟢 Beginner | 🟢 Safe |
| `2-port_listening_on_localhost` | 🔧 Script | Network debugging listener | 🟡 Intermediate | 🟢 Safe |
| `0-change_your_home_IP` | 🔧 Script | DNS resolution modification | 🔴 Advanced | 🟡 Medium Risk |

## 🔒 Security & Safety Guidelines

### 🛡️ General Security Practices
- 🔍 **Review First**: Always examine scripts before execution
- 🧪 **Test Environment**: Use isolated/test systems when possible
- 💾 **Backup Critical Files**: Especially `/etc/hosts` and network configs
- 🔐 **Minimal Privileges**: Run with least necessary permissions
- 📊 **Monitor Changes**: Track network modifications and their effects

### ⚠️ Important Warnings

**🏠 DNS Modification Script (0-change_your_home_IP):**
- **Risk Level**: 🟡 Medium
- **Impact**: System-wide DNS resolution changes
- **Precaution**: Always backup `/etc/hosts` before modification
- **Recommendation**: Use only in isolated test environments
- **Recovery**: Script creates automatic backup at `/etc/hosts.backup`

**🔊 Network Listener Script (2-port_listening_on_localhost):**
- **Risk Level**: 🟢 Low
- **Impact**: Opens local network port 98
- **Scope**: Localhost only (127.0.0.1)
- **Security**: No external network exposure

## 🐛 Troubleshooting Guide

### ⚠️ Common Issues & Solutions

**🚫 Permission Denied:**
```bash
# Make scripts executable
chmod +x script-name

# Use sudo for system-level operations
sudo ./script-name
```

**📋 Command Not Found:**
```bash
# Install missing network tools
sudo apt install net-tools netcat-openbsd  # Ubuntu/Debian
sudo yum install net-tools nc              # CentOS/RHEL
```

**🚪 Port Already in Use:**
```bash
# Check what's using the port
sudo lsof -i :98
sudo netstat -tlnp | grep :98

# Kill conflicting process if needed
sudo kill -9 <PID>
```

**🌐 Network Connectivity Issues:**
```bash
# Test basic connectivity
ping -c 4 8.8.8.8          # Test Internet
ping -c 4 127.0.0.1        # Test loopback
ip addr show               # Check interfaces (modern)
ifconfig                   # Check interfaces (traditional)
```

### 🖥️ Platform-Specific Notes

**🍎 macOS Considerations:**
- Some network tools have different command options
- System Integrity Protection may affect `/etc/hosts` modifications
- Use `brew` for additional GNU tools if needed
- `sed -i` requires backup extension: `sed -i .bak`

**🐧 Linux Distribution Differences:**
- Package names may vary between distributions
- SELinux/AppArmor may restrict network operations
- Firewall rules might affect network testing
- Different default network interface names (eth0 vs ens33)

## 📚 Learning Resources & References

### 📖 Essential Documentation
- 📋 `man ifconfig` - Network interface configuration
- 📁 `man hosts` - Host name resolution file format
- 🔌 `man nc` - Netcat networking utility
- 🌐 `man ping` - Network connectivity testing
- 📊 `man netstat` - Network statistics and connections

### 🛠️ Additional Network Tools
- **Modern Alternatives:**
  - `ip` - Modern replacement for ifconfig
  - `ss` - Modern replacement for netstat
  - `dig`/`nslookup` - DNS lookup utilities
- **Advanced Tools:**
  - `tcpdump` - Packet capture and analysis
  - `wireshark` - GUI network protocol analyzer
  - `nmap` - Network discovery and port scanning

### 🏗️ Network Protocol References

**🌐 Important Port Numbers:**
| Port | Protocol | Service | Usage |
|------|----------|---------|-------|
| 22 | TCP | 🔑 SSH | Secure remote access |
| 53 | TCP/UDP | 🌍 DNS | Domain name resolution |
| 80 | TCP | 🌐 HTTP | Web traffic |
| 443 | TCP | 🔒 HTTPS | Secure web traffic |
| 25 | TCP | 📧 SMTP | Email sending |
| 110 | TCP | 📨 POP3 | Email retrieval |
| 143 | TCP | 📩 IMAP | Email access |

**🏗️ OSI Model Quick Reference:**
1. ⚡ **Physical**: Hardware, cables, electrical signals
2. 🔗 **Data Link**: MAC addresses, switches, frames
3. 🌐 **Network**: IP addresses, routers, packets
4. 🚀 **Transport**: TCP/UDP, ports, segments
5. 🔗 **Session**: Connection management, sessions
6. 📄 **Presentation**: Encryption, compression, formatting
7. 💻 **Application**: User applications, HTTP, FTP, email

## 🎓 Skills Assessment & Certification

After completing this project, you should be able to:

### 📚 Theoretical Knowledge
- ✅ Explain the OSI model and its practical applications
- ✅ Differentiate between network types and their use cases
- ✅ Understand addressing mechanisms (MAC vs IP)
- ✅ Compare and contrast TCP vs UDP protocols
- ✅ Identify common network ports and their services

### 🔧 Practical Skills
- ✅ Monitor network ports and active connections
- ✅ Test network connectivity using various tools
- ✅ Discover and analyze network interfaces
- ✅ Modify system DNS resolution safely
- ✅ Create network debugging tools
- ✅ Troubleshoot common network issues

### 🛡️ Security Awareness
- ✅ Understand the security implications of network modifications
- ✅ Implement safe testing practices
- ✅ Backup and restore system configurations
- ✅ Recognize and mitigate network security risks

## 🔗 Next Steps & Advanced Topics

### 🚀 Intermediate Networking
- **Network Configuration**: Static IP setup, routing tables
- **Firewall Management**: iptables, ufw, firewalld
- **VPN Setup**: OpenVPN, WireGuard configuration
- **Load Balancing**: HAProxy, Nginx configurations

### 🏢 Enterprise Networking
- **VLAN Configuration**: Virtual LAN management
- **Network Monitoring**: Nagios, Zabbix, PRTG
- **Network Automation**: Ansible, Puppet, Chef
- **Container Networking**: Docker, Kubernetes networking

### 🔒 Network Security
- **Penetration Testing**: Nmap, Metasploit, Burp Suite
- **Network Forensics**: Wireshark analysis, log investigation
- **Intrusion Detection**: Snort, Suricata, OSSEC
- **Security Hardening**: Network device configuration

## 👤 Author

**Héctor Soto** - [@hector17rock](https://github.com/hector17rock)

*Network engineer and system administrator passionate about sharing knowledge and building practical learning resources for the tech community.*

---

## 📄 License & Usage

This project is created for educational purposes and practical learning. Feel free to:
- 🔄 Fork and modify for your learning needs
- 📚 Use in educational environments
- 🤝 Contribute improvements and additional exercises
- 📖 Share with other learners and students

## 🤝 Contributing

Contributions are welcome! Areas for improvement:
- 🆕 Additional network exercises and scripts
- 📝 More comprehensive documentation
- 🐛 Bug fixes and improvements
- 🌍 Multi-language support
- 🧪 Additional test cases and examples

## 📞 Support & Contact

- 🐛 **Issues**: Report bugs or request features via GitHub Issues
- 💬 **Questions**: Discussion and questions welcome
- 📧 **Contact**: Connect via GitHub profile
- 🌟 **Feedback**: Your experience and suggestions are valuable!

---

**📚 Repository**: HBNB-Library  
**📁 Project**: Network_PROJECT  
**🎯 Focus**: Networking fundamentals and practical administration

*📅 Last updated: September 2024*