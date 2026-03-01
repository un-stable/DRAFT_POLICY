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
- 3 Dedicated physical Servers (App, File, Backup) — no virtualization/VMs in use
- Network devices (Sophos firewall, Cisco managed switches)
- Endpoints and admin workstations (~90 PCs/endpoints)
- Active Directory domain controllers and service accounts
- Software and licenses used to support sankei-india.com

---

## 3. INVENTORY

- Maintain a centralized inventory (CMDB) of all IT assets; include AD computer objects and service accounts.
- Inventory fields: Asset ID, Type, Owner, Location, OS/Version, IP/MAC, AD Computer Name, Purchase Date, Warranty, EOL, Classification, Backup Location.
- Annual inventory audit and reconciliation.

---

## 4. OS & SOFTWARE SUPPORT

- Only vendor-supported OS versions may be used on production servers and endpoints. For AD domain controllers, maintain supported Windows Server versions.
- Unsupported OS or software must have documented compensating controls and a remediation plan.
- Maintain a patch window and schedule for servers and network devices.

---

## 5. ASSET LIFECYCLE

- Procurement: Security requirements reviewed prior to purchase (including Sophos licensing and Cisco hardware).
- Deployment: AD join for endpoints, baseline image with Sophos endpoint agent pre-installed, hardening baseline applied.
- Maintenance: Patch management for Windows endpoints and servers, Sophos agent updates, firmware updates for Cisco switches.
- Decommission: Secure wipe, AD computer account cleanup, asset disposal record.

---

## 6. RESPONSIBILITIES

- Asset Owner: Ensure proper use and classification.
- IT Operations: Update CMDB, apply patches, backup configuration.
- Security Operations: Monitor for unauthorized assets.

---

## 7. MONITORING & AUDIT

- Periodic scans for unregistered devices on the network; cross-check with AD computer objects and CMDB.
- Quarterly patch compliance reports for endpoints (~90) and servers.
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
