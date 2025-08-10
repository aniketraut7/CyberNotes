# 🛡️ OWASP Top 10 – Web Application Security Risks (2021)

The **OWASP Top 10** is a globally recognized list of the most critical security risks to web applications, compiled by the [Open Web Application Security Project](https://owasp.org/).  
It serves as an **awareness document** for developers, security teams, and organizations.

---

## **1. Broken Access Control**
**Description:** Flaws in enforcing what authenticated users are allowed to do.  
**Examples:**
- Viewing or modifying another user's data by changing a URL parameter.
- Bypassing role-based access restrictions.
**Impact:** Data breaches, privilege escalation.
**Mitigation:**
- Enforce server-side access checks.
- Use Role-Based Access Control (RBAC).
- Deny access by default.

---

## **2. Cryptographic Failures** (formerly Sensitive Data Exposure)
**Description:** Failures related to data encryption, both at rest and in transit.  
**Examples:**
- Storing passwords in plaintext.
- Using outdated encryption like MD5 or SHA1.
**Impact:** Data theft, credential leaks.
**Mitigation:**
- Use strong encryption (AES-256, TLS 1.2+).
- Use proper key management.
- Hash passwords with `bcrypt`, `scrypt`, or `Argon2`.

---

## **3. Injection**
**Description:** Unsanitized input is interpreted as code.  
**Examples:**
- SQL Injection: `id=1 OR 1=1`
- Command Injection: `; rm -rf /`
**Impact:** Data manipulation, server compromise.
**Mitigation:**
- Use parameterized queries.
- Sanitize and validate input.
- Use ORM frameworks.

---

## **4. Insecure Design**
**Description:** Security flaws built into the design of an application.  
**Examples:**
- No rate limiting on login forms.
- Missing threat modeling during development.
**Impact:** Easy exploitation of systemic flaws.
**Mitigation:**
- Use secure design patterns.
- Conduct threat modeling sessions.
- Include security in early development phases.

---

## **5. Security Misconfiguration**
**Description:** Insecure default settings or improper configurations.  
**Examples:**
- Default admin credentials.
- Unnecessary services enabled.
**Impact:** Increased attack surface.
**Mitigation:**
- Harden systems based on benchmarks (CIS, NIST).
- Disable unnecessary features.
- Regular configuration audits.

---

## **6. Vulnerable and Outdated Components**
**Description:** Using outdated software components with known vulnerabilities.  
**Examples:**
- Old CMS versions.
- Outdated JS libraries.
**Impact:** Exploitation of known CVEs.
**Mitigation:**
- Maintain an inventory of components.
- Apply updates promptly.
- Use vulnerability scanners.

---

## **7. Identification & Authentication Failures**
**Description:** Flaws in authentication mechanisms.  
**Examples:**
- Weak passwords allowed.
- No multi-factor authentication.
**Impact:** Account takeover.
**Mitigation:**
- Enforce MFA.
- Secure password reset processes.
- Implement secure session handling.

---

## **8. Software & Data Integrity Failures**
**Description:** Integrity of software updates and data is not verified.  
**Examples:**
- Downloading unsigned software updates.
- Using plugins from untrusted sources.
**Impact:** Supply chain attacks.
**Mitigation:**
- Use digital signatures.
- Verify integrity before deployment.

---

## **9. Security Logging & Monitoring Failures**
**Description:** Insufficient logging and alerting of security events.  
**Examples:**
- No logs for failed login attempts.
- Logs not monitored in real time.
**Impact:** Delayed breach detection.
**Mitigation:**
- Enable centralized logging.
- Set up SIEM alerts.
- Define an incident response plan.

---

## **10. Server-Side Request Forgery (SSRF)**
**Description:** The server makes requests to unintended locations.  
**Examples:**
- Fetching AWS instance metadata from internal IPs.
**Impact:** Internal network compromise.
**Mitigation:**
- Validate URLs and restrict protocols.
- Block access to internal IP ranges.
- Use allowlists.

---

## 📌 OWASP Top 10 Visual Summary

| Risk ID | Risk Name | Example Vulnerability | Typical Impact |
|---------|-----------|----------------------|----------------|
| A01     | Broken Access Control | IDOR | Unauthorized data access |
| A02     | Cryptographic Failures | Plaintext passwords | Data theft |
| A03     | Injection | SQL Injection | Database compromise |
| A04     | Insecure Design | Missing rate limiting | Account brute-force |
| A05     | Security Misconfiguration | Default creds | System takeover |
| A06     | Vulnerable Components | Old WordPress | CVE exploitation |
| A07     | Auth Failures | No MFA | Account takeover |
| A08     | Integrity Failures | Unverified updates | Supply chain attack |
| A09     | Logging Failures | No alerts | Delayed detection |
| A10     | SSRF | Internal API access | Internal compromise |

---

### **Lucifer’s Tip 🕶️**: Don’t just memorize the OWASP Top 10 — actively test these in labs like [PortSwigger Web Security Academy](https://portswigger.net/web-security) or [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/) to get real skills.
