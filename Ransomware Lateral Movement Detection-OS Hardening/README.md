# Ransomware Lateral Movement Detection via Network Behaviour Profiling  
## Graph & Sequence-Based Deep Learning Framework

---

# Executive Overview

This case study models ransomware propagation behaviour across enterprise networks using graph-based and temporal deep learning techniques.

The goal is early detection before full encryption impact.

---

# Threat Scenario

Post-execution ransomware typically:

- Enumerates network shares
- Initiates SMB connections
- Attempts credential reuse
- Spreads laterally
- Encrypts data

---

# Network Indicators

- Increased TCP connections on port 445
- Spike in failed authentication attempts
- Elevated file modification rates
- Internal subnet traversal velocity
- Outbound encrypted traffic anomalies

---

# Detection Architecture

## Feature Engineering

- SMB session density
- Host-to-host connection graph
- Authentication anomaly rate
- Packet entropy metrics
- Sequential propagation patterns

---

## Model Design

- Graph Neural Network (GNN) for lateral movement modelling
- LSTM for behavioural sequence detection
- Multi-class classification (Benign / Worm-like / Ransomware)

---

# Enterprise Impact

Prevents:

- Large-scale file encryption
- Operational downtime
- Regulatory breach
- Business continuity disruption

---

# Industrial Relevance

Critical for:

- OT segmentation protection
- SCADA workstation security
- Engineering system integrity
- Production continuity assurance

---

# Senior-Level Competencies Demonstrated

- East-west traffic analysis
- Graph-based anomaly modelling
- Ransomware behavioural classification
- Detection engineering architecture
- Industrial cybersecurity awareness
