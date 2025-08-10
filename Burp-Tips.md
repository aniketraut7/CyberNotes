# 🐞 Burp Suite Tips & Tricks

**Burp Suite** is a leading web vulnerability scanner and penetration testing tool used to identify, exploit, and secure web applications.  
This cheatsheet contains tips, tricks, and workflow ideas for beginners and professionals.

---

## 🚀 Basic Setup

- **Install & Run:**
  - Download from [https://portswigger.net/burp](https://portswigger.net/burp)
  - Use **Burp Community** (free) or **Burp Pro** (paid)
- **Set Proxy:**
  - Go to `Proxy → Options → Add`
  - Default: `127.0.0.1:8080`
- **Browser Setup:**
  - Install **FoxyProxy** in Firefox/Chrome
  - Route traffic through Burp’s proxy

---

## 🛠 Core Features

- **Proxy** — Intercept, modify, and forward HTTP/S requests.
- **Target** — Map out application scope and structure.
- **Intruder** — Automate attacks like fuzzing, brute force, and payload testing.
- **Repeater** — Manually craft and resend requests.
- **Sequencer** — Analyze randomness in tokens.
- **Decoder** — Encode/decode data (Base64, URL, Hex).
- **Comparer** — Compare two responses.
- **Extender** — Install custom plugins/extensions.

---

## 🎯 Common Use Cases


1. Manual Testing Workflow
   - Proxy → Scope → Crawl → Scan → Analyze → Exploit
   
2. Authentication Testing
   - Capture login requests in Proxy
   - Test weak credentials with Intruder

3. Session Hijacking
   - Intercept session cookies
   - Replay in new requests via Repeater

4. Parameter Tampering
   - Modify GET/POST parameters and resend

5. Hidden Directory Discovery
   - Use Burp Intruder with a wordlist for directory brute-force

---

## 📌 Useful Extensions (BApp Store)

- Logger++ — Enhanced logging
- Active Scan++ — Additional scan checks
- Retire.js — Detect vulnerable JS libraries
- JSON Beautifier — Pretty-print JSON
- Authorize — Test for broken access control
- Param Miner — Discover hidden parameters

---

## ⚡ Pro Tips

- Always define the Target Scope to avoid scanning unnecessary hosts.

- Use Hotkeys:

    - Ctrl+Shift+R → Send to Repeater

    - Ctrl+Shift+I → Send to Intruder

- Combine Burp with external tools like ffuf, dirsearch, and nmap.

---

## 🧠 Advanced Usage

### Intruder Attack Types:

  - Sniper → One parameter at a time
  - Battering Ram → Same payload in all positions
   - Pitchfork → Multiple payload sets in parallel
   - Cluster Bomb → All combinations

### Automated Scanning:

   - Burp Pro:
       - Crawl + Audit mode
       - Generates detailed HTML reports
   - Filter by severity: High, Medium, Low, Info

### Macro & Session Handling:

  - Record login macros for authenticated scans
   - Auto-handle session timeouts

---

## 🛠 Example Burp Workflow for XSS Testing

1. Browse the target site with Burp Proxy on
2. Intercept input submission request
3. Send to Repeater
4. Inject payload:
   - <script>alert('XSS')</script>
5. Observe reflected script execution
6. Validate using manual and automated scans

---

## 📌 Quick Commands

- Save all project data:
  Project options → Save → Burp project file (.burp)

- Change User-Agent:
  Proxy → HTTP history → Right-click request → Change headers

---

  ### Lucifer’s Tip 🕶️: Master Burp’s manual testing before depending on automation — it makes you a true hacker, not just a button clicker.
