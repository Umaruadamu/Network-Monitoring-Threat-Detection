# Web Server Compromise via DNS/HTTP Abuse & Brute Force Exploitation  
## Multi-Stage Attack Analysis & Enterprise Hardening Strategy

---

# Executive Overview

This case study analyses a multi-stage cyberattack involving:

- Administrative brute force compromise
- Malicious web server modification
- HTTP-based malware delivery
- DNS redirection to attacker-controlled infrastructure

The investigation integrates protocol analysis, attack chain modelling, and strategic remediation design.

---

# Network Protocols Identified

Primary Protocol:
- HTTP (Application Layer)

Supporting Protocol:
- DNS (Domain Name System)

DNS was used to resolve both legitimate and malicious domains.
HTTP was used to deliver the malicious payload and perform redirection.

---

# Incident Summary

Observed Indicators:

- Users prompted to download a file
- Endpoint performance degradation
- Admin account lockout
- Redirection to malicious domain

Investigation revealed:

1. Successful brute force attack on admin account
2. Injection of malicious script into website
3. Delivery of malware via HTTP
4. DNS-based redirection to attacker infrastructure

---

# Attack Chain

1. Credential compromise (Brute Force)
2. Web server manipulation
3. Malicious file distribution
4. Client execution
5. Potential persistence & C2 communication

---

# Enterprise Risk Assessment

Confidentiality:
Possible endpoint compromise

Integrity:
Website content tampering

Availability:
Admin lockout disrupted operations

Reputational Risk:
High customer trust impact

---

# Recommended Security Measure

Adaptive Multi-Factor Authentication (MFA) with Behaviour-Based Login Monitoring

Enhancements include:

- Login rate limiting
- Account lockout thresholds
- Geo-location anomaly detection
- Device fingerprint validation
- AI-based authentication anomaly scoring

This moves beyond static brute force protection toward intelligent identity security.

---

# Senior-Level Competencies Demonstrated

- Application-layer protocol analysis
- Multi-stage attack modelling
- Identity security risk evaluation
- Web infrastructure compromise investigation
- Strategic remediation design
