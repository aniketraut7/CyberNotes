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

### **2. Active Enumeration**
Actively probes the target infrastructure. May trigger IDS/IPS alerts.

- **Amass (active mode)**
  ```bash
  amass enum -active -d example.com
  ```
- **Gobuster DNS**
  ```bash
  gobuster dns -d example.com -w wordlist.txt
  ```
- **DNSRecon**
  ```bash
  dnsrecon -d example.com -t brt
  ```
- **Fierce**
  ```bash
  fierce --domain example.com
  ```
- **Knockpy**
```bash
knockpy example.com
```

### **3. Hybrid / Combined Enumeration**

1. Combines multiple methods to ensure maximum coverage.
  
 - subfinder -d example.com -silent > subs.txt
 - assetfinder --subs-only example.com >> subs.txt
 - amass enum -passive -d example.com >> subs.txt
 - sort -u subs.txt -o subs.txt

2. Validate results:
   
 - cat subs.txt | httpx -silent
---

### 📊 Automation Script Example
  ```bash
  #!/bin/bash

  domain=$1

  echo "[*] Enumerating subdomains for $domain..."

  subfinder -d $domain -silent > all_subs.txt

  assetfinder --subs-only $domain >> all_subs.txt

  amass enum -passive -d $domain >> all_subs.txt

  sort -u all_subs.txt -o all_subs.txt

  cat all_subs.txt | httpx -silent > live_subs.txt

  echo "[+] Live subdomains saved to live_subs.txt"
 ```

###  Run it:
 chmod +x enum.sh
 ./enum.sh example.com


### 📌 Tips & Best Practices

- Use multiple sources to avoid missing subdomains.

- Check for wildcard DNS using dig or nslookup.

- Use ASN enumeration to find IP ranges and map them to subdomains.

- Schedule periodic scans — domains change over time.

- For stealth: stick to passive methods in sensitive engagements.


### Lucifer Insight 💻🕶️: The best recon artist isn’t the loudest scanner — it’s the one who knows where to look when others don’t.
