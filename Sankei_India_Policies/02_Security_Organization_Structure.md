# SECURITY ORGANIZATION STRUCTURE

**Organization:** Sankei India (sankei-india.com)  
**Document ID:** SIP-SOS-002  
**Version:** 1.0  
**Effective Date:** March 1, 2026  
**Review Date:** March 1, 2027  
**Classification:** Internal Use Only

---

## 1. PURPOSE

This document defines the organizational structure for information security at Sankei India, including roles, responsibilities, and reporting lines for both normal operations and incident/accident response scenarios. This structure aligns with JAMA Cybersecurity Guidelines requirements.

---

## 2. SCOPE

This document covers:
- Information security governance structure
- Roles and responsibilities of security personnel
- CSIRT (Computer Security Incident Response Team) structure
- Communication channels and escalation paths
- Coordination with external organizations

---

## 3. ORGANIZATIONAL CHART - NORMAL OPERATIONS

```
┌─────────────────────────────────────────────────────────────────┐
│                     MANAGING DIRECTOR                           │
│              (Ultimate Security Accountability)                 │
└─────────────────────────┬───────────────────────────────────────┘
                          │
┌─────────────────────────▼───────────────────────────────────────┐
│                    CISO / IT HEAD                               │
│         (Chief Information Security Officer)                    │
│    • Oversees information security strategy                     │
│    • Reports to Managing Director                               │
│    • Chairs Security Committee                                  │
└─────────────────────────┬───────────────────────────────────────┘
                          │
        ┌─────────────────┼─────────────────┐
        │                 │                 │
        ▼                 ▼                 ▼
┌───────────────┐ ┌───────────────┐ ┌───────────────┐
│ IT Operations │ │ Security      │ │ Compliance &  │
│ Team          │ │ Operations    │ │ Audit         │
├───────────────┤ ├───────────────┤ ├───────────────┤
│• Server Admin │ │• Monitoring   │ │• Policy Review│
│• Network Admin│ │• Access Mgmt  │ │• Audit Support│
│• Helpdesk     │ │• Patch Mgmt   │ │• Training     │
│• Sophos Admin │ │• Backup Ops   │ │• Documentation│
└───────────────┘ └───────────────┘ └───────────────┘
```

---

## 4. ROLES AND RESPONSIBILITIES

### 4.1 Managing Director

| Responsibility | Description |
|----------------|-------------|
| Strategic Oversight | Approve security strategy and major investments |
| Policy Approval | Final approval authority for security policies |
| Resource Allocation | Ensure adequate budget and staffing for security |
| Incident Escalation | Receive reports on critical security incidents |
| External Communication | Authorize external communications on major incidents |

### 4.2 CISO / IT Head

| Responsibility | Description |
|----------------|-------------|
| Security Program | Design, implement, and maintain security program |
| Risk Management | Conduct risk assessments and manage risk register |
| Policy Development | Develop and maintain security policies and procedures |
| Incident Management | Lead incident response activities |
| Compliance | Ensure compliance with JAMA and regulatory requirements |
| Vendor Management | Oversee security aspects of vendor relationships |
| Training | Ensure security awareness training is conducted |
| Reporting | Provide regular security reports to management |

### 4.3 IT Operations Team

| Responsibility | Description |
|----------------|-------------|
| Server Administration | Manage 3 dedicated physical servers (Application, File, Backup); no virtualization in use |
| Network Management | Maintain Sophos firewall, Cisco managed switches, fiber/RF connectivity, and DSL drop |
| System Maintenance | Patch management for Windows servers and endpoints, AD maintenance, system hardening |
| Backup Operations | Execute and verify folder-based backups for sankei-india.com, AD System State backups, and Server Closet media |
| User Support | Handle access requests and technical support for ~90 PCs/endpoints |

### 4.4 Security Operations

| Responsibility | Description |
|----------------|-------------|
| Monitoring | Monitor Sophos logs, network traffic, system alerts |
| Access Management | Manage user accounts, permissions, access reviews |
| Vulnerability Management | Conduct scans, track remediation |
| Incident Detection | Identify and escalate security events |

### 4.5 Compliance & Audit

| Responsibility | Description |
|----------------|-------------|
| Policy Management | Maintain policy documentation |
| Audit Support | Support internal and external audits |
| Training Coordination | Organize security awareness programs |
| Compliance Monitoring | Track compliance with JAMA and other standards |

---

## 5. SECURITY COMMITTEE

### 5.1 Composition

| Role | Member | Frequency |
|------|--------|-----------|
| Chair | CISO / IT Head | Monthly |
| Member | Operations Manager | Monthly |
| Member | HR Representative | Monthly |
| Member | Finance Representative | Monthly |
| Advisor | External Security Consultant | Quarterly |

### 5.2 Committee Responsibilities

- Review security posture and incidents monthly
- Approve security initiatives and projects
- Review policy changes and updates
- Conduct annual security strategy review
- Review JAMA self-assessment results

---

## 6. INCIDENT RESPONSE ORGANIZATION (CSIRT)

### 6.1 CSIRT Structure

```
┌─────────────────────────────────────────────────────────────────┐
│                   CSIRT COMMANDER                               │
│                   (CISO / IT Head)                              │
│    • Overall incident coordination                              │
│    • Decision authority                                         │
│    • External communication approval                            │
└─────────────────────────┬───────────────────────────────────────┘
                          │
    ┌─────────────────────┼─────────────────────┐
    │                     │                     │
    ▼                     ▼                     ▼
┌───────────────┐ ┌───────────────┐ ┌───────────────────┐
│ Technical     │ │ Communications│ │ Recovery &        │
│ Response      │ │ Team          │ │ Documentation     │
├───────────────┤ ├───────────────┤ ├───────────────────┤
│• Investigation│ │• Internal Comm│ │• System Recovery  │
│• Containment  │ │• External Comm│ │• Evidence Preserve│
│• Eradication  │ │• Vendor Coord │ │• Incident Logging │
│• Forensics    │ │• Customer Comm│ │• Report Writing   │
└───────────────┘ └───────────────┘ └───────────────────┘
```

### 6.2 CSIRT Roles

| Role | Primary | Backup | Contact |
|------|---------|--------|---------|
| CSIRT Commander | CISO/IT Head | Operations Manager | [Phone/Email] |
| Technical Lead | Senior IT Administrator (AD/Sophos lead) | Jr. IT Admin | [Phone/Email] |
| Communications Lead | HR/Admin Head | CISO/IT Head | [Phone/Email] |
| Recovery Lead | IT Operations (Backup Admin) | Vendor Support (Sophos/ISP) | [Phone/Email] |

### 6.3 Incident Severity Classification

| Severity | Description | Response Time | Escalation |
|----------|-------------|---------------|------------|
| **Critical (P1)** | Business operations stopped, data breach | Immediate (15 min) | MD + CSIRT |
| **High (P2)** | Major system compromised, potential breach | 1 hour | CSIRT |
| **Medium (P3)** | Limited impact, contained threat | 4 hours | IT Team |
| **Low (P4)** | Minor incident, no business impact | 24 hours | IT Team |

---

## 7. EXTERNAL ORGANIZATION COORDINATION

### 7.1 External Contacts

| Organization | Purpose | Contact Type | Review Frequency |
|--------------|---------|--------------|------------------|
| Sophos Support | Firewall/Security incidents | Support Contract | Annual |
| ISP - Fiber Provider | Network connectivity issues | SLA Agreement | Annual |
| ISP - RF Provider | Backup connectivity | SLA Agreement | Annual |
| Cyber Insurance | Incident claims | Policy | Annual |
| Legal Counsel | Data breach response | Retainer | As needed |
| CERT-In | Mandatory incident reporting | Government | As required |

### 7.2 Vendor Security Requirements

All external vendors with access to Sankei India systems must:
- Sign Non-Disclosure Agreement (NDA)
- Comply with security policies
- Undergo security assessment
- Provide incident notification within 24 hours

### 7.3 Contractual Review

| Agreement Type | Review Frequency | Last Review | Next Review |
|----------------|------------------|-------------|-------------|
| Sophos Support | Annual | N/A | March 2027 |
| ISP Agreements | Annual | N/A | March 2027 |
| Vendor NDAs | Annual | N/A | March 2027 |

---

## 8. COMMUNICATION FLOW

### 8.1 Normal Operations Reporting

```
Daily:   IT Team → IT Head (Status Report)
Weekly:  IT Head → Department Heads (Summary)
Monthly: Security Committee Meeting (All stakeholders)
Quarterly: IT Head → Managing Director (Executive Report)
Annually: JAMA Self-Assessment Review
```

### 8.2 Incident Communication

```
Detection → IT Team (Immediate)
     ↓
Assessment → CSIRT Commander (Within severity timeline)
     ↓
Containment → Technical Team + Communications (Parallel)
     ↓
Resolution → All stakeholders (Status updates)
     ↓
Closure → Management + Documentation (Final report)
```

---

## 9. REVIEW AND UPDATES

### 9.1 Review Schedule

| Review Type | Frequency | Responsible |
|-------------|-----------|-------------|
| Organizational Chart | Annual | CISO/IT Head |
| Role Assignments | Semi-Annual | HR + IT |
| Contact Information | Quarterly | IT Team |
| CSIRT Procedures | Annual | CSIRT Commander |

### 9.2 Triggers for Review

- Organizational changes
- Major security incidents
- Changes in business operations
- Regulatory updates
- Post-incident lessons learned

---

## 10. DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | March 1, 2026 | IT Department | Initial Release |

---

## 11. APPROVAL

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Managing Director | | | |
| CISO/IT Head | | | |

---

**End of Document**
