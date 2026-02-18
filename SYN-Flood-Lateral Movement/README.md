# Case Study 1: SYN Flood Attack – Network-Layer Analysis & Deep Learning Detection Framework

---

# Executive Summary

This case study examines a SYN flood attack causing web service disruption and demonstrates how traditional log-based detection can be enhanced using deep learning–based traffic classification.

The investigation integrates:

- TCP protocol analysis
- Resource exhaustion modelling
- Availability risk evaluation
- Deep learning feature engineering for traffic anomaly detection

---

# Incident Overview

Symptom:
- Website connection timeout errors
- Web server unresponsive

Observed Log Pattern:
- High volume of TCP SYN packets
- Incomplete three-way handshakes
- No corresponding ACK completion
- Elevated half-open connections

---

# Attack Mechanics

TCP handshake normally follows:

1. SYN →  
2. SYN-ACK ←  
3. ACK →

In a SYN flood attack:

- Attacker sends massive SYN requests
- Does not complete handshake
- Server reserves memory per request
- Connection table becomes exhausted

Result:
- Legitimate clients denied service
- Availability compromised

---

# Enterprise Impact

CIA Analysis:

Confidentiality: No direct impact  
Integrity: No direct data modification  
Availability: Severe impact  

In industrial environments, such attacks could disrupt:

- Remote telemetry dashboards
- Operational monitoring systems
- Production scheduling platforms

---

# Deep Learning Detection Extension

Traditional detection:
- Threshold-based SYN rate monitoring

Limitations:
- Static thresholds
- High false positives during peak load

Proposed Framework:

Input Features:
- SYN packet rate per IP
- SYN/ACK ratio
- Incomplete handshake percentage
- Connection duration distribution
- Source IP entropy
- Time-window burst variance

Model Architecture:
- LSTM for temporal sequence analysis
- CNN for traffic pattern feature extraction
- Hybrid model for classification

Output:
- Binary classification (Normal / SYN Flood)
- Risk confidence score

Advantages:
- Detects slow-rate distributed SYN floods
- Adapts to traffic seasonality
- Reduces alert fatigue

---

# Senior Competencies Demonstrated

- Protocol-level attack analysis
- Resource exhaustion modelling
- ML-based anomaly detection design
- Detection engineering enhancement
- Availability risk contextualisation
