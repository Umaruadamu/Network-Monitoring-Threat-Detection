# Enterprise Network Layer Monitoring & Threat Detection Case Study  
## DNS Service Disruption – Log-Based Incident Analysis

---

# Executive Summary

This case study presents a structured network-layer analysis of a DNS service disruption identified through packet capture inspection using tcpdump.

The investigation demonstrates enterprise-level capability in:

- Network-layer protocol analysis  
- Log interpretation and anomaly identification  
- Threat hypothesis development  
- Incident classification  
- Risk-based remediation planning  

The incident involved repeated DNS resolution failures caused by ICMP “Destination Port Unreachable” responses referencing UDP port 53.

---

# Incident Overview

Time Detected: 13:24 (24-hour format)  
User Impact: Customers unable to resolve domain name  
Symptom: “Destination port unreachable” error  
Affected Service: DNS resolution  

The issue disrupted domain resolution, preventing access to the organisation’s public-facing web service.

---

# Technical Analysis

## Protocol Flow Observed

Captured traffic revealed the following communication sequence:

1. Client → DNS Server  
   - Protocol: UDP  
   - Port: 53  
   - Purpose: DNS A-record query  

2. DNS Server → Client  
   - Protocol: ICMP  
   - Message: "Destination Port Unreachable (udp port 53 unreachable)"

---

## Log Interpretation

Key indicators identified in tcpdump logs:

- UDP packets transmitted to DNS server IP
- ICMP Type 3 (Destination Unreachable)
- Code 3 (Port Unreachable)
- Repeated failed DNS resolution attempts
- DNS query flags including A-record request

The presence of ICMP Port Unreachable responses confirms:

- The DNS service process was not listening on port 53  
  OR  
- Traffic to port 53 was being actively blocked  

---

# Network-Layer Diagnostic Interpretation

From a network-layer perspective, this incident represents a failure at one of three possible control points:

1. Application-layer failure (DNS daemon not running)
2. Network-layer filtering (Firewall blocking UDP/53)
3. Service exhaustion (e.g., DoS condition causing service crash)

The repeated ICMP responses suggest deterministic blocking rather than packet loss.

---

# Threat Hypothesis Development

Based on observed behaviour, plausible root causes include:

### 1. Denial of Service (DoS) Attack
- Flooding of DNS service
- Resource exhaustion
- Service crash
- ICMP rejection due to unavailable service

### 2. Firewall Misconfiguration
- Newly enforced rule blocking inbound/outbound UDP 53
- Incorrect segmentation policy
- Change management failure

### 3. Service Misconfiguration
- DNS daemon stopped
- Incorrect binding configuration
- Service listening on alternate port

---

# Enterprise Risk Impact Assessment

## Confidentiality
Low immediate impact (resolution failure does not imply data compromise)

## Integrity
Low impact unless configuration tampering occurred

## Availability
High impact — DNS outage directly affects:

- Customer access
- Operational continuity
- Revenue
- Brand trust

In industrial or oil & gas environments, DNS failure may impact:

- Remote telemetry systems
- SCADA name resolution
- Internal control system dependencies

---

# Incident Response Methodology

## Phase 1 – Verification

- Confirm DNS service status (systemctl status / service check)
- Validate port listening (netstat / ss)
- Inspect firewall rules (iptables / ACL / security groups)
- Review recent configuration changes

---

## Phase 2 – Threat Evaluation

- Check for abnormal inbound traffic spikes
- Review logs for volumetric anomalies
- Inspect IDS/IPS alerts
- Correlate timestamps with system logs

---

## Phase 3 – Remediation

If firewall misconfiguration:
- Restore correct rule set
- Implement change control review

If DNS service failure:
- Restart service
- Investigate crash logs
- Patch vulnerabilities

If DoS suspected:
- Apply rate limiting
- Enable upstream filtering
- Activate DDoS mitigation provider

---

# Detection Engineering Enhancements

To prevent recurrence:

- Deploy alert for repeated ICMP Port Unreachable events
- Implement DNS health monitoring
- Baseline normal DNS query volume
- Create anomaly thresholds
- Integrate logs into SIEM correlation pipeline

Example detection logic (conceptual):

Repeated ICMP Type 3 Code 3 responses over threshold → Trigger Availability Alert

---

# Industrial & Critical Infrastructure Relevance

DNS failure in industrial environments can disrupt:

- Field sensor data aggregation
- Remote site connectivity
- Hybrid IT/OT coordination
- Centralised monitoring platforms

Proactive DNS monitoring is critical for:

- Operational continuity
- Production uptime
- Safety systems

---

# Senior-Level Competencies Demonstrated

- Deep protocol-level analysis (UDP, ICMP, DNS)
- Root cause hypothesis modelling
- Availability risk assessment
- Enterprise troubleshooting methodology
- Threat-informed investigation
- Detection engineering design
- Operational resilience thinking

---

# Strategic Reflection

This case demonstrates structured, network-layer investigative reasoning aligned with enterprise monitoring practices.

Rather than focusing solely on packet interpretation, the analysis integrates:

- Protocol semantics
- Infrastructure control points
- Risk evaluation
- Business impact assessment
- Preventative detection architecture

The approach reflects an enterprise-ready network monitoring mindset suitable for regulated and industrial environments.
