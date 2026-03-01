# NETWORK SECURITY POLICY

**Organization:** Sankei India (sankei-india.com)  
**Document ID:** SIP-NET-006  
**Version:** 1.0  
**Effective Date:** March 1, 2026  
**Review Date:** March 1, 2027  

---

## 1. PURPOSE

Define required network security controls to protect Sankei India's network architecture, ensure secure external connectivity, and maintain network resiliency.

---

## 2. SCOPE

Applies to all network components: Sophos firewall, managed switches, fiber primary link, RF secondary link, DSL drop, and all connected servers and endpoints.

---

## 3. NETWORK ARCHITECTURE

- Primary uplink: Fiber
- Secondary uplink: RF
- Edge security: Sophos border device
- Internal switching: Managed switches with VLAN segmentation
- External connectivity: DHCP-based with DSL drop as needed

---

## 4. PERIMETER SECURITY

- Sophos firewall must be configured with:
  - Deny-by-default rule base
  - Explicit allow rules for required services (web, management via restricted IPs)
  - IDS/IPS enabled
  - Geo-blocking where applicable
  - Regular signature updates
- Administrative access restricted to management VLAN and trusted admin IPs; MFA required.

---

## 5. NETWORK SEGMENTATION

- Separate VLANs for:
  - Servers (production)
  - Management
  - User workstations
  - Guest/IoT
  - Backup infrastructure
- Inter-VLAN traffic filtered via firewall policies.

---

## 6. DHCP & IP MANAGEMENT

- External DHCP used for internet-facing segments; internal network uses static IPs for servers and critical devices.
- Maintain IP address documentation in CMDB.
- DHCP leases audited monthly.

---

## 7. REMOTE ACCESS

- VPN access required for remote admin and remote workers with MFA.
- VPN admin accounts limited and logged.

---

## 8. DEVICE HARDENING

- Managed switches hardened: disable unused ports, enable port-security, BPDU Guard, and management ACLs.
- Change default credentials; apply latest firmware patches.
- Configuration backups stored in Server Closet backup location.

---

## 9. MONITORING & LOGGING

- Centralize logs from Sophos and network devices to a secure log server.
- Retain logs for a minimum of 90 days.
- Configure alerts for anomalous traffic, failed login attempts, and unusual bandwidth usage.

---

## 10. REDUNDANCY & FAILOVER

- Primary Fiber with RF as secondary uplink; configure routing to failover seamlessly.
- Document failover procedures and test failover at least annually.

---

## 11. SECURITY UPDATES

- Apply network device firmware updates within 30 days of release after testing.
- Emergency patches applied immediately following risk assessment.

---

## 12. VENDOR SUPPORT

- Maintain active Sophos support contract.
- Ensure SLAs for ISP providers (Fiber and RF) and test contactability.

---

## 13. INCIDENT RESPONSE

- Network-related incidents to follow SOP-Incident-Response.
- Network isolation and switch port actions must be logged and approved by CSIRT Commander.

---

## 14. TESTING

- Annual network security review and penetration test.
- Quarterly vulnerability scanning for network devices.

---

## 15. DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | March 1, 2026 | IT Department | Initial Release |

---

**End of Document**
