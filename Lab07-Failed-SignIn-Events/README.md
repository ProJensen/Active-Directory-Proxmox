# Lab 07 - Investigate Suspicious Sign-In Activity

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
This lab documents the process of investigating suspicious sign-in activity in a Windows domain environment using Event Viewer.

The purpose of this project is to demonstrate how an administrator can review security logs, identify failed sign-in attempts and account lockout events, and determine whether follow-up action is needed to help protect a user account.

## Scenario
A small business notices suspicious sign-in activity involving a domain user account, such as repeated failed sign-in attempts and possible account lockout behavior.

As the IT administrator, I need to use Event Viewer to review the security logs, identify the relevant sign-in events, and determine whether any follow-up action is needed to protect the account, such as resetting the password, unlocking the account, or requiring the user to change the password at next sign-in.

## Objectives
- Open and review the Security log in Event Viewer
- Identify failed sign-in events
- Identify account lockout events
- Review key event details such as username, time, and event description
- Investigate suspicious account activity using recorded security events
- Review possible follow-up actions such as password reset, account unlock, or requiring a password change

## Tools and Services Used
- Windows Server 2025
- Active Directory Domain Services (AD DS)
- Event Viewer
- Security log
- Active Directory Users and Computers
- Server Manager
- Proxmox VE
