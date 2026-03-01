# SOP - INCIDENT RESPONSE

**Organization:** Sankei India (sankei-india.com)  
**Document ID:** SIP-IR-003  
**Version:** 1.0  
**Effective Date:** March 1, 2026  
**Review Date:** March 1, 2027  

---

## 1. PURPOSE

Provide standardized steps to detect, assess, contain, eradicate, recover from, and document information security incidents affecting Sankei India systems.

---

## 2. SCOPE

Applies to all information security incidents affecting on-premises infrastructure (3 dedicated servers, Sophos perimeter), network connectivity (Fiber primary, RF secondary), web application, Active Directory compromises, and backups for sankei-india.com. Covers incidents involving ~90 endpoints protected by Sophos.

---

## 3. INCIDENT CLASSIFICATION & PRIORITY

Refer to CSIRT severity matrix in Security Organization Structure. Classify incidents as Critical (P1), High (P2), Medium (P3), Low (P4).

### CSIRT Severity Matrix

| Severity | Criteria (Impact / Scope) | Examples (Sankei India) | Response SLA (Ack / Contain) | Immediate Actions | Escalation / Notify |
|----------|---------------------------|--------------------------|-------------------------------|-------------------|---------------------|
| P1 — Critical | Major business outage, confirmed data breach, AD compromise affecting domain, public web defacement, ransomware encrypting production data | Public web offline, AD domain compromise, file server encrypted, company-wide outage (~affects many of ~90 endpoints or 3 servers) | Ack: 15 min / Contain: 30 min | Activate CSIRT, isolate affected hosts (Sophos isolate + switch-port shutdown), block malicious IPs on Sophos, disable compromised AD accounts, engage Management/Legal | MD + CSIRT Commander + External reporting as required (CERT-In, customers) |
| P2 — High | Significant degradation or targeted compromise with potential data loss, multi-user impact but limited to subset of systems | Targeted compromise of file server, persistent malware on multiple endpoints, suspected data exfiltration from web app | Ack: 1 hr / Contain: 2 hrs | Isolate affected endpoints, apply firewall blocks, collect logs (Sophos, AD, IIS), start forensic capture, schedule restore from backup if needed | CSIRT Commander, Technical Lead, Vendor Support (Sophos/ISP) |
| P3 — Medium | Localized incident with limited business impact; single system or user affected | Single endpoint infected, phishing causing credential exposure for one user, non-critical service disruption | Ack: 4 hrs / Contain: 8 hrs | Quarantine endpoint via Sophos, reset user credentials, review AD logs, remediate and monitor | IT Ops + Technical Lead |
| P4 — Low | Low-risk events or informational issues with no business impact | Malware detected and removed automatically, routine suspicious scan, low-severity policy violations | Ack: 24 hrs / Contain: 72 hrs | Log incident, apply standard remediation, update detection rules if needed | IT Ops |

Notes:
- For P1/P2 preserve evidence (memory/image if feasible), collect Sophos telemetry, AD Security logs, IIS logs, switch logs, and backup logs; document chain-of-custody.
- Map SLA times to real-world staffing and after-hours contact lists; maintain 24×7 on-call for P1.
- Use this matrix to drive incident severity field in Incident Tracker and automated alert rules in Sophos Central.
- Review and adjust severity assignments during post-incident review; update remediation tracker with owners/timelines.

---

## 4. REPORTING

- Any employee who detects a suspicious event must report immediately to IT operations via email/phone and log in the Incident Tracker.
- External reporting (CERT-In, customers, vendors) is coordinated by CSIRT Commander.

---

## 5. RESPONSE PHASES

1. Detection & Reporting
   - Monitor Sophos Central alerts (endpoint and firewall), AD logs (domain controllers), and server logs for indicators of compromise.
   - Create incident record with timestamp, reporter, affected systems, and whether AD accounts are involved.

2. Triage & Assessment (within response SLA)
   - Gather initial facts: affected hostnames/IPs (approx. 90 endpoints inventory), user accounts, services (public web server, file shares), scope (web app, file server, backup).
   - Check AD logs for suspicious logins, account lockouts, and privilege escalations.

3. Containment
   - Use Sophos to isolate infected endpoints remotely; block malicious IPs at Sophos firewall; if needed, disable affected AD accounts or force password reset.
   - For servers, isolate via switch port shutdown on Cisco managed switches or Sophos firewall rules.

4. Eradication
   - Run Sophos full scan and remediation on affected endpoints; remove malicious artifacts; rebuild endpoints where necessary.
   - Reset credentials for compromised AD accounts and review group memberships.

5. Recovery
   - Restore from verified backups (Server Closet or folder-based backups) using SOP-Backup-Recovery. Ensure AD System State restoration procedures are followed when AD is impacted.

6. Lessons Learned & Closure
   - Prepare final incident report including Sophos alert logs, AD forensic findings, restore timeline, and recommended mitigations.

---

## 6. FORENSICS & EVIDENCE HANDLING

- Preserve volatile data where feasible (memory, active network captures) prior to reboot.
- Collect log files from Sophos, servers, and switches; retain copies in a secure evidence store.
- Label evidence with chain-of-custody information.
- For severe incidents consider engaging external forensics vendor.
- Collect Sophos Central logs, AD Security/Event logs from domain controllers, IIS/web server logs for public web server, and backup logs.
- Preserve image of affected endpoints if possible; otherwise capture Sophos telemetry and event timelines.

---

## 7. COMMUNICATION

- Internal status updates: hourly for P1 incidents, every 4 hours for P2, daily for P3/P4.
- Management and external communications require CSIRT Commander approval.
- If customer data is affected, follow legal and contractual notification requirements.

---

## 8. ROLES & RESPONSIBILITIES

- Reporter: Notify IT, provide initial details, note if user account(s) are involved.
- IT Operations: Initial triage, AD check, Sophos isolation actions, containment.
- Technical Lead: Lead technical investigation and remediation, coordinate with Sophos support if needed.
- Communications Lead: Prepare messages and coordinate external notifications.
- CSIRT Commander: Approve actions, escalate to Management.

---

## 9. TIMELINES & SLAs

- Acknowledge reported incidents within 15 minutes for P1, 1 hour for P2, 4 hours for P3.
- Begin containment actions within 30 minutes for P1, 2 hours for P2.
- Provide initial incident summary to Management within 4 hours for P1.

---

## 10. TESTING & EXERCISES

- Conduct tabletop incident response exercises semi-annually.
- Run at least one full restore test for critical systems quarterly.

---

## 11. RECORDS & METRICS

- Retain incident records for minimum 3 years.
- KPIs: Mean Time to Detect (MTTD), Mean Time to Contain (MTTC), Mean Time to Recover (MTTR).

---

## 12. REFERENCES

- SIP-NET-006 Network Security Policy
- SIP-BR-005 SOP Backup & Recovery
- JAMA Cybersecurity Checklist

---

## 13. DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | March 1, 2026 | IT Department | Initial Release |

---

**End of Document**
