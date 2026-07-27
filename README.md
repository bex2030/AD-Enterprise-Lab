# AD-Enterprise-Lab

> A fully automated Enterprise Active Directory lab built with PowerShell for Windows administration, Active Directory security, and Windows offensive security training.

![Windows](https://img.shields.io/badge/Windows-Server%202022-blue)
![PowerShell](https://img.shields.io/badge/PowerShell-Automation-5391FE)
![Active Directory](https://img.shields.io/badge/Active%20Directory-Enterprise-success)
![Status](https://img.shields.io/badge/Status-In%20Development-orange)

---

# Overview

**AD-Enterprise-Lab** is a realistic Enterprise Active Directory environment designed for cybersecurity professionals, penetration testers, students, and anyone interested in learning Active Directory from both administrative and offensive security perspectives.

The lab is fully deployed using PowerShell automation, enabling the rapid creation of a complete enterprise Active Directory environment within minutes. It simulates a realistic corporate infrastructure consisting of multiple domain controllers, a child domain, Windows 11 enterprise workstations, Organizational Units (OUs), users, security groups, service accounts, SMB shares, and intentionally vulnerable attack scenarios.

Unlike many traditional Active Directory labs that rely on Kali Linux as the primary attack platform, this project focuses on Windows-native offensive techniques to better reflect modern internal penetration testing and post-compromise operations in enterprise environments.

The project is intended for educational purposes and authorized security testing only.

---

# Table of Contents

- Overview
- Features
- Lab Topology
- Objectives
- Requirements
- Virtual Machines
- Enterprise Structure
- Organizational Units
- Users
- Security Groups
- Service Accounts
- Deployment
- Project Structure
- Group Policy Objects (GPO)
- Attack Scenarios
- Screenshots
- Future Improvements
- Learning Outcomes
- Disclaimer
- License

---

# Features

## Infrastructure Features

- Fully Automated PowerShell Deployment
- Enterprise Active Directory Forest
- Root Domain
- Child Domain
- Windows Server 2022 Domain Controllers
- Windows 11 Enterprise Workstations
- Enterprise Network Topology

## Active Directory Features

- Organizational Units (OUs)
- Users
- Security Groups
- Service Accounts
- Service Principal Names (SPNs)
- SMB Shares
- Kerberos Authentication
- Group Policy Objects (GPO)

## Offensive Security Features

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
- Practice Active Directory administration and management.
- Perform Windows-based Active Directory attack scenarios.
- Understand common Active Directory attack paths.
- Practice privilege escalation techniques.
- Learn Active Directory enumeration methodologies.
- Improve Windows security knowledge through hands-on experience.
- Build a reusable enterprise lab for research, demonstrations, and interview preparation.

---

# Requirements

| Component | Requirement |
|-----------|-------------|
| Hypervisor | VMware Workstation Pro |
| Operating System | Windows Server 2022 |
| Workstation | Windows 11 Enterprise |
| RAM | Minimum 16 GB (32 GB Recommended) |
| Storage | 60 GB+ |
| PowerShell | 5.1+ |
| Network | NAT |

---

# Virtual Machines

| Machine | Operating System | Role | CPU | RAM |
|----------|-----------------|------|-----|-----|
| DC01 | Windows Server 2022 | Root Domain Controller | 2 Cores | 3 GB |
| DC02 | Windows Server 2022 | Child Domain Controller | 2 Cores | 3 GB |
| WIN11-01 | Windows 11 Enterprise | Domain Workstation | 2 Cores | 4 GB |

---

# Enterprise Structure

The following structure represents the Active Directory hierarchy implemented throughout the lab.

```text
Enterprise Forest
│
├── cyber.local
│   └── HeadOffice
│       ├── Users
│       │   ├── ahmed
│       │   ├── faris
│       │   ├── mohamed
│       │   ├── waleed
│       │   └── osama
│       │
│       ├── Groups
│       │   ├── GG_IT
│       │   ├── GG_HR
│       │   ├── GG_Cyber
│       │   └── GG_Management
│       │
│       └── Service Accounts
│           └── iis_server
│
└── dev.cyber.local
    └── Development
        ├── Users
        │   ├── ali
        │   ├── nasser
        │   ├── faisal
        │   ├── ibrahim
        │   └── saud
        │
        └── Groups
            ├── GG_Developers
            ├── GG_QA
            ├── GG_DevOps
            ├── GG_Database
            └── GG_ProjectManagers
```

The root domain (`cyber.local`) represents the company's Head Office, while the child domain (`dev.cyber.local`) represents the Development environment. This separation simulates a realistic enterprise Active Directory infrastructure and enables multi-domain administration, trust relationships, and Windows-based attack scenarios.

---

# Organizational Units

The following Organizational Unit (OU) structure is implemented throughout the Active Directory environment.

```text
cyber.local
└── HeadOffice
    ├── Users
    ├── Groups
    └── Service Accounts

dev.cyber.local
└── Development
    ├── Users
    └── Groups
```

The Organizational Unit (OU) hierarchy is designed to simulate a realistic enterprise environment while providing a clear separation of users, groups, and service accounts across the root and child domains. This structure simplifies administration, delegation, and security management.

---

# Users

The following domain users are automatically created by the PowerShell deployment scripts to simulate a realistic enterprise environment with different departments and privilege levels.

## Root Domain (`cyber.local`)

| Username | Department | Role |
|----------|------------|------|
| ahmed | N/A | Low-Privileged Domain User |
| faris | IT | IT Support |
| mohamed | HR | HR Officer |
| waleed | Management | Manager |
| osama | Cyber Security | Security Analyst |

## Child Domain (`dev.cyber.local`)

| Username | Department | Role |
|----------|------------|------|
| ali | Development | Software Developer |
| nasser | Development | Backend Developer |
| faisal | Development | Frontend Developer |
| ibrahim | Development | QA Engineer |
| saud | Development | DevOps Engineer |

The user accounts are intentionally assigned different roles and privilege levels to simulate a realistic enterprise environment and support Active Directory administration, authentication, and Windows-based security testing scenarios.

---

# Security Groups

The following security groups are used to manage user permissions and simulate Role-Based Access Control (RBAC) within the Active Directory environment.

## Root Domain (`cyber.local`)

| Group Name | Description |
|------------|-------------|
| GG_IT | IT department users |
| GG_HR | Human Resources department users |
| GG_Cyber | Cyber Security team |
| GG_Management | Management department |

## Child Domain (`dev.cyber.local`)

| Group Name | Description |
|------------|-------------|
| GG_Developers | Software Development team |
| GG_QA | Quality Assurance team |
| GG_DevOps | DevOps team |
| GG_Database | Database Administrators |
| GG_ProjectManagers | Project Management team |

The security groups simplify permission management and demonstrate Role-Based Access Control (RBAC) within a multi-domain Active Directory environment.

---

# Service Accounts

The following service accounts are configured to support enterprise services and Windows-based security testing scenarios.

| Account | Purpose |
|---------|---------|
| iis_server | Dedicated IIS service account with a registered SPN for Kerberos authentication and Kerberoasting demonstrations. |

The configured service accounts simulate real-world enterprise services and enable realistic attack scenarios involving Kerberos authentication and Service Principal Names (SPNs).

---

# Deployment

This section provides step-by-step instructions for deploying the entire Active Directory lab using the included PowerShell automation scripts.

The deployment process includes:

- Preparing the virtual machines
- Configuring network settings
- Installing Active Directory Domain Services (AD DS)
- Creating the Active Directory Forest
- Deploying the Child Domain
- Creating Organizational Units (OUs)
- Creating Users and Security Groups
- Configuring Service Accounts and Service Principal Names (SPNs)
- Creating SMB Shares
- Joining Windows 11 workstations to the domain
- Verifying the lab deployment

Detailed deployment instructions will be added as each deployment phase is completed.

---

# Project Structure

```text
AD-Enterprise-Lab
│
├── Scripts                    # PowerShell automation scripts
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
├── Docs                       # Documentation and attack scenarios
├── Images                     # Lab screenshots
└── README.md
```

MIT License
