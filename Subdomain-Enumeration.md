# 🌐 Subdomain Enumeration

Subdomain enumeration is the process of identifying valid subdomains for a given domain.  
It is a crucial step in reconnaissance to discover hidden services and potential attack surfaces.

---

## 🔍 Why Subdomain Enumeration Matters
- Reveals **additional attack surfaces** (e.g., `admin.example.com`)
- Helps discover **forgotten or unpatched apps**
- Identifies **staging, dev, or test environments**
- Aids in mapping the **infrastructure of the target**

---

## 🛠 Tools & Methods

### **1. Passive Enumeration**
These methods don’t directly interact with the target’s infrastructure, making them stealthier.

- **Amass**  
  ```bash
  amass enum -passive -d example.com
  ```
- **Subfinder**
  ```bash
  subfinder -d example.com -silent
  ```
- **crt.sh (Certificate Transparency Search)**
  ```bash
  Visit: https://crt.sh/?q=example.com
  ```
- **Assetfinder**
  ```bash
  assetfinder --subs-only example.com
  ```
- **SecurityTrails API**
  ```bash
  securitytrails --domain example.com
  ```
