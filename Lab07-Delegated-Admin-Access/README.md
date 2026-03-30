# Lab 07 - Delegated Admin Access

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
This lab documents the process of configuring delegated admin access in an Active Directory domain environment.

The purpose of this project is to demonstrate how limited administrative permissions can be assigned to a support account without granting full Domain Admin rights.

## Scenario
A small business wants to allow junior IT staff to perform basic account support tasks in the Windows domain environment without giving them full administrative control over the domain.

As the IT administrator, I need to create a dedicated support account, assign it to a delegated security group, and configure limited permissions so it can manage selected user account tasks in Active Directory.

## Objectives
- Create a dedicated support account for administrative tasks
- Create a security group for delegated access
- Add the support account to the delegated group
- Delegate limited permissions to the target OU
- Verify that the support account can perform the assigned tasks
- Confirm that the support account does not have full Domain Admin rights

## Tools and Services Used
- Windows Server 2025
- Active Directory Users and Computers
- Active Directory Domain Services (AD DS)
- Server Manager
- Proxmox VE

## Administrative Workflow

### Step 1: Open Active Directory Users and Computers
- Sign in to **DC01**
- Open **Server Manager**
- Select **Tools**
- Click **Active Directory Users and Computers**

### Step 2: Create a Security Group for Delegated Access
- In **Active Directory Users and Computers**, locate the appropriate OU for administrative groups
- Right-click the OU and select **New > Group**
- Create a group named:
  - **Delegated Admins**
- Set:
  - **Group scope:** `Global`
  - **Group type:** `Security`
- Click **OK**
