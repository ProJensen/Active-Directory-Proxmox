# Lab01 - Install Active Directory Domain Services

## Table of Contents
- [Overview](#overview)
- [Scenario](#scenario)
- [Objectives](#objectives)
- [Tools and Services Used](#tools-and-services-used)
- [Administrative Workflow](#administrative-workflow)
- [Expected Outcome](#expected-outcome)
- [Common Issues and Troubleshooting](#common-issues-and-troubleshooting)
- [What I Learned](#what-i-learned)

## Overview
This lab documents the initial deployment of Active Directory Domain Services (AD DS) in a Windows Server environment.

The purpose of this project is to demonstrate the core administrative workflow required to prepare a Windows Server virtual machine, configure its network settings, install AD DS, and promote it to a Domain Controller.

## Scenario
A small business is setting up its first internal Windows domain environment to centralize authentication, user management, and administrative control.

As the IT administrator, I need to configure a Windows Server system as the first Domain Controller for the organization.

## Objectives
- Rename the Windows Server virtual machine to a meaningful server name
- Configure a static IP address
- Install the Active Directory Domain Services role
- Promote the server to a Domain Controller
- Create a new Active Directory forest

## Tools and Services Used
- Proxmox VE
- Windows Server 2025
- Active Directory Domain Services (AD DS)
- DNS
- Server Manager

## Administrative Workflow

### Step 1: Rename the Server
- Open **Server Manager**
- Go to **Local Server**
- Select the current **Computer name**
- Click **Change**
- Rename the server to **DC01**
- Restart the server when prompted

![Local Server](https://raw.githubusercontent.com/ProJensen/Active-Directory-Proxmox/refs/heads/main/Lab01-Install-AD-DS/screenshots/1_Local_Server.png?token=GHSAT0AAAAAADXN5BH6YIITISLB2PN4VDPK2N4VAFA)

![Rename Server](https://raw.githubusercontent.com/ProJensen/Active-Directory-Proxmox/refs/heads/main/Lab01-Install-AD-DS/screenshots/1_Rename_Server.png?token=GHSAT0AAAAAADXN5BH66BINIHDHNIRZFVLA2N4VATA)
