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

```bash
1. **Manual Testing Workflow**
   Proxy → Scope → Crawl → Scan → Analyze → Exploit
   
2. **Authentication Testing**
   Capture login requests in Proxy
   Test weak credentials with Intruder

3. **Session Hijacking**
   Intercept session cookies
   Replay in new requests via Repeater

4. **Parameter Tampering**
   Modify GET/POST parameters and resend

5. **Hidden Directory Discovery
   Use Burp Intruder with a wordlist for directory brute-force
