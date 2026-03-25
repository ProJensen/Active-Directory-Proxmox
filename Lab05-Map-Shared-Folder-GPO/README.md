Lab05-Map-Shared-Folder-GPO

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
This lab documents the process of using Group Policy to map a shared folder automatically for domain users in an Active Directory environment.

The purpose of this project is to demonstrate how Group Policy can be used to standardize user access to shared network resources in a more efficient and manageable way.

## Scenario
A small business wants Sales users to access their department shared folder more easily without manually entering the network path each time.

As the IT administrator, I need to create and apply a Group Policy Object (GPO) that automatically maps the Sales shared folder for the appropriate users when they sign in to a domain-joined client.

## Objectives
- Open and manage Group Policy in a domain environment
- Create a new Group Policy Object (GPO)
- Configure a mapped network drive using Group Policy Preferences
- Link the policy to the correct Organizational Unit (OU)
- Verify that the mapped drive appears for the intended domain user

## Tools and Services Used
- Windows Server 2025
- Windows 11 Pro
- Active Directory Domain Services (AD DS)
- Group Policy Management
- File Explorer
- Proxmox VE

## Administrative Workflow

### Step 1: Open Group Policy Management
- Sign in to **DC01**
- Open **Server Manager**
- Select **Tools**
- Click **Group Policy Management**

This tool is used to create, edit, and link Group Policy Objects in the Active Directory environment.
