# Lab 08 - Configure Remote Assistance by Group Policy

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
This lab documents the process of configuring Remote Assistance by Group Policy in an Active Directory domain environment.

The purpose of this project is to demonstrate how remote support access can be centrally configured for a delegated IT support account.

## Scenario
A company wants to allow the IT Support account to remotely assist users on domain-joined client computers.

As the IT administrator, I need to use Group Policy to enable Offer Remote Assistance on the target client computer, assign the IT Support account as an allowed helper, and verify that remote assistance can be offered from ADMIN01 to CLIENT01.

## Objectives
- Create a dedicated security group for Remote Assistance helpers
- Add the IT Support account to the helper group
- Create and link a GPO for Remote Assistance
- Enable Offer Remote Assistance through Group Policy
- Configure the helper group in the policy
- Verify that the required firewall settings are allowed
- Test a Remote Assistance connection from ADMIN01 to CLIENT01
