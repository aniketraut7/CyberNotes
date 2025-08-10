# 🛡️ OWASP Top 10 – Web Application Security Risks (2021)

The **OWASP Top 10** is the most widely recognized list of the most critical web application security risks, published by the [Open Web Application Security Project](https://owasp.org).  
This guide summarizes each risk, its impact, and common mitigation strategies.

---

## 1️⃣ **Broken Access Control**
- **Description:** Users can perform actions they shouldn’t (e.g., accessing another user's data).
- **Example:** Changing `user_id=123` to `user_id=124` in a URL to view another account.
- **Mitigation:**
  - Enforce proper role-based access control (RBAC).
  - Validate access on the server side.
  - Use deny-by-default permissions.

---

## 2️⃣ **Cryptographic Failures** (formerly *Sensitive Data Exposure*)
- **Description:** Sensitive data is exposed due to weak or no encryption.
- **Example:** Storing passwords in plaintext.
- **Mitigation:**
  - Use strong encryption (AES-256, TLS 1.2+).
  - Don’t store unnecessary sensitive data.
  - Use secure password hashing (`bcrypt`, `Argon2`).

---

## 3️⃣ **Injection**
- **Description:** Malicious input is interpreted as code or commands.
- **Example:** SQL Injection via `id=1 OR 1=1`.
- **Mitigation:**
  - Use prepared statements and parameterized queries.
  - Validate and sanitize input.
  - Use ORM frameworks where possible.

---

## 4️⃣ **Insecure Design**
- **Description:** Poor security controls are built into the application design.
- **Example:** No rate-limiting on login attempts.
- **Mitigation:**
  - Use threat modeling during design.
  - Apply secure design patterns.
  - Perform security reviews early in development.

---

## 5️⃣ **Security Misconfiguration**
- **Description:** Insecure default settings or incomplete configurations.
- **Example:** Default admin/admin credentials left unchanged.
- **Mitigation:**
  - Disable default accounts and features.
  - Apply hardening guides.
  - Automate configuration management.

---

## 6️⃣ **Vulnerable & Outdated Components**
- **Description:** Using outdated software with known vulnerabilities.
- **Example:** Running an old version of Apache with public exploits.
- **Mitigation:**
  - Regularly update dependencies.
  - Monitor CVE databases.
  - Use tools like `OWASP Dependency-Check`.

---

## 7️⃣ **Identification & Authentication Failures**
- **Description:** Weak authentication systems that allow account compromise.
- **Example:** No multi-factor authentication (MFA).
- **Mitigation:**
  - Use MFA wherever possible.
  - Lock accounts after failed login attempts.
  - Secure session management.

---

## 8️⃣ **Software & Data Integrity Failures**
- **Description:** Code or data integrity not verified.
- **Example:** Unverified software updates.
- **Mitigation:**
  - Use code signing.
  - Verify digital signatures of third-party libraries.
  - Enable integrity checks in CI/CD pipelines.

---

## 9️⃣ **Security Logging & Monitoring Failures**
- **Description:** Lack of detection and response capabilities.
- **Example:** No alerts for suspicious activity.
- **Mitigation:**
  - Implement centralized logging.
  - Monitor logs in real-time (SIEM).
  - Create incident response procedures.

---

## 🔟 **Server-Side Request Forgery (SSRF)**
- **Description:** The server fetches resources from untrusted input.
- **Example:** SSRF fetching internal AWS metadata.
- **Mitigation:**
  - Validate and whitelist URLs.
  - Disable unnecessary URL schemes.
  - Isolate server network permissions.

---

> **Lucifer’s Tip 🕶️**: The OWASP Top 10 is not just for reading — test these vulnerabilities in labs like [PortSwigger Web Security Academy](https://portswigger.net/web-security) and [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/).
