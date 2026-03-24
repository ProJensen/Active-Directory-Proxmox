# Active-Directory-Proxmox
Hands-on Active Directory home lab built with Proxmox and Windows Server.

## Table of Contents
- [Overview](#overview)
- [Goals](#goals)
- [Skills Covered](#skills-covered)
- [Lab Projects](#lab-projects)
- [Lab Environment](#lab-environment)
- [Tools and Technologies](#tools-and-technologies)
- [Key Learning Areas](#key-learning-areas)
- [Repository Structure](#repository-structure)
- [Progress Tracker](#progress-tracker)
- [Author](#author)

## Overview
This repository documents my Active Directory lab projects built in a Proxmox home lab environment.

It focuses on Windows Server administration, Active Directory, domain-joined clients, user management, shared folders, and Group Policy.

## Goals
- Build a structured Active Directory lab
- Practice Windows Server and Active Directory administration through hands-on lab scenarios
- Develop documentation and troubleshooting skills
- Strengthen practical knowledge of domain environments, user management, and group policy configuration
- Demonstrate initiative and hands-on learning for IT support and system administration roles

## Skills Covered
- Active Directory
- Windows Server 2025
- Active Directory Domain Services (AD DS)
- DNS and Network Configuration
- Domain Join Process
- User, Group, and OU Management
- Shared Folder and NTFS Permissions
- Group Policy
- Proxmox Virtualization

## Lab Projects

| Lab No. | Project Title | Focus Area | Status |
|-|-|-|-|
| 01 | [Install AD DS](./Lab01-Install-AD-DS/) | Domain setup / AD DS / DNS | Completed |
| 02 | [Create Users, Groups, and OUs](./Lab02-Users-Groups-OUs/) | Identity administration | Completed |
| 03 | [Join Client to Domain](./Lab03-Domain-Join-Client/) | Domain join / client management | Completed |
| 04 | [Shared Folder Permission](./Lab04-Shared-Folder-Permissions/) | File access / permissions | Planned |
| 05 | [Group Policy](./Lab05-GPO/) | Policy management / desktop configuration | Planned |

## Lab Environment
This portfolio is based on a simulated Active Directory lab environment built in Proxmox for learning and portfolio development purposes.

The environment uses Proxmox for virtualization and OPNsense for internal lab network separation, with Windows Server and a Windows client used to practice common administration tasks in a Windows domain environment.

## Tools and Technologies
- Proxmox VE
- Windows Server 2025
- Windows 11
- Active Directory Domain Services (AD DS)
- DNS
- Group Policy Management
- Managed Switch (network and VLAN separation)
- OPNsense
- GitHub

## Key Learning Areas
- Building an Active Directory lab in a virtualized environment
- Installing and configuring a Windows Server Domain Controller
- Understanding DNS and domain join requirements in a Windows domain
- Managing users, groups, and organizational units in Active Directory
- Joining a Windows client to the domain
- Configuring shared folders and NTFS permissions
- Applying Group Policy settings
- Developing troubleshooting skills

## Repository Structure
```text
Active-Directory-Proxmox/
│
├── README.md
├── Lab01-Install-AD-DS/
│   ├── README.md
│   └── screenshots/
├── Lab02-Users-Groups-OUs/
│   ├── README.md
│   └── screenshots/
├── Lab03-Domain-Join-Client/
│   ├── README.md
│   └── screenshots/
├── Lab04-Shared-Folder-Permissions/
│   ├── README.md
│   └── screenshots/
└── Lab05-GPO/
    ├── README.md
    └── screenshots/
```

## Progress Tracker
- [x] Complete Lab 01 - Install AD DS
- [x] Complete Lab 02 - Create Users, Groups, and OUs
- [x] Complete Lab 03 - Join Client to Domain
- [ ] Complete Lab 04 - Shared Folder Permissions
- [ ] Complete Lab 05 - Group Policy

## Author
**Jenhon Sze**

This repository is part of my IT support, system administration, and home lab learning portfolio.
