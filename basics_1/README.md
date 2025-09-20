<div align="center">

# 🌐 Network Administration Lab

*Module 2: Advanced Level*

[![Advanced](https://img.shields.io/badge/Level-Advanced-orange.svg)]()
[![Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow.svg)]()
[![Practical](https://img.shields.io/badge/Type-Practical-blue.svg)]()
[![Bash](https://img.shields.io/badge/Language-Bash-green.svg)]()

**Master network administration through hands-on Bash scripting and real-world scenarios** 🚀

</div>

---

## 🎯 **What You'll Master**

Dive deep into network administration with practical scripts that demonstrate essential networking concepts. These aren't just examples – they're real tools used by system administrators and network engineers.

## 📁 Directory Structure

```
basics_1/
├── 0-change_your_home_IP          # Modify DNS resolution for localhost and domains
├── 1-show_attached_IPs            # Display all active IPv4 addresses
├── 2-port_listening_on_localhost  # Create a network listener on localhost
└── README.md                      # This documentation
```

## 🚀 Scripts Overview

### 🏠 0-change_your_home_IP
**Purpose**: Modifies the `/etc/hosts` file to change DNS resolution for localhost and facebook.com. 🔄

**What it does**:
- 🔄 Changes `localhost` resolution from `127.0.0.1` to `127.0.0.2`
- 🌐 Redirects `facebook.com` to resolve to `8.8.8.8` (Google DNS)
- 💾 Creates a backup of the original `/etc/hosts` file

**Usage**:
```bash
sudo ./0-change_your_home_IP
```

**Requirements**:
- Root privileges (must run with `sudo`)
- Linux/Ubuntu system (modifies `/etc/hosts`)

**⚠️ Warning**: This script modifies system DNS resolution. Revert changes after testing to avoid breaking system functionality.

**Example Output**:
```bash
# Before running script
$ ping localhost
PING localhost (127.0.0.1) 56(84) bytes of data.

# After running script  
$ ping localhost
PING localhost (127.0.0.2) 56(84) bytes of data.
```

### 🔍 1-show_attached_IPs
**Purpose**: Displays all active IPv4 addresses configured on the current machine. 📶

**What it does**:
- 🔍 Scans all network interfaces
- 📊 Extracts and displays IPv4 addresses
- 🌐 Works on both Linux and macOS systems

**Usage**:
```bash
./1-show_attached_IPs
```

**Example Output**:
```bash
$ ./1-show_attached_IPs
127.0.0.1
192.168.1.14
192.168.2.1
```

**📝 Technical Details**:
- ⚙️ Uses `ifconfig` command to gather interface information
- 🔍 Employs regex pattern matching to extract IP addresses
- ✅ Compatible with different `ifconfig` output formats

### 🔊 2-port_listening_on_localhost
**Purpose**: Creates a network listener on port 98 of localhost for debugging and testing network connections. 🔌

**What it does**:
- 🎯 Binds to port 98 on localhost (127.0.0.1)
- 👂 Listens for incoming connections
- 💬 Displays any text received from connected clients
- 🔧 Useful for network debugging and testing

**Usage**:
```bash
# Terminal 1 - Start the listener
sudo ./2-port_listening_on_localhost

# Terminal 2 - Connect and send data
telnet localhost 98
```

**Example Session**:
```bash
# Terminal 1
$ sudo ./2-port_listening_on_localhost
Hello world
test message

# Terminal 2
$ telnet localhost 98
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
Hello world
test message
```

**💼 Use Cases**:
- 🔍 Debugging socket connection issues
- 🛡️ Testing firewall rules
- 🌐 Network connectivity troubleshooting
- 🔄 Inter-process communication testing

## 🛠 System Requirements

### 💻 Operating System Support
- **Primary**: 🐧 Ubuntu/Linux distributions
- **Secondary**: 🍎 macOS (with some limitations)
- **Architecture**: 💪 x86_64, ARM64

### 🛠️ Required Tools
- 📜 `bash` (version 4.0+)
- 🌐 `ifconfig` (net-tools package)
- 🔌 `netcat` (`nc` command)
- 🔍 `grep` with Extended Regular Expression support
- ✂️ `sed` for text processing

### 📦 Installation of Dependencies

**🐧 Ubuntu/Debian**:
```bash
sudo apt update
sudo apt install net-tools netcat-openbsd
```

**🍎 macOS**:
```bash
# netcat is pre-installed
# ifconfig is available in base system
brew install gnu-sed  # Optional: for GNU sed compatibility
```

**🏭 CentOS/RHEL**:
```bash
sudo yum install net-tools nc
```

## 🔧 Setup Instructions

1. 📺 **Clone or download** the scripts to your system
2. ⚙️ **Make scripts executable**:
   ```bash
   chmod +x 0-change_your_home_IP
   chmod +x 1-show_attached_IPs  
   chmod +x 2-port_listening_on_localhost
   ```
3. 📦 **Install dependencies** (if not already present)
4. ✅ **Test basic functionality**:
   ```bash
   ./1-show_attached_IPs  # Should work without root
   ```

## 📋 Usage Examples

### 🔍 Basic Network Interface Discovery
```bash
# Show all IPv4 addresses
./1-show_attached_IPs

# Show with line endings visible
./1-show_attached_IPs | cat -e
```

### 📞 Network Debugging Session
```bash
# Start listener in background
sudo ./2-port_listening_on_localhost &

# Test connection
echo "Hello Network" | nc localhost 98

# Or use telnet interactively
telnet localhost 98
```

### 🌐 DNS Resolution Testing
```bash
# Check current resolution
ping -c 1 localhost

# Apply changes
sudo ./0-change_your_home_IP

# Verify changes
ping -c 1 localhost
ping -c 1 facebook.com

# Restore original (recommended)
sudo cp /etc/hosts.backup /etc/hosts
```

## 🔒 Security Considerations

### 🏠 Script 0: DNS Modification
- **Risk Level**: 🟡 Medium
- **Impact**: 🌐 System-wide DNS resolution changes
- **Mitigation**: 💾 Always backup `/etc/hosts` before modification
- **Recommendation**: 🧪 Use only in test environments

### 🔊 Script 2: Network Listener
- **Risk Level**: 🟢 Low
- **Impact**: 🔌 Opens a local network port
- **Port Range**: 📍 98 (typically unrestricted)
- **Binding**: 🏠 localhost only (127.0.0.1)

### 🛡️ General Security Practices
- 🔐 Run scripts with minimal necessary privileges
- 🔍 Review script contents before execution
- 🧪 Use in isolated/test environments when possible
- 🔍 Monitor network connections during testing

## 🐛 Troubleshooting

### ⚠️ Common Issues

**🚫 Permission Denied**:
```bash
# Solution: Make scripts executable
chmod +x script-name

# For system file modifications:
sudo ./script-name
```

**📋 Command Not Found (ifconfig)**:
```bash
# Ubuntu/Debian
sudo apt install net-tools

# Alternative: use ip command
ip addr show
```

**🚪 Port Already in Use**:
```bash
# Check what's using port 98
sudo lsof -i :98
sudo netstat -tlnp | grep :98

# Kill process if needed
sudo kill -9 <PID>
```

**🔌 netcat Variations**:
```bash
# Different netcat implementations
nc -l 98          # Some systems
nc -l -p 98       # Others  
nc -l 127.0.0.1 98  # Explicit binding (recommended)
```

### 💻 Platform-Specific Notes

**🍎 macOS Differences**:
- ✂️ `sed -i` requires backup extension: `sed -i .bak`
- 🛠️ Some network tools have different options
- 🛡️ System Integrity Protection may affect `/etc/hosts`

**🐧 Linux Variations**:
- 📦 Different distributions may have varying default tools
- 🛡️ SELinux/AppArmor may restrict network operations
- 🔥 Firewall rules might block connections

## 📚 Learning Objectives

After working with these scripts, you should understand:

1. **🌐 Network Interface Management**
   - 🔍 How to discover active network interfaces
   - 📊 IPv4 address configuration and display
   - 📈 Interface status and statistics

2. **🔍 DNS and Name Resolution**
   - 📁 `/etc/hosts` file structure and purpose
   - 🔄 Local DNS override mechanisms
   - ⚡ Impact of DNS changes on system behavior

3. **🔍 Network Debugging**
   - 🔊 Basic network listeners and clients
   - 🔗 TCP connection establishment
   - 🔌 Port binding and socket programming concepts

4. **🔧 System Administration**
   - 💾 File backup strategies
   - 🔐 Privilege escalation requirements
   - ⚙️ System configuration modification safety

## 🔗 Related Topics

- **🌐 Network Configuration**: IP addressing, subnetting, routing
- **🔍 DNS Management**: BIND, systemd-resolved, network configuration
- **🔌 Socket Programming**: TCP/UDP protocols, client-server architecture  
- **📈 System Monitoring**: `netstat`, `ss`, `lsof` for network analysis
- **🛡️ Security**: Firewall configuration, port scanning, network security

## 📖 Additional Resources

### 📚 Documentation
- 📋 `man ifconfig` - Interface configuration manual
- 📁 `man hosts` - Hosts file format documentation  
- 🔌 `man nc` - Netcat manual and examples

### 🛠️ Network Tools
- 🌐 `ip` - Modern replacement for ifconfig
- 📈 `ss` - Modern replacement for netstat
- 🔍 `dig`/`nslookup` - DNS lookup tools
- 📊 `tcpdump`/`wireshark` - Packet capture and analysis

### ✅ Best Practices
- 🧪 Always test network changes in safe environments
- 📝 Document configuration changes
- 📁 Use version control for configuration files
- 📈 Implement monitoring for network services

---

## 📝 Notes

- 🎓 Scripts are designed for educational purposes and basic system administration
- 🔍 Always review and test scripts before using in production environments
- 💾 Backup important system files before making modifications
- 🛠️ Consider using configuration management tools for production deployments

## 👤 Author

**Héctor Soto** - [@hector17rock](https://github.com/hector17rock)

---

**📚 Repository**: HBNB-Library  
**📁 Project**: Network_PROJECT  
**📂 Directory**: basics_1

*📅 Last updated: September 2024*
