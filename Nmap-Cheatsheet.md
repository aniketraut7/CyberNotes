# 📍 Nmap Cheatsheet

**Nmap** (Network Mapper) is one of the most powerful and widely used tools for network reconnaissance.  
This guide covers the most common scanning options and tips.

---

## 🚀 Basic Scanning

```bash
nmap <target>                # Default scan
nmap 192.168.1.1              # Single IP
nmap 192.168.1.1 192.168.1.2  # Multiple IPs
nmap 192.168.1.1-50           # IP range
nmap 192.168.1.0/24           # Subnet scan
```

## 🔍 Port Scanning

```bash
nmap -F <target>                 # Fast scan (top 1000 ports)
nmap -p 21,22,80,443 <target>    # Specific ports
nmap -p 1-65535 <target>         # All ports
nmap --top-ports 100 <target>    # Top 100 ports
```

## 🛠 Service & Version Detection

 ```bash
nmap -sV <target>                # Detect service versions
nmap -sV --version-intensity 9 <target>  # More accurate
```

## 🧠 OS Detection

```bash
nmap -O <target>                 # OS detection
sudo nmap -A <target>            # Aggressive: OS + version + scripts + traceroute
```

## 🦠 Vulnerability Scripts

```bash
nmap --script vuln <target>
nmap --script http-enum <target>
nmap --script ftp-anon <target>
nmap --script smb-vuln-ms17-010 <target>
```

## 🎯 Scan Techniques

```bash
nmap -sS <target>    # SYN scan (stealth)
nmap -sT <target>    # TCP connect scan
nmap -sU <target>    # UDP scan
nmap -sA <target>    # ACK scan
nmap -sW <target>    # Window scan
nmap -sM <target>    # Maimon scan
```

## 🕵️ Bypass Firewalls & IDS

```bash
nmap -f <target>             # Fragment packets
nmap --data-length 25 <target> # Add random payload length
nmap --source-port 53 <target> # Spoof source port
nmap -D RND:10 <target>        # Decoy scan
```

## 📁 Output Formats

```bash
nmap -oN output.txt <target>    # Normal text file
nmap -oG output.gnmap <target>  # Grepable
nmap -oX output.xml <target>    # XML
nmap -oA allformats <target>    # All formats
```

## ⚡ Performance & Optimization

```bash
nmap -T4 <target>       # Faster scan
nmap -T5 <target>       # Very aggressive scan (may miss hosts)
nmap --min-rate 1000 <target>  # Send packets faster
```

## 📌 Common Useful One-Liners

```bash
nmap -sC -sV <target>         # Default scripts + version
nmap -p- --open -sS -T4 <target>  # Full TCP scan, only open ports
nmap -Pn -A <target>          # Treat host as alive, aggressive scan
```

Lucifer’s Tip 🕶️: Nmap is only as good as your options. Learn how to chain flags for stealth, speed, and detail.
