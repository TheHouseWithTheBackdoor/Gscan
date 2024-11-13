# 🌐 Network Port Scanner

A fast and efficient network port scanner written in Bash for TCP and UDP scanning with MAC address discovery support.

## 🌟 Features

- 🚀 Fast parallel scanning
- 🔍 TCP port scanning
- 🌊 UDP port scanning (using netcat)
- 📡 Host discovery
- 💻 MAC address detection
- 🎯 IP range support (CIDR notation)
- 🎨 Colored output
- 🛡️ Error handling and input validation

## 📋 Prerequisites

The script requires the following tools:
- `bash` (version 4+)
- `nc` (netcat) - for UDP scanning
- `arp` - for MAC address discovery (optional)

## 🚀 Usage

```bash
Gscan [-u] [-i] <ip_range> [port1] [port2] [port3] ...
```

### 🎛️ Options

- `-u, --udp`: Use UDP instead of TCP scanning (requires netcat)
- `-i, --info`: Include MAC address information (requires arp command)

### 📝 Examples

```bash
# Scan TCP port 80 on local network
Gscan 192.168.1.0/24 80

# Scan multiple TCP ports
Gscan 192.168.1.0/24 80 443 8080

# Scan UDP port 53 (DNS)
Gscan -u 192.168.1.0/24 53

# Scan with MAC address detection
Gscan -i 192.168.1.0/24 80

# Host discovery (no ports specified)
Gscan 192.168.1.0/24
```

## 🎯 Output Examples

```bash
# TCP Scan
192.168.1.1 Port 80 is open
192.168.1.10 Port 80 is open (MAC: 00:1A:2B:3C:4D:5E)

# UDP Scan
192.168.1.1 Port 53 is open (UDP)

# Host Discovery
192.168.1.1 is active
192.168.1.10 is active (MAC: 00:1A:2B:3C:4D:5E)
```

## ⚡ Performance

- Uses parallel processing for faster scanning
- Efficient host discovery
- Quick response time for TCP scanning
- Accurate UDP port detection using netcat

## ⚠️ Limitations

- UDP scanning requires netcat installation
- MAC address discovery requires arp command
- Some systems may require root privileges for certain operations
- UDP scanning may be less reliable due to protocol nature

## 🔒 Security Notes

- Always ensure you have permission to scan the target network
- Some networks may block or detect port scanning activities
- Use responsibly and ethically

## 🛠️ Technical Details

The scanner uses:
- `/dev/tcp` for TCP scanning
- `netcat` for UDP scanning
- `ping` for host discovery
- `arp` for MAC address resolution
- BASH parallel processing for performance

## 💡 Tips

1. Run with sudo for better network access
2. Use small port ranges for faster results
3. UDP scanning might need multiple attempts
4. Consider network conditions when scanning
5. Check target network policies before scanning

## 🐛 Troubleshooting

**Common issues:**

1. Permission denied:
```bash
sudo Gscan [options]
```

2. Missing netcat or arp commands:
- The script will show relevant installation instructions when needed

## 📞 Contact

Create an issue for bugs, features, or questions.

---
Made with ❤️ by Garpoz Master
