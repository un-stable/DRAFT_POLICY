# SOP — Incident Response (Shareable Sample)

Organization: Sankei India (sankei-india.com)
Document ID: SIP-IR-003-SAMPLE
Version: 1.0
Effective Date: March 1, 2026
Classification: Internal / Client Shareable

---

## 1. Purpose
Provide a concise, auditable procedure for detecting, triaging, containing, eradicating, recovering from, and documenting information security incidents affecting Sankei India systems.

---

## 2. Scope
Applies to incidents affecting on-premises infrastructure (3 dedicated servers: App, File, Backup), public web server (sankei-india.com), Active Directory domain, Cisco network, Sophos-managed endpoints (~90 PCs), and backup media in the Server Closet.

---

## 3. Definitions
- CSIRT: Computer Security Incident Response Team
- IOC: Indicator of Compromise
- AD: Active Directory
- MTTR: Mean Time to Recover

---

## 4. CSIRT Severity Matrix

| Severity | Impact / Scope | Examples (Sankei India) | SLA (Ack / Contain) |
|---|---:|---|---:|
| P1 — Critical | Company-wide outage or confirmed data breach | AD domain compromise; public web defacement; ransomware on production servers | 15 min / 30 min |
| P2 — High | Significant multi-user impact or targeted compromise | File server compromise; persistent malware on multiple endpoints | 1 hr / 2 hrs |
| P3 — Medium | Localized, limited business impact | Single endpoint infection; isolated phishing compromise | 4 hrs / 8 hrs |
| P4 — Low | Informational or low-risk | Auto-removed malware; routine suspicious scan | 24 hrs / 72 hrs |

Notes: Preserve evidence for P1/P2 (memory, images, logs). Use matrix to set Incident Tracker severity.

---

## 5. Reporting
- Any staff observing suspicious activity must immediately notify IT Operations (email/phone) and create an Incident Tracker entry.
- Provide: reporter name, timestamp, affected host(s), summary of activity, and user account(s) if known.
- CSIRT Commander coordinates external reporting (CERT‑In, customers, vendors) when required.

---

## 6. Response Phases (Checklist)

1) Detection & Initial Reporting
   - Review Sophos Central alerts, AD Security logs, IIS logs for web server, and switch logs.
   - Record initial IOC, affected assets (use CMDB/AD computer list), and estimate scope.

2) Triage & Assignment
   - Assign severity per CSIRT matrix; notify CSIRT members.
   - Collect volatile logs (Sophos telemetry, AD events) and secure evidence storage.

3) Containment
   - Endpoints: Use Sophos to isolate/quarantine affected endpoint(s).
   - Servers: Apply Sophos firewall blocks and/or disable relevant interface via Cisco switch port shutdown.
   - Accounts: Disable compromised AD accounts; force password resets; revoke sessions.

4) Eradication
   - Remove malware via Sophos remediation; apply patches; rebuild endpoint images if necessary.
   - Remove persistence mechanisms and close exploited vectors.

5) Recovery
   - Restore services from verified backups (Server Closet / folder-based backups) following AD System State restore procedures for domain issues.
   - Validate application and authentication functionality before returning to production.

6) Lessons Learned & Closure
   - Produce a final incident report (timeline, root cause, impact, remediation, owner actions).
   - Update detection rules, run targeted scans, and schedule retraining if needed.

---

## 7. Forensics & Evidence Handling
- Actions before reboot: collect memory image (if feasible), packet captures, and Sophos telemetry.
- Centralize logs and evidence in a secure evidence repository; maintain chain‑of‑custody records.
- For P1/P2 incidents consider external forensic vendor engagement.

---

## 8. Communications
- Internal: hourly updates for P1, every 4 hours for P2, daily for P3/P4.
- External: CSIRT Commander approves messages to customers, regulators, and vendors.
- Only authorized spokespeople communicate externally.

---

## 9. Roles & Responsibilities

| Role | Responsibility |
|---|---|
| CSIRT Commander (CISO / IT Head) | Lead incident response, approve external communications, escalate to MD |
| Technical Lead (Senior IT Admin) | Lead technical mitigation, forensics collection, coordinate Sophos support |
| IT Operations | Triage, containment actions (Sophos, Cisco), backup/restore operations |
| Communications Lead (HR/Admin) | Internal/external messaging and stakeholder notifications |
| Backup Admin | Verify backup integrity and execute restores (Server Closet) |

---

## 10. Timelines & SLAs
- P1: Acknowledge within 15 minutes; containment actions within 30 minutes.
- P2: Acknowledge within 1 hour; containment within 2 hours.
- P3: Acknowledge within 4 hours; containment within 8 hours.
- P4: Acknowledge within 24 hours; containment within 72 hours.

---

## 11. Testing & Exercises
- Tabletop exercises: semi‑annual (include AD compromise, public web defacement, ransomware scenarios).
- Restore tests: quarterly for public web server and AD System State; document MTTR.

---

## 12. Recordkeeping & Metrics
- Retain incident records and evidence for a minimum of 3 years.
- Track KPIs: MTTD, MTTC, MTTR, number of incidents by severity.

---

## 13. Attachments / Evidence Checklist (for auditor)
- Sophos Central alert exports and remediation logs
- AD Security/Event log extracts (domain controllers)
- IIS/web server logs and access logs for sankei-india.com
- Switch port logs and configuration backups (Cisco)
- Backup job logs and recent restore test reports
- Incident Tracker export and final incident report

---

## 14. Contacts (Placeholders)
- CSIRT Commander: [Name] / [phone] / [email]
- Technical Lead: [Name] / [phone] / [email]
- Sophos Support: [Contract number] / support@sophos.com
- ISP (Fiber): [Provider] / [SLA contact]
- ISP (RF): [Provider] / [SLA contact]

---

## 15. Document Control
- Version: 1.0  |  Date: March 1, 2026  |  Author: IT Department

---

**End of Document**
