# Challenge 1: Create a host pool for multi-session

[Previous Challenge](../../readme.md) - **[Home](../../README.md)** - [Next Challenge](./02-AVD-RDP-Properties.md)

## Introduction

In this challenge you will create Microsoft Entra ID joined pooled desktops from a Microsoft Windows 11 Multi-Session Gallery Image. After the deployment you will connect to this session host with the native or web Remote Desktop client. 

## Challenge

Create AVD multi-session hostpool joined in Microsoft Entra ID:
- Region: **North Europe**
- Metadata location: **North Europe**
- Validation environment: **No**
- Create Session Host Configuration: **No**
- Host Pool type: **Pooled**
- Compute family: **Standard Dasv6** or **Standard Dsv6**
- Choose **Windows 11 Enterprise multi-session Version + Microsoft 365 Apps** Gallery image  
- Domain to join: **Microsoft Entra ID** and Enroll with Intune **No**
- Register desktop app group to **new workspace**
- Assign users
- Enable Microsoft Entra ID single sign on: "Connections will use Microsoft Entra authentication to provide single sign-on."

Login to the session host
- Log in as a user and verify that the operating system is a multi-session build

Create new Remote Apps
- Deploy **Microsoft Edge and Word (or whatever) as Remote Apps**

## 💡 Pro Tipps 💡
> **1.** We are deploying an EntraID only host pool. In this case you have to set IAM (RBAC) rights on the resource group level. [More information here](https://learn.microsoft.com/en-us/azure/virtual-desktop/azure-ad-joined-session-hosts#assign-user-access-to-host-pools)

> **2.** If you are trying to access your virtual desktop from **Windows devices or other devices that are not connected to the same Entra ID tenant**, add **targetisaadjoined:i:1** as a custom RDP property to the host pool. [More information here](https://learn.microsoft.com/en-us/azure/virtual-desktop/deploy-azure-ad-joined-vm#access-azure-ad-joined-vms)

## Success Criteria
- Host Pools are created and Session Hosts are showing available
- Users are assigned to the appropriate application group of the host pool
- Able to show the Host Pool settings configured
- VMs are joined to Microsoft Entra ID
- Users can sign in to the VM
- Office Apps can be accessed via RemoteApp

## Learning Resources
- [Create Azure Virtual Desktop Hostpool](https://learn.microsoft.com/en-us/azure/virtual-desktop/create-host-pools-azure-marketplace)
- [Manage app groups for Azure Virtual Desktop portal](https://learn.microsoft.com/en-us/azure/virtual-desktop/manage-app-groups)
- [Connect to Azure Virtual Desktop with the Remote Desktop client for Windows](https://learn.microsoft.com/en-us/azure/virtual-desktop/users/connect-windows?tabs=subscribe#install-the-windows-desktop-client)
