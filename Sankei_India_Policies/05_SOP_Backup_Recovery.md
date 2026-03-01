# SOP - BACKUP & RECOVERY

**Organization:** Sankei India (sankei-india.com)  
**Document ID:** SIP-BR-005  
**Version:** 1.0  
**Effective Date:** March 1, 2026  
**Review Date:** March 1, 2027  

---

## 1. PURPOSE

Define backup and recovery procedures for critical systems and data to ensure business continuity and protect against data loss, corruption, or ransomware.

---

## 2. SCOPE

Covers backups for the File Server, Web Application data, and configuration backups for servers and network devices. Applies to folder-based backups located at /sankei-india.com/Backup/user/sankei-india.com and physical backups in the Server Closet.

---

## 3. BACKUP STRATEGY

- Primary backups are taken on-site to the Backup Server.
- Secondary (offline/air-gapped) copies stored in Server Closet media.
- Retention: Daily backups for 30 days, weekly backups for 12 weeks, monthly backups for 12 months.
- Backup types: Full weekly, incremental daily.

---

## 4. RANSOMWARE PROTECTIONS

- Backups stored on devices not directly writable from user workstations.
- Apply immutability or WORM where supported for backup storage.
- Use separate credentials for backup management and monitor for unauthorized backup access.
- Regularly scan backups for malware prior to restore.

---

## 5. BACKUP SCHEDULE

| Data Type | Frequency | Retention | Storage Location |
|-----------|-----------|-----------|------------------|
| File Server Data | Daily (incremental), Weekly (full) | 30 days (daily), 12 weeks (weekly) | Backup Server + Server Closet |
| Web App Data | Hourly (incremental), Daily (full) | 7 days (hourly), 30 days (daily) | Backup Server |
| Server Configs | Weekly | 1 year | Backup Server + Server Closet |

---

## 6. RESTORATION PROCEDURE

1. Verify restoration request and obtain approval from IT Head.
2. Identify appropriate backup set and validate integrity (checksum, logs).
3. Perform restore on isolated test environment where feasible.
4. Validate data integrity and application functionality.
5. Schedule cutover and restore to production during maintenance window.
6. Document restore steps and update incident record if restoration is due to an incident.

---

## 7. TESTING

- Quarterly restore tests for critical systems.
- Record duration (MTTR) and issues discovered during tests.
- Update restoration procedures based on test outcomes.

---

## 8. ROLES & RESPONSIBILITIES

- IT Operations: Execute backups, validate logs, perform restores.
- Backup Administrator: Manage backup policies, credentials, and media.
- Security Operations: Monitor backup access and integrity.
- CISO: Approve backup retention and restoration for critical data.

---

## 9. LOGGING & MONITORING

- Backup jobs must log success/failure and alerts sent to IT operations.
- Weekly backup reports reviewed by IT Head.

---

## 10. RETENTION & DISPOSAL

- Securely dispose of backup media past retention period.
- Maintain disposal records in CMDB.

---

## 11. DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | March 1, 2026 | IT Department | Initial Release |

---

**End of Document**
