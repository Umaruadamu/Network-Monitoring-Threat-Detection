# DNS Tunneling & Command-and-Control Detection  
## Entropy Modelling & Deep Learning-Based Anomaly Detection

---

# Executive Overview

This repository presents a deep learning framework for detecting covert data exfiltration and command-and-control communication via DNS tunneling.

DNS is commonly allowed outbound, making it an attractive covert channel.

---

# Threat Characteristics

Indicators of DNS abuse include:

- High query frequency
- Long encoded subdomains
- Elevated Shannon entropy
- High NXDOMAIN response rate
- Domain generation patterns

---

# Detection Framework

## Feature Engineering

- Subdomain length distribution
- Shannon entropy measurement
- Query burst analysis
- Unique domain frequency
- Temporal clustering patterns

---

## Model Architectures

- CNN for encoded string pattern recognition
- LSTM for periodic beacon detection
- Autoencoder for unsupervised anomaly modelling

---

# Enterprise Impact

Mitigates:

- Intellectual property exfiltration
- Persistent C2 communication
- Insider data theft
- Cloud workload compromise

---

# Industrial Relevance

Protects:

- Distributed field assets
- Engineering configuration data
- Remote operational infrastructure

---

# Senior-Level Competencies Demonstrated

- Covert channel analysis
- Entropy-based feature engineering
- AI-driven anomaly detection
- Detection-to-SIEM translation
- Advanced network threat modelling
