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
A small business wants junior IT staff to perform basic user support tasks for employees in different departments without giving them full Domain Admin rights.

As the IT administrator, I need to create a dedicated support account in the IT OU, assign it to a delegated security group, and grant limited permissions over the HR and Sales OUs.

## Objectives
- Create a dedicated IT support account
- Create a security group for delegated administration
- Add the support account to the delegated group
- Delegate limited permissions to the target OUs
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

This group will be used to assign limited administrative permissions in a more organized way.

![New Group](./screenshots/2_New_Group.png)

### Step 3: Create a Dedicated IT Support User in the IT OU
- In the **IT** OU, right-click and select **New > User**
- Create a support account
- Example:
  - **First name:** `IT`
  - **Last name:** `Support`
  - **User logon name:** `itsupport`
- Set a password for the account
- Configure the password options as needed
- Complete the user creation process

This creates a dedicated support account instead of using a highly privileged account for daily support tasks.

![New User](./screenshots/3_New_User.png)

### Step 4: Add the Support User to the Delegated Group
- Locate the **itsupport** account
- Open **Properties**
- Go to the **Member Of** tab
- Click **Add**
- Add the account to:
  - **Delegated Admins**
- Click **Apply** and **OK**

This step adds the support account to the security group that will receive delegated permissions.

![Delegated Admins](./screenshots/4_Delegated_Admins.png)

### Step 5: Delegate Control on the HR OU
- In Active Directory Users and Computers, right-click the **HR** OU
- Select **Delegate Control**
- Click **Next**
- Click **Add**
- Select:
  - **Delegated Admins**
- Click **OK**
- Click **Next**
- Select the following common tasks:
  - **Reset user passwords and force password change at next logon**
  - **Read all user information**
  - **Create, delete, and manage user accounts**
- Complete the wizard

This step grants the delegated group limited user administration permissions over the HR OU without assigning full domain-wide administrative rights.

![HR Delegate Control](./screenshots/5_HR_Delegate_Control.png)

![Add Group](./screenshots/5_Add_Group.png)

![Task to Delegate](./screenshots/5_Task_To_Delegate.png)

### Step 6: Delegate Control on the Sales OU
- In Active Directory Users and Computers, right-click the **Sales** OU
- Select **Delegate Control**
- Click **Next**
- Click **Add**
- Select:
  - **Delegated Admins**
- Click **OK**
- Click **Next**
- Select the following common tasks:
  - **Reset user passwords and force password change at next logon**
  - **Read all user information**
  - **Create, delete, and manage user accounts**
- Complete the wizard

This step grants the delegated group limited user administration permissions over the Sales OU without assigning full domain-wide administrative rights.

### Step 7: Prepare ADMIN01 with RSAT
- Create a new Windows 11 Pro virtual machine named **ADMIN01**
- Join **ADMIN01** to the **lab.local** domain
- Sign in to **ADMIN01** using an administrative account
- Open **Settings > System > Optional features**
- Click **View features**
- Click **Available features**
- Search for:
  - **RSAT: Active Directory Domain Services and Lightweight Directory Services Tools**
- Select the feature and install it

This step prepares ADMIN01 as a dedicated admin workstation for Active Directory management tasks.

![RSAT Installation](./screenshots/7_RSAT_Installation.png)

### Step 8: Sign In with the IT Support Account
- Sign out of the administrative account on **ADMIN01**
- Sign in using the **IT Support** account
- Open **Active Directory Users and Computers** from **Windows Tools** or by searching from the Start menu

This step is used to verify that the delegated support account can access the AD management tools from ADMIN01.

![Active Directory Users and Computers](./screenshots/8_Active_Directory_Users_And_Computers.png)
