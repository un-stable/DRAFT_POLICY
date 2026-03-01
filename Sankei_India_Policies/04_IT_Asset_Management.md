# IT ASSET MANAGEMENT

**Organization:** Sankei India (sankei-india.com)  
**Document ID:** SIP-AM-004  
**Version:** 1.0  
**Effective Date:** March 1, 2026  
**Review Date:** March 1, 2027  

---

## 1. PURPOSE

Define how IT assets (hardware, software, network devices, servers) are inventoried, managed, and secured throughout their lifecycle.

---

## 2. SCOPE

All IT assets including:
- 3 Dedicated Servers (App, File, Backup)
- Network devices (Sophos, managed switches)
- Endpoints and admin workstations
- Software and licenses used to support sankei-india.com

---

## 3. INVENTORY

- Maintain a centralized inventory (CMDB) of all IT assets.
- Inventory fields: Asset ID, Type, Owner, Location, OS, IP/MAC, Purchase Date, Warranty, EOL, Classification, Backup Location.
- Annual inventory audit and reconciliation.

---

## 4. OS & SOFTWARE SUPPORT

- Only vendor-supported OS versions may be used on production servers.
- Unsupported OS or software must have documented compensating controls and a remediation plan.
- Maintain a patch window and schedule for servers and network devices.

---

## 5. ASSET LIFECYCLE

- Procurement: Security requirements reviewed prior to purchase.
- Deployment: Hardening baseline applied (disable unused services, secure configurations).
- Maintenance: Patch management, anti-malware, asset tagging.
- Decommission: Secure wipe, asset disposal record.

---

## 6. RESPONSIBILITIES

- Asset Owner: Ensure proper use and classification.
- IT Operations: Update CMDB, apply patches, backup configuration.
- Security Operations: Monitor for unauthorized assets.

---

## 7. MONITORING & AUDIT

- Periodic scans for unregistered devices on the network.
- Quarterly patch compliance reports.
- Annual review of CMDB and EOL schedules.

---

## 8. BACKUP OF ASSET CONFIGURATIONS

- Backup configurations for network devices (Sophos, switches) stored in Server Closet backup location.
- Retain configuration backups for at least 1 year.

---

## 9. MOBILE & REMOTE DEVICES

- Enforce endpoint protection and encrypted storage.
- Remote devices must use VPN and MFA to access internal resources.

---

## 10. EXCEPTIONS

- Any deviation from this policy must be approved by CISO and documented with a risk acceptance form.

---

## 11. DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | March 1, 2026 | IT Department | Initial Release |

---

**End of Document**
