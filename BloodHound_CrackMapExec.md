# BloodHound and CrackMapExec Enumeration

This document covers the enumeration steps performed using CrackMapExec (CME) and BloodHound in a homelab environment. The goal was to enumerate Active Directory objects and potential attack paths on the `homelab.local` domain.

---

## 1. Tools Used

- **CrackMapExec**: A post-exploitation tool for enumerating information from Active Directory environments.
- **BloodHound**: A tool that uses graph theory to reveal hidden relationships and attack paths in Active Directory.
- **Neo4j**: The database backend used by BloodHound to store and query relationship data.

---

## 2. Setup Environment

- **Attacker Machine**: Kali Linux
- **Target Machine**: Windows Server 2022 (Domain Controller)
- **Domain**: `homelab.local`
- **Domain Controller IP**: `192.168.239.10`
- **Test User**: `tuser@homelab.local` with password `Password123!`

---

## 3. CrackMapExec Enumeration

Performed initial enumeration:

```bash
crackmapexec smb 192.168.239.10
```

Checked credentials:

```bash
crackmapexec smb 192.168.239.10 -u tuser -p Password123!
```

Enumerated:

- Logged on users:

```bash
crackmapexec smb 192.168.239.10 -u tuser -p Password123! --loggedon-users
```

- Shares:

```bash
crackmapexec smb 192.168.239.10 -u tuser -p Password123! --shares
```

- Groups:

```bash
crackmapexec smb 192.168.239.10 -u tuser -p Password123! --groups
```

- LAPS policies:

```bash
crackmapexec smb 192.168.239.10 -u tuser -p Password123! --laps
```

---

## 4. BloodHound Setup

### SharpHound Execution

On the Windows 10 client:

```powershell
Set-Location "C:\SharpHound"
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
. .\SharpHound.ps1
Invoke-BloodHound -CollectionMethod All -ZipFileName loot.zip
```

### File Transfer to Kali

Transferred `loot.zip` to Kali via shared folders or SCP.

---

## 5. BloodHound GUI

- Started Neo4j browser at `http://localhost:7474`
- Launched BloodHound on Kali
- Logged in with default credentials: `neo4j` / `neo4j` (changed on first login)
- Uploaded `loot.zip`
- Visualized attack paths and domain relationships

---

## 6. Next Steps

- Explore domain relationships and potential privilege escalation paths
- Add detection and alerting on enumeration behavior
- Begin testing privilege escalation techniques
