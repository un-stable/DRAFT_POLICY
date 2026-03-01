# INFORMATION SECURITY POLICY

**Organization:** Sankei India (sankei-india.com)  
**Document ID:** SIP-ISP-001  
**Version:** 1.0  
**Effective Date:** March 1, 2026  
**Review Date:** March 1, 2027  
**Classification:** Internal Use Only

---

## 1. PURPOSE

This Information Security Policy establishes the framework for protecting Sankei India's information assets, ensuring confidentiality, integrity, and availability of data across all business operations. This policy aligns with JAMA (Japan Automobile Manufacturers Association) Cybersecurity Guidelines and industry best practices.

---

## 2. SCOPE

This policy applies to:
- All employees, contractors, and third-party personnel
- All information systems, networks, and data
- All physical and virtual infrastructure including:
  - 3 Dedicated physical Servers (Application, File Server, Backup) — no virtualization/VMs in use
  - Sophos Firewall/Border Security and Sophos Endpoint AV protecting ~90 endpoints
  - Cisco managed network switches
  - Active Directory (AD) domain for authentication and user/group management
  - Fiber (Primary) and RF (Secondary) connectivity
  - Web-based application hosted as 1 public web server (sankei-india.com)
  - No VDI environment in use

---

## 3. POLICY STATEMENT

### 3.1 Information Security Principles

Sankei India is committed to:
1. **Confidentiality** - Protecting sensitive information from unauthorized access
2. **Integrity** - Ensuring accuracy and completeness of information
3. **Availability** - Ensuring authorized users have access to information when needed

### 3.2 Compliance Standards

This organization maintains compliance with:
- JAMA Cybersecurity Checklist (Self-Assessment conducted annually)
- ISO 27001 Information Security Management principles
- Applicable data protection regulations

---

## 4. INFORMATION CLASSIFICATION

| Classification Level | Description | Handling Requirements |
|---------------------|-------------|----------------------|
| **Confidential** | Trade secrets, customer data, financial records | Encrypted storage, restricted access, no external sharing |
| **Internal** | Business processes, internal communications | Access limited to employees, secure transmission |
| **Public** | Marketing materials, public website content | No restrictions |

---

## 5. ROLES AND RESPONSIBILITIES

| Role | Responsibilities |
|------|------------------|
| **Management** | Approve policies, allocate resources, oversee security program |
| **CISO/IT Head** | Implement security controls, manage incidents, conduct risk assessments |
| **IT Department** | Maintain systems, apply patches, monitor security events |
| **All Employees** | Follow security policies, report incidents, complete training |

---

## 6. SECURITY CONTROLS

### 6.1 Network Security
- **Perimeter Security:** Sophos firewall at network border and Sophos AV for endpoint protection
- **Network Segmentation:** Cisco managed switches with VLAN configuration separating servers, management, endpoints, and guest networks
- **Connectivity:** Fiber (Primary) with RF backup for redundancy
- **External Connectivity:** DHCP-based with DSL drop configuration

### 6.2 Access Control
- Principle of least privilege for all system access
- Authentication via Active Directory for corporate systems; AD service accounts reviewed quarterly
- Strong password requirements (minimum 12 characters, complexity rules) and account lockout thresholds
- Multi-factor authentication for critical systems and administrative accounts (including Sophos and AD administrators)
- Regular access reviews (quarterly) and AD group membership audits

### 6.3 Data Protection
- Encryption for data at rest and in transit for sensitive data
- Regular backups with offline storage capability; AD System State backups performed and retained per backup policy
- Folder-based backup structure: /sankei-india.com/Backup/user/sankei-india.com

### 6.4 Endpoint Protection
- Sophos endpoint protection deployed to approximately 90 PCs/endpoints/systems; centralized management and alerting enabled
- Regular malware scans and real-time protection enabled via Sophos console
- Patch management program for endpoints and servers; endpoint patch status reviewed weekly

---

## 7. SECURITY ASSESSMENT

### 7.1 Self-Assessment Schedule

| Assessment Type | Frequency | Responsible Party |
|----------------|-----------|-------------------|
| JAMA Cybersecurity Checklist | Annual | CISO/IT Head |
| Internal Security Audit | Semi-Annual | IT Department |
| Vulnerability Assessment | Quarterly | IT Department |
| Risk Assessment | Annual | Management + IT |

### 7.2 JAMA Cybersecurity Checklist

The detailed JAMA self-assessment, item-by-item scoring, gap analysis, remediation tracker, and evidence index are maintained in the following subdocument:

> **📄 Subdocument: [01.1_JAMA_Cybersecurity_Checklist.md](01.1_JAMA_Cybersecurity_Checklist.md)**  
> **Document ID:** SIP-JAMA-01.1

### 7.3 Self-Assessment Status

- [ ] JAMA Cybersecurity Checklist completed (see SIP-JAMA-01.1)
- [ ] Gap analysis documented (see SIP-JAMA-01.1, Section 5)
- [ ] Remediation plan created (see SIP-JAMA-01.1, Section 5)
- [ ] Management review conducted

---

## 8. INCIDENT MANAGEMENT

All security incidents must be:
1. Reported immediately to IT Department
2. Documented in incident tracking system
3. Investigated within 24 hours
4. Escalated to management as per severity
5. Subject to post-incident review

Refer to: **SOP-Incident-Response (Document ID: SIP-IR-003)**

---

## 9. BUSINESS CONTINUITY

### 9.1 Critical Systems

| System | RPO | RTO | Backup Method |
|--------|-----|-----|---------------|
| Public Web Server (sankei-india.com) | 1 hour | 1 hour | Server-based backup + offsite copy (priority restore) |
| Web Application (App Server) | 4 hours | 2 hours | Server-based backup |
| File Server | 24 hours | 4 hours | Folder-based backup to Server Closet |
| Active Directory | 1 hour | 2 hours | AD System State + full server backup |
| Email/Communication | 4 hours | 1 hour | Cloud + local backup |

### 9.2 Alternative Operations
- Secondary RF connectivity available for network failover
- Backup server in Server Closet for critical data restoration
- Manual procedures documented for system outages, including steps to restore AD authentication and public web service

---

## 10. COMPLIANCE MONITORING

### 10.1 Review Schedule

| Activity | Frequency | Last Review | Next Review |
|----------|-----------|-------------|-------------|
| Policy Review | Annual | N/A | March 2027 |
| Security Awareness Training | Annual | N/A | March 2027 |
| Access Rights Review | Quarterly | N/A | June 2026 |
| Backup Testing | Quarterly | N/A | June 2026 |

---

## 11. POLICY VIOLATIONS

Violations of this policy may result in:
- Verbal/written warning
- Suspension of system access
- Disciplinary action up to termination
- Legal action for severe violations

---

## 12. DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | March 1, 2026 | IT Department | Initial Release |

---

## 13. APPROVAL

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Managing Director | | | |
| CISO/IT Head | | | |
| HR Head | | | |

---

**End of Document**
