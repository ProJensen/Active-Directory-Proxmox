# Lab 03 - Join Client to Domain

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
This lab documents the process of joining a Windows 11 client virtual machine to an Active Directory domain.

The purpose of this project is to demonstrate the administrative workflow required to prepare a domain-joined client, configure its network settings correctly, and verify successful domain access in a Windows environment.

## Scenario
A small business has already deployed its first Domain Controller and created initial users, groups, and Organizational Units in Active Directory.

As the IT administrator, I need to prepare a Windows 11 client device and join it to the domain so that it can be centrally managed through Active Directory.

## Objectives
- Rename the Windows 11 client computer name
- Configure the client network settings for domain communication
- Set the client DNS server to the Domain Controller
- Join the client to the Active Directory domain
- Verify successful domain authentication

## Tools and Services Used
- Proxmox VE
- Windows 11 Pro
- Windows Server 2025
- Active Directory Domain Services (AD DS)
- DNS

## Administrative Workflow

### Step 1: Rename the Client Computer
- Open **Settings**
- Go to **System** > **About**
- Select **Rename this PC**
- Rename the computer to **CLIENT01**
- Restart the client when prompted

![Rename Client](./screenshots/1_Rename_Client.png)

### Step 2: Configure the Client Network Settings
- Open **Control Panel**
- Go to **Network and Sharing Center**
- Select **Change adapter settings**
- Right-click the active Ethernet adapter and select **Properties**
- Select **Internet Protocol Version 4 (TCP/IPv4)** and click **Properties**
- Configure the client network settings:
  - IP address: **10.10.10.20** or another available IP in the lab subnet
  - Subnet mask: **255.255.255.0**
  - Default gateway: **10.10.10.1**
  - Preferred DNS server: **10.10.10.10**

The DNS server must point to the Domain Controller so the client can resolve the Active Directory domain correctly.

![Client IPv4 Settings](./screenshots/2_Client_IPv4_Settings.png)
