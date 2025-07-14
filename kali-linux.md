# Kali Linux Setup & Red Team Tools

This document outlines the installation and configuration of Kali Linux within the homelab for red team testing against the Active Directory environment.

---

## 1. VM Configuration

- RAM: 4 GB
- CPU: 2 cores
- Disk: 80 GB
- Network: VMnet8 (NAT)
- IP: `192.168.239.30`
- Gateway: `192.168.239.2`
- DNS: `192.168.239.10` (domain controller)

---

## 2. Installation & Customization

- Downloaded Kali Linux ISO from [official site](https://www.kali.org/get-kali/)
- Installed using graphical installer
- Custom hostname: `khavin-kali`
- User: `khavin`
- Partitioned disk with guided setup
- Installed default desktop environment (GNOME)

---

## 3. Tools Installed

- `crackmapexec`
- `enum4linux`
- `bloodhound`
- `neo4j`
- `SharpHound.ps1` (transferred manually)

---

## 4. Connectivity Verification

- Verified DNS resolution and ping to domain controller:
  - `ping 192.168.239.10`
- Successfully joined the homelab network
- Tested access to Windows Server shares
- Performed SMB enumeration from Kali Linux

---

## 5. Tools Tested

- `enum4linux` — Basic enumeration of domain information
- `crackmapexec` — SMB enumeration and login verification
- BloodHound + Neo4j — Launched GUI and uploaded `loot.zip`
- PowerShell Enumeration — Used `SharpHound.ps1` on Windows 10 to collect AD data

---

## 6. Next Steps

- Begin red team testing against Windows domain
- Document successful enumeration, privilege escalation, and attack paths
- Correlate findings with logs and monitor detection using blue team tools
