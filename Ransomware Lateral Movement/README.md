# Case Study 2: Ransomware Lateral Movement – Network Behaviour Profiling & Classification

---

# Executive Summary

This case study investigates abnormal east-west traffic patterns indicative of ransomware propagation within an enterprise network.

The analysis integrates:

- Lateral movement detection
- SMB anomaly analysis
- Behavioural traffic profiling
- Deep learning–based ransomware classification

---

# Incident Overview

Observed Anomalies:

- Rapid SMB connection attempts across multiple hosts
- Increased file share enumeration
- Unusual authentication attempts
- Sharp increase in encrypted outbound traffic

Initial Hypothesis:
Ransomware attempting lateral propagation and data encryption.

---

# Network-Level Indicators

1. Spike in TCP connections to port 445
2. Increased failed authentication attempts
3. Large volume of small file writes
4. Outbound traffic entropy increase

---

# Behavioural Signature

Unlike volumetric DoS, ransomware propagation exhibits:

- Sequential scanning behaviour
- Privilege escalation attempts
- Targeted internal subnet traversal

Traffic characteristics:
- Structured but rapid host enumeration
- Burst authentication retries
- Encrypted payload transmission

---

# Deep Learning Integration

Feature Engineering:

- SMB session frequency
- Host-to-host connection graph density
- Authentication failure ratio
- Packet entropy metrics
- Internal subnet traversal speed

Model Design:

Graph Neural Network (GNN):
- Models host relationships
- Identifies abnormal connectivity clusters

LSTM:
- Detects sequential propagation behaviour

Classifier Output:
- Benign traffic
- Worm-like propagation
- Ransomware behavioural profile

---

# Enterprise Risk Impact

Confidentiality: Potential data exfiltration  
Integrity: File encryption  
Availability: Severe disruption  

In oil & gas:
- OT engineering stations could be affected
- Production operations could halt
- Safety system interfaces disrupted

---

# Senior Competencies Demonstrated

- Ransomware behavioural modelling
- East-west traffic analysis
- Graph-based anomaly detection
- ML-driven threat classification
- Industrial risk contextualisation
