# AD-Enterprise-Lab

> A realistic Enterprise Active Directory lab fully automated with PowerShell for Windows administration, Active Directory security, and Windows offensive security training.

![Windows](https://img.shields.io/badge/Windows-Server%202022-blue)
![PowerShell](https://img.shields.io/badge/PowerShell-Automation-5391FE)
![Active Directory](https://img.shields.io/badge/Active%20Directory-Enterprise-success)
![Status](https://img.shields.io/badge/Status-In%20Development-orange)

---

# Overview

**AD-Enterprise-Lab** is a realistic Enterprise Active Directory environment built for cybersecurity professionals, penetration testers, students, and anyone interested in learning Active Directory from both administrative and offensive security perspectives.

The environment is deployed automatically using PowerShell scripts, enabling anyone to build a complete enterprise lab in just a few minutes. The lab simulates a real corporate infrastructure with multiple domain controllers, a child domain, Windows 11 workstations, organizational units (OUs), users, security groups, service accounts, SMB shares, and intentionally vulnerable attack scenarios.

Unlike many traditional Active Directory labs that rely on Kali Linux, this project focuses on Windows-native attack techniques, providing a more realistic representation of modern internal penetration testing and post-compromise operations.

The project is intended for educational purposes and authorized security testing only.

---

# Features

## Infrastructure

- Fully Automated PowerShell Deployment
- Enterprise Active Directory Forest
- Root Domain
- Child Domain
- Windows Server 2022
- Windows 11 Enterprise Workstations
- Enterprise Network Topology

## Active Directory

- Organizational Units (OUs)
- Users
- Security Groups
- Service Accounts
- SPNs
- SMB Shares
- Kerberos Authentication
- Group Policy Objects (GPO)

## Offensive Security

- Active Directory Enumeration
- LDAP Enumeration
- SMB Enumeration
- PowerView
- SharpHound
- BloodHound
- Rubeus
- Password Spraying
- Kerberoasting
- AS-REP Roasting
- Privilege Escalation
- Lateral Movement

---

# Lab Topology

```text
                               Enterprise Forest
                               cyber.local
                                    │
        ┌───────────────────────────┴───────────────────────────┐
        │                                                       │
        │                                                       │
 Root Domain                                            Child Domain
 cyber.local                                           dev.cyber.local
        │                                                       │
        │                                                       │
  ┌───────────────┐                                     ┌───────────────┐
  │     DC01      │                                     │     DC02      │
  │ Windows Server│                                     │ Windows Server│
  │     2022      │                                     │     2022      │
  └───────────────┘                                     └───────────────┘
                │
                │
      ┌──────────────────────┐
      │      WIN11-01        │
      │     Windows 11       │
      │  Domain Workstation  │
      └──────────────────────┘
```

---

# Objectives

- Deploy an enterprise Active Directory environment using PowerShell automation.
- Simulate a realistic Windows enterprise infrastructure.
- Practice Active Directory administration.
- Perform Windows-based Active Directory attack scenarios.
- Learn common attack paths.
- Practice privilege escalation techniques.
- Learn Active Directory enumeration methodologies.
- Improve Windows security knowledge.
- Build a reusable enterprise lab for research and interview preparation.

---

# Requirements

| Component | Requirement |
|-----------|-------------|
| Hypervisor | VMware Workstation Pro |
| Operating System | Windows Server 2022 |
| Workstation | Windows 11 |
| RAM | Minimum 16 GB |
| Storage | 60 GB+ |
| PowerShell | 5.1+ |

---

# Virtual Machines

| Machine | Operating System | Role |
|----------|-----------------|------|
| DC01 | Windows Server 2022 | Root Domain Controller |
| DC02 | Windows Server 2022 | Child Domain Controller |
| WIN11-01 | Windows 11 | Domain Workstation |

---

# Project Structure

```text
AD-Enterprise-Lab
│
├── Scripts
│   ├── 00-Rename-Server.ps1
│   ├── 01-Install-ADDS.ps1
│   ├── 02-Create-OUs.ps1
│   ├── 03-Create-Users.ps1
│   ├── 04-Create-Groups.ps1
│   ├── 05-Create-ServiceAccounts.ps1
│   ├── 06-Register-SPNs.ps1
│   ├── 07-Add-GroupMembers.ps1
│   ├── 08-Create-SMB-Shares.ps1
│   └── 09-Disable-Defender-Firewall.ps1
│
├── Docs
├── Images
└── README.md
```

---

# Enterprise Structure

> Coming Soon

---

# Deployment

> Coming Soon

---

# Organizational Units

> Coming Soon

---

# Users

> Coming Soon

---

# Security Groups

> Coming Soon

---

# Service Accounts

> Coming Soon

---

# SMB Shares

> Coming Soon

---

# Group Policy Objects (GPO)

> Coming Soon

---

# Attack Scenarios

| Scenario | Status |
|----------|--------|
| Active Directory Enumeration | ⏳ |
| LDAP Enumeration | ⏳ |
| SMB Enumeration | ⏳ |
| Password Spraying | ⏳ |
| Kerberoasting | ⏳ |
| AS-REP Roasting | ⏳ |
| BloodHound Analysis | ⏳ |
| Privilege Escalation | ⏳ |
| Lateral Movement | ⏳ |

---

# Screenshots

> Coming Soon

---

# Future Improvements

- Additional Windows Workstations
- Active Directory Certificate Services (AD CS)
- Microsoft SQL Server
- IIS Web Server
- Windows Defender for Endpoint
- Sysmon
- Microsoft Sentinel Integration
- Splunk Integration
- Wazuh Integration

---

# Learning Outcomes

By completing this lab, you will gain hands-on experience with:

- Enterprise Active Directory Administration
- Windows Security
- Active Directory Enumeration
- Kerberos Attacks
- Windows Privilege Escalation
- Lateral Movement
- Internal Penetration Testing
- Enterprise Security Operations

---

# Disclaimer

This project is intended for educational purposes and authorized security testing only.

Do not use these techniques against systems you do not own or have explicit permission to test.

---

# License

MIT License
