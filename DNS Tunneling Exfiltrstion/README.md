# Case Study 3: DNS Tunneling & Command-and-Control Detection via Deep Learning

---

# Executive Summary

This case study examines covert data exfiltration using DNS tunneling and proposes a deep learning–based detection model for identifying anomalous DNS behaviour.

---

# Incident Overview

Observed Behaviour:

- High-frequency DNS queries
- Unusually long subdomain strings
- Encoded payload-like patterns
- Consistent communication to a single external resolver

Suspicion:
DNS-based command-and-control (C2) or data exfiltration.

---

# Attack Mechanics

DNS tunneling exploits:

- Outbound DNS allowed by firewall
- Encodes data into subdomain fields
- Uses TXT or A record queries

Traditional detection weaknesses:
- DNS seen as benign traffic
- Low bandwidth per request
- Difficult signature detection

---

# Feature Engineering for Detection

Extracted Features:

- Subdomain length distribution
- Shannon entropy of query strings
- Query frequency per host
- NXDOMAIN response ratio
- Unique domain generation rate

---

# Model Architecture

CNN:
- Pattern recognition in encoded query strings

LSTM:
- Temporal sequence anomaly detection

Autoencoder:
- Unsupervised anomaly detection baseline

Output:
- Probability of DNS tunneling
- Host risk score

---

# Enterprise Impact

Confidentiality: High (data exfiltration)  
Integrity: Minimal  
Availability: Minimal  

In industrial context:
- Intellectual property leakage
- Remote operational configuration exposure
- Mapping of internal network architecture

---

# Senior Competencies Demonstrated

- Covert channel analysis
- DNS behavioural modelling
- Feature entropy modelling
- Advanced anomaly detection architecture
- Detection engineering refinement
