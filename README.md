# Homelab Documentation

Welcome to my personal cybersecurity and system administration homelab.

This project simulates a corporate enterprise network using virtualization, Windows Server, Active Directory, VPN, and offensive/defensive tooling. All work is documented for hands-on learning, skill development, and professional growth.

---

## Core Components

- **Hypervisor**: VMware Workstation (running on Windows host)
- **Host Machine**: MINISFORUM Intel i9-12900HK, 32GB RAM, 1TB SSD
- **Domain Controller**: Windows Server 2022 (AD, DNS, DHCP, GPO)
- **Clients**:
  - Windows 10 (domain-joined)
  - Kali Linux (Red Team)
  - Ubuntu Server (VPN & Utility server)
- **VPN**: WireGuard setup between Ubuntu, Kali, and Win10

---

## Goals

- Learn Windows Server, Active Directory, GPOs, and DHCP/DNS
- Build a red/blue team test environment
- Perform AD enumeration and attacks (BloodHound, CME)
- Defend with GPOs, logging, firewalls, and threat detection
- Stream content locally via Plex server
- Document the process to reinforce learning

---

## Documentation

- [Windows Server Setup](windows-server-setup.md)
- [Active Directory Setup](active-directory.md)
- [Windows 10 Client](windows-10-client.md)
- [Kali Linux Setup](kali-linux.md)
- [BloodHound & CME Enumeration](bloodhound.md)
- [WireGuard VPN Setup](vpn.md)
- [Ubuntu Server Utility](ubuntu-server.md)
- [Plex Media Server](plex.md)

---

## ✅ Progress Snapshot (as of [Insert Date])

- ✅ Domain `homelab.local` created and working
- ✅ Windows 10 client joined to domain
- ✅ Kali has working network access to DC
- ✅ CrackMapExec & BloodHound enumeration successful
- ✅ SharpHound executed on Win10; data captured
- ✅ Neo4j + BloodHound GUI working on Kali
- ✅ WireGuard VPN tested and working between VMs
- ⏳ Plex server installed, pending media uploads
- ⏳ GPO creation and blue team hardening next

---

## Notes

This homelab is a living environment for testing and learning. Future updates will include:
- Sysmon + Windows Event Forwarding
- SIEM integration (maybe Wazuh/Graylog/ELK)
- PowerShell & AD automation
- Custom CTFs and attack simulations

---

## About Me

Khavin Mahesh – aspiring cybersecurity professional focused on practical, real-world skills and ethical security testing. This lab is part of my hands-on journey into red/blue team operations.

