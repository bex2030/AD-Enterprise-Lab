# AD-Enterprise-Lab

> A fully automated Enterprise Active Directory lab built with PowerShell to simulate a realistic corporate environment for Windows administration, Active Directory security, and Windows-based attack scenarios.

---

## Overview

**AD-Enterprise-Lab** is a realistic Active Directory enterprise environment designed for cybersecurity professionals, penetration testers, students, and anyone interested in learning Active Directory from both administrative and offensive security perspectives.

The entire environment is deployed automatically using PowerShell scripts, allowing you to build a fully functional enterprise lab within minutes. The lab simulates a real corporate infrastructure with multiple domain controllers, a child domain, Windows 11 workstations, organizational units, users, groups, service accounts, SMB shares, and intentionally vulnerable attack scenarios for learning and research.

Unlike many traditional Active Directory labs that rely on Kali Linux, this project focuses on **Windows-based attack techniques**, providing a more realistic representation of modern internal penetration testing and post-compromise operations.

---

# Features

- Fully Automated PowerShell Deployment
- Enterprise Active Directory Forest
- Root Domain & Child Domain
- Windows Server 2022 Domain Controllers
- Windows 11 Domain Workstations
- Organizational Units (OUs)
- Users & Security Groups
- Service Accounts & SPNs
- SMB Shares
- Kerberos Authentication
- Enterprise Network Structure
- Windows-based Attack Scenarios
- PowerView
- SharpHound
- BloodHound
- Rubeus
- Password Spraying
- Kerberoasting
- AS-REP Roasting
- Active Directory Enumeration
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

This project aims to provide a realistic enterprise Active Directory environment for learning, practicing, and demonstrating offensive and defensive Active Directory concepts.

The objectives include:

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
