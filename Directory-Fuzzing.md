# 📂 Directory & File Fuzzing

Directory fuzzing is the process of brute-forcing hidden directories and files on a web server.  
It helps in discovering **admin panels, configuration files, backups**, and other sensitive resources that developers may have left accessible.

---

## 🔍 Why Directory Fuzzing Matters
- Reveals **hidden admin areas** (`/admin`, `/dashboard`)
- Finds **configuration leaks** (`config.php`, `.env`, `.git/`)
- Locates **backup files** (`backup.zip`, `.bak`, `.old`)
- Identifies **unlinked content** that attackers can exploit
- Aids in **bug bounty hunting** and penetration testing

---

## 🛠 Popular Tools & Usage

### **1. Gobuster**
Fast and efficient directory brute-forcer.
```bash
gobuster dir -u https://example.com -w /path/to/wordlist.txt
```

- Add file extensions:
  gobuster dir -u https://example.com -w wordlist.txt -x php,txt,html

- Ignore 404s and handle redirects:
  gobuster dir -u https://example.com -w wordlist.txt -t 50 -x php,txt --wildcard
