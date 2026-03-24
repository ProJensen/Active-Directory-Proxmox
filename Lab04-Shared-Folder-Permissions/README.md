# Lab 04 - Shared Folder and NTFS Permissions

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
This lab documents the process of creating a shared folder in a Windows domain environment and assigning both share permissions and NTFS permissions.

The purpose of this project is to demonstrate how access to shared resources can be controlled through Active Directory security groups in a structured and manageable way.

## Scenario
A small business needs to provide a shared folder for the Sales department so employees can access common files from a domain-joined client device.

As the IT administrator, I need to create the shared folder, assign the correct permissions, and verify that only authorized users can access it.

## Objectives
- Create a shared folder on the Windows Server
- Configure share permissions
- Configure NTFS permissions
- Assign access using Active Directory security groups
- Test folder access from a domain-joined client

## Tools and Services Used
- Proxmox VE
- Windows Server 2025
- Windows 11 Pro
- Active Directory Domain Services (AD DS)
- Active Directory Users and Computers
- File Explorer
- Server Manager

## Administrative Workflow

### Step 1: Create the Shared Folder
- Sign in to **DC01**
- Open **File Explorer**
- Create a folder such as **C:\SalesShare**

This folder will be used as the shared resource for the Sales department.

![Create Folder](./screenshots/1_Create_Folder.png)

### Step 2: Configure Share Permissions
- Right-click the folder and select **Properties**
- Go to the **Sharing** tab
- Select **Advanced Sharing**
- Check **Share this folder**
- Click **Permissions**
- Remove Permissions for **Everyone**
- Add the **Sales-Users** group
- Assign the required share permissions, such as **Change** and **Read**
- Click **Apply** and **OK** to save the settings

This step controls access to the folder over the network.

![Advanced Sharing](./screenshots/2_Advanced_Sharing.png)

![Permissions](./screenshots/2_Permissions.png)

![Select Group](./screenshots/2_Select_Group.png)

![Assign Permissions](./screenshots/2_Assign_Permission_2.png)

### Step 3: Configure NTFS Permissions
- In the folder **Properties**, go to the **Security** tab
- Select **Edit**
- Add the **Sales-Users** group
- Confirm that the related permissions such as **Modify**, **Read & execute**, **List folder contents**, **Read**, and **Write** are also allowed
- Click **Apply** and **OK** to save the settings

This step controls what users are allowed to do inside the folder after they gain access to it over the network.

![Edit Group](./screenshots/3_Edit_Group_In_Security.png)

![Select Group](./screenshots/3_Select_Group.png)

![Group Permissions](./screenshots/3_Group_Permissions.png)

### Step 4: Access the Shared Folder from the Domain Client
- Sign in to **CLIENT01** with a domain user account
- Open **File Explorer**
- In the address bar, enter the network path to the shared folder, such as:

```text
\\DC01\SalesShare
```
- Confirm that the authorized user can access the folder successfully

This step verifies that the shared folder is reachable from a domain-joined client.

![Sales User Sign in](./screenshots/4_Sales_User_SignIn.png)

![Access and Modify Folder](./screenshots/4_Access_Modify_Folder.png)

### Step 5: Verify Group-Based Access Control
- Test access using another user who is not a member of the group
- Confirm that access is allowed only for the authorized user or group

This step confirms that folder access is being controlled through Active Directory group membership.

![Access Restricted](./screenshots/5_Restricted_Access.png)

### Expected Outcome
At the end of this lab:
- A shared folder is created on the Windows Server
- Share permissions are configured
- NTFS permissions are configured
- The Sales-Users group is granted appropriate access
- An authorized domain user can access the shared folder from the client
- Unauthorized users are denied access

## Common Issues and Troubleshooting

### Issue 1: The shared folder cannot be opened from the client
Possible causes:
- The folder path was entered incorrectly
- File sharing is not enabled properly
- Network communication between the client and server is not working

### Issue 2: The user can access the folder but cannot modify files
Possible causes:
- Share permissions are too restrictive
- NTFS permissions do not allow write access
- The user is not a member of the correct security group

### Issue 3: A user who should be denied access can still open the folder
Possible causes:
- The user belongs to another group with access
- Default permissions were not removed or reviewed
- NTFS permissions are broader than intended
