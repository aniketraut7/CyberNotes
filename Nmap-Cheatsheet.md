# 📍 Nmap Cheatsheet

**Nmap** (Network Mapper) is one of the most powerful and widely used tools for network reconnaissance.  
This guide covers the most common scanning options and tips.

---

## 🚀 Basic Scanning

```bash
nmap <target>
nmap 192.168.1.1
nmap 192.168.1.1 192.168.1.2
nmap 192.168.1.1-50
nmap 192.168.1.0/24

🔍 Port Scanning
nmap -F <target>               # Fast scan common 1000 ports
nmap -p 21,22,80,443 <target>  # Specific ports
nmap -p- <target>              # All ports
