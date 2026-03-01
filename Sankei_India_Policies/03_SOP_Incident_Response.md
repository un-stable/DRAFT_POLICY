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

Applies to all information security incidents affecting on-premises infrastructure (3 dedicated servers, Sophos perimeter), network connectivity (Fiber primary, RF secondary), web applications, and backups.

---

## 3. INCIDENT CLASSIFICATION & PRIORITY

Refer to CSIRT severity matrix in Security Organization Structure. Classify incidents as Critical (P1), High (P2), Medium (P3), Low (P4).

---

## 4. REPORTING

- Any employee who detects a suspicious event must report immediately to IT operations via email/phone and log in the Incident Tracker.
- External reporting (CERT-In, customers, vendors) is coordinated by CSIRT Commander.

---

## 5. RESPONSE PHASES

1. Detection & Reporting
   - Monitor Sophos alerts, server logs, and network devices.
   - Create incident record with timestamp, reporter, affected systems.

2. Triage & Assessment (within response SLA)
   - Gather initial facts: affected hostnames/IPs, user accounts, services, scope (web app, file server, backup).
   - Determine severity and assign CSIRT members.

3. Containment
   - Short-term: isolate affected host(s)/segment via Sophos or switch port shutdown.
   - Long-term: apply ACLs, block malicious IPs, disable compromised accounts.

4. Eradication
   - Remove malware, close exploited ports, apply patches, reset credentials.
   - Coordinate with Sophos Support for advanced remediation.

5. Recovery
   - Restore systems from verified backups (Server Closet backups or folder-based backups in /sankei-india.com/Backup/) following SOP-Backup-Recovery.
   - Validate application functionality and integrity.

6. Lessons Learned & Closure
   - Prepare final incident report, include timeline, root cause, actions taken, and remediation plan.
   - Update policies and run follow-up training if needed.

---

## 6. FORENSICS & EVIDENCE HANDLING

- Preserve volatile data where feasible (memory, active network captures) prior to reboot.
- Collect log files from Sophos, servers, and switches; retain copies in a secure evidence store.
- Label evidence with chain-of-custody information.
- For severe incidents consider engaging external forensics vendor.

---

## 7. COMMUNICATION

- Internal status updates: hourly for P1 incidents, every 4 hours for P2, daily for P3/P4.
- Management and external communications require CSIRT Commander approval.
- If customer data is affected, follow legal and contractual notification requirements.

---

## 8. ROLES & RESPONSIBILITIES

- Reporter: Notify IT, provide initial details.
- IT Operations: Initial triage, containment actions, log collection.
- Technical Lead: Lead technical investigation and remediation.
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
