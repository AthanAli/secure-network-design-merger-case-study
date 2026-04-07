# 🛡️ Secure Network Design — Corporate Merger Case Study

> **WGU D482: Secure Network Design**  
> Author: Athanase Ali | M.S. Cybersecurity & Information Assurance, Western Governors University

---

## 📋 Project Overview

This project presents a comprehensive secure network design for two merging organizations — a global financial services firm (Company A) and a healthcare software provider (Company B). The engagement covers vulnerability analysis, network topology redesign, regulatory compliance alignment, and threat modeling across both organizations' converged infrastructure.

The merged network design prioritizes **Zero Trust Architecture**, **network segmentation**, and **dual-compliance** with PCI DSS and HIPAA, all within realistic budget constraints.

---

## 🏢 Company Profiles

| | Company A | Company B |
|---|---|---|
| **Industry** | Global Financial Services | Healthcare Software (SaaS for Medical Providers) |
| **Key Data** | Customer financial & payment data | Protected Health Information (PHI), payment data |
| **Core Challenge** | Legacy infrastructure, cloud adoption gaps | No dedicated cybersecurity staff, third-party dependency |
| **Compliance Requirements** | PCI DSS | HIPAA, PCI DSS |

---

## 🔍 Security & Infrastructure Problems Identified

### Company A
- **Insufficient Endpoint Security** — inadequate protection for customer financial data across global operations
- **Legacy Authentication Systems** — weak authentication posture vulnerable to credential-based attacks
- **Outdated Network Infrastructure** — end-of-life hardware limiting Zero Trust and cloud adoption
- **Limited Cloud Integration** — inability to leverage cloud for scalability and redundancy

### Company B
- **No Dedicated Cybersecurity Professional** — critical security gaps in specialized medical software
- **Third-Party Support Vulnerabilities** — third-party infrastructure providers not aligned with HIPAA/PCI DSS standards
- **Inadequate Data Encryption** — insufficient protection of credit card and PHI data in transit/at rest
- **Limited Scalability** — software architecture unable to scale with medical client growth

---

## ⚠️ Vulnerability Analysis

### Company A

| Vulnerability | Impact | Risk | Likelihood |
|---|---|---|---|
| Open ports 21–90, 3389 (FTP/RDP exposed) | Unauthorized access, data compromise | High | High |
| Organization-wide 8-character password policy | Brute-force susceptibility, account takeover | High | Moderate |

### Company B

| Vulnerability | Impact | Risk | Likelihood |
|---|---|---|---|
| MFA not enforced for all users | Unauthorized access via compromised credentials | High | High |
| PostgreSQL admin interface exposed to internet | Database exfiltration or manipulation | High | Low |

---

## 🖧 Merged Network Design

The proposed merged network topology implements:

- **Zero Trust Zone** — enforces identity verification, least-privilege access, and continuous monitoring for all users and devices
- **Network Segmentation** — Company A and Company B resources isolated into dedicated segments; payment processing systems separately delineated
- **Cloud-Hybrid Architecture** — Azure cloud integration for scalability and redundancy, with on-premises retention for legacy/sensitive workloads
- **OSI/TCP-IP Layered Security** — controls implemented at network, transport, and application layers

### Hardware Changes

| Component | Action | Rationale |
|---|---|---|
| Cisco 3750X Switches (×4) | Replaced → Cisco Catalyst 9300 Series | End-of-life; no manufacturer patches |
| Legacy firewall | Replaced → Fortinet FortiGate 100F NGFW | ZTNA, SD-WAN, SSL inspection, microsegmentation |
| Border router | Added → Cisco ASR 1000 Series | Unified access security, MFA support, SD-WAN |
| Windows Server 2012 + Windows XP/7 | Upgraded → Windows Server 2019 + Windows 11 Pro | Unsupported OS; critical patch gap |
| Meraki M28 APs, HPE JL262A switches, Sophos XG, HPE AP535 APs | Retained | Still manufacturer-supported; cost-effective |

---

## 🔐 Network Design Principles

### 1. Network Segmentation
Implemented via the **Fortinet FortiGate 100F NGFW** and **Cisco Catalyst 9300 Series switches**. The FortiGate delivers end-to-end secure networking with microsegmentation and SD-WAN capabilities, reducing attack surface and lateral movement risk. Cisco 9300 switches provide predictable, scalable segmentation at the access layer.

### 2. Zero Trust Architecture (ZTA)
The FortiGate 100F includes built-in universal ZTNA — automatically controlling, verifying, and limiting user access to validated applications only. The Cisco ASR 1000 Series router extends ZTA principles to WAN connections, enforcing MFA and role-based trust evaluation for all SD-WAN sessions.

---

## 📜 Regulatory Compliance

### PCI DSS
- Payment processing resources isolated in dedicated network segments
- TLS encryption enforced across Zero Trust Zone and cloud services
- Continuous monitoring and logging of payment-related network traffic
- Least-privilege access controls limiting cardholder data access to authorized personnel only

### HIPAA
- PHI isolated within Company B's dedicated network segment
- Encryption enforced for all PHI in transit and at rest
- Role-based authentication and authorization controls limit PHI access
- Full audit trail logging for all PHI access events

---

## 🚨 Threat Analysis — Post-Merger Risks

### Insider Threats
- **Risk:** Malicious or negligent employees, contractors, or partners with access to sensitive data in the Zero Trust Zone
- **Mitigations:** User Behavior Analytics (UBA), Role-Based Access Control (RBAC), insider threat awareness training, scalable log management

### Advanced Persistent Threats (APTs)
- **Risk:** Sophisticated long-term intrusion campaigns targeting the merged entity's expanded attack surface
- **Mitigations:** Behavioral analytics and anomaly detection, threat intelligence feeds, periodic penetration testing and red team exercises, continuous network performance monitoring

---

## 💰 Cost-Benefit Summary

| Infrastructure Model | Advantages | Costs |
|---|---|---|
| **On-Premises** | Immediate cost savings; suitable for legacy apps and sensitive data | Ongoing maintenance; dedicated security investment |
| **Cloud (Azure)** | Scalability, redundancy, shared security responsibility model, compliance tooling | Ongoing operational costs; requires disciplined resource management |

**Recommendation:** Hybrid approach — cloud for scalability and new workloads, on-premises retention for sensitive/legacy systems — balancing security, compliance, and budget.

---

## 🔗 Relevance to ICS/OT Security

The competencies demonstrated here — **network segmentation, Zero Trust implementation, vulnerability assessment, multi-vendor hardware lifecycle management, and dual-compliance architecture** — translate directly to OT/ICS environments where network segmentation (Purdue Model zones), vendor EOL management, and regulatory compliance (NERC CIP, IEC 62443) are foundational requirements.

---

## 🛠️ Skills Demonstrated

`Network Architecture` · `Zero Trust Architecture` · `Network Segmentation` · `Vulnerability Assessment` · `PCI DSS` · `HIPAA` · `Fortinet FortiGate` · `Cisco Catalyst` · `Cisco ASR` · `Threat Modeling` · `Insider Threat Analysis` · `APT Defense` · `Cloud-Hybrid Design` · `Cost-Benefit Analysis`

---

## 📚 References

- Fortinet FortiGate 100F Series Data Sheet — fortinet.com
- Cisco ASR 1000 Series Data Sheet — cisco.com
- Cisco Catalyst 9300 Series Data Sheet — cisco.com
- Landoll, D. (2021). *The Security Risk Assessment Handbook*. CRC Press.
- Lammle, T. (2022). *CompTIA Network+ Study Guide: Exam N10-008* (5th ed.). Sybex.
- Stewart, M. & Kinsey, D. (2021). *Network Security, Firewalls, and VPNs* (3rd ed.). Jones & Bartlett Learning.

---

## 📄 License

This project was completed as an academic assignment. Content is shared for portfolio purposes.
