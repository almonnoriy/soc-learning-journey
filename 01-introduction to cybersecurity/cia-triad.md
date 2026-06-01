# CIA Triad

## What it is
The CIA Triad is the core model that defines the three goals of information security. Every security decision — whether you're a SOC analyst, a pen tester, or a sysadmin — is ultimately protecting one or more of these three properties.

---

## 1. Confidentiality

**Definition:** Ensuring that information is only accessible to those who are authorized to see it.

**Simple analogy:** Your DM inbox. Only you and the recipient should read it — not a stranger in a café sniffing Wi-Fi.

**How it's protected:**
- Encryption (AES, TLS)
- Access control lists (ACLs)
- Multi-factor authentication (MFA)
- Role-based access control (RBAC)

**When it's violated:**
- A hacker intercepts unencrypted traffic (man-in-the-middle)
- A phishing attack steals login credentials
- An insider leaks customer data

**SOC relevance:** You'll monitor for unauthorized access alerts, failed logins, and unusual data exfiltration patterns.

---

## 2. Integrity

**Definition:** Ensuring that data is accurate, complete, and has not been tampered with — either in transit or at rest.

**Simple analogy:** Imagine sending ₦50,000 and the transfer shows ₦5,000 on arrival. That's an integrity failure.

**How it's protected:**
- Hashing (MD5, SHA-256) — verifies files haven't changed
- Digital signatures
- Version control and audit logs
- Input validation (stops SQL injection)

**When it's violated:**
- An attacker modifies a database record
- A file is corrupted during transfer
- SQL injection alters records in a banking system

**SOC relevance:** You'll look for unauthorized file changes, database anomalies, and alerts from file integrity monitoring (FIM) tools like Tripwire or OSSEC.

---

## 3. Availability

**Definition:** Ensuring that systems, services, and data are accessible to authorized users when they need them.

**Simple analogy:** You try to use your bank's app at 8am — it's down. That's an availability failure.

**How it's protected:**
- Redundancy and failover systems
- Load balancers
- Regular backups (3-2-1 rule)
- DDoS mitigation
- Patch management (prevents crashes)

**When it's violated:**
- A DDoS attack floods a server with traffic
- Ransomware encrypts files and locks users out
- A power outage takes down unprotected infrastructure

**SOC relevance:** You'll respond to uptime alerts, investigate DDoS incidents, and escalate ransomware events.

---

## How they interact

The three properties often create tension with each other:
- **High confidentiality** (lots of encryption, strict access) can reduce availability (slower systems, more friction).
- **High availability** (open, fast, always-on) can weaken confidentiality.
- Security professionals constantly balance this triangle based on the value and sensitivity of the asset.

---

## Real-world example (Nigerian fintech context)

Take a mobile banking app like Opay or Kuda:

| Property | What it protects | Attack scenario |
|---|---|---|
| Confidentiality | Your account balance, BVN, transaction history | Hacker intercepts API calls |
| Integrity | Transfer amounts, recipient details | Attacker modifies transaction data in transit |
| Availability | Access to your funds at any time | DDoS on the payment gateway |

---

## Key terms to know

- **Asset** — anything of value (data, system, people)
- **Threat** — something that could cause harm
- **Vulnerability** — a weakness that a threat can exploit
- **Risk** — likelihood × impact of a threat exploiting a vulnerability
- **Control** — a measure put in place to reduce risk

---

*Next topic: Authentication vs Authorization*
