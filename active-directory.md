# Active Directory Setup

This document outlines the setup of Active Directory on Windows Server 2022 and how Windows 10 was joined to the domain `homelab.local`.

---

## 1. Domain Promotion

- Installed the **Active Directory Domain Services (AD DS)** role via Server Manager  
- Created a **new forest**: `homelab.local`  
- Set the **DSRM password**  
- Configured DNS during promotion  
- Server was rebooted and renamed to: `dc1.homelab.local`

---

## 2. DNS Configuration

- Internal DNS set to `127.0.0.1` on the domain controller  
- Created a **Forward Lookup Zone** for `homelab.local`  
- Added an **A record** for `dc1` pointing to `192.168.239.10`

---

## 3. Organizational Units (OUs)

- Created OUs for:
  - `Computers`
  - `Users`
  - `Servers`

---

## 4. User Creation

- Created a test user: `tuser@homelab.local`  
- Password: `Password123!`  
- Added user to standard domain groups

---

## 5. Windows 10 Domain Join

- Configured Windows 10 VM with static IP and set DNS to `192.168.239.10`  
- Joined domain: `homelab.local`  
- Rebooted and logged in as `homelab\tuser`

---

## 6. Group Policy Setup

Used **Group Policy Management Console (GPMC)** to:

- Set **password complexity & expiration policies**  
- Enforce **Windows Defender** and **firewall settings**  
- Disable **local administrator** login via GPO

---

## 7. Tools Verified

- Active Directory Users and Computers (ADUC)  
- DNS Manager  
- Group Policy Management Console (GPMC)

---

## 8. Verification

Used these commands on the client to verify domain setup:

```cmd
echo %userdomain%
gpresult /r
ping dc1.homelab.local


