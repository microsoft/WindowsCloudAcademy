# Challenge 1: Create a host pool for multi-session

[Previous Challenge](../../readme.md) - **[Home](../../README.md)** - [Next Challenge](./02-AVD-RDP-Properties.md)

## Introduction

In this challenge, you will deploy an **Azure Virtual Desktop (AVD) pooled host pool** using the latest available **Windows 11 Enterprise multi-session image with Microsoft 365 Apps** from the Azure Marketplace. A pooled host pool allows multiple users to share session host VMs, with each user working in their own session.

The session hosts will be **joined only to Microsoft Entra ID**, without joining a traditional Active Directory domain. You will configure user access and Microsoft Entra ID single sign-on, then connect to a full desktop using a supported native client or web client to verify the deployment.

You will also publish applications such as **Microsoft Word or Excel** through a **RemoteApp application group**. This lets users launch individual applications without opening a full remote desktop. By the end of the challenge, you will have explored both desktop and RemoteApp access in a cloud-only AVD environment.

## Challenge

Deploy a pooled AVD environment in your team's resource group. First verify desktop access, then publish and test individual applications through RemoteApp.

### 1. Create the host pool and session hosts

Use the following configuration. Replace `[n]` with your team number.

| Setting | Required value |
|---|---|
| Resource group | `RG-WCA-PUNK[n]` |
| Host pool type | **Pooled** |
| Metadata location | **North Europe** |
| Session host region | **North Europe** |
| Validation environment | **No** |
| Create Session Host Configuration | **No** |
| VM size family | **Standard Dasv6** or **Standard Dsv6** |
| Image | Latest available **Windows 11 Enterprise multi-session with Microsoft 365 Apps** |
| Directory join | **Microsoft Entra ID** only |
| Enroll with Intune | **No** |

### 2. Configure workspace and user access

- Create a workspace and register the host pool's **desktop application group**.
- Assign your team's user group, `GRP-P[n]-Users`, to the desktop application group.
- Set the host pool's **preferred application group type** to **Desktop** for the desktop test.
- Configure the host pool's **Microsoft Entra ID single sign-on** RDP setting using the PowerShell snippet in **Pro tip 2**.
- The **Virtual Machine User Login** role is already configured for your team's resource group; see **Pro tip 1**.

### 3. Verify desktop access

- Confirm that the session hosts report **Available**.
- Connect using a supported native client or web client with a team user account.
- Verify that the session host runs **Windows 11 Enterprise multi-session**.
- Confirm that Microsoft 365 Apps are installed.

### 4. Publish and test RemoteApps

- Create a **RemoteApp application group** associated with the same host pool.
- Publish **Microsoft Word and Excel**.
- Register the RemoteApp application group with your workspace.
- Assign your team's user group, `GRP-P[n]-Users`, to the RemoteApp application group.
- Change the host pool's **preferred application group type** to **RemoteApp**. When users are assigned to both application groups, this determines which resource type they receive.
- Refresh the workspace in your client, then launch the published applications and verify that they open without displaying a full desktop.

## 💡 Pro Tips 💡
> **1. VM sign-in permissions are already configured.** Microsoft Entra ID-joined session hosts require the **Virtual Machine User Login** RBAC role for user sign-in. The lab deployment assigns this role to `GRP-P[n]-Users` on `RG-WCA-PUNK[n]`. Deploy session hosts there to inherit it; you must still assign the group to the AVD application groups. [Learn more](https://learn.microsoft.com/en-us/azure/virtual-desktop/azure-ad-joined-session-hosts#assign-user-access-to-host-pools)

> **2. Configure SSO.** Use the snippet below to set the host pool's **Microsoft Entra ID SSO** RDP property. Devices can belong to another tenant, but users must sign in with an authorized account in the host pool's tenant. [Learn more](https://learn.microsoft.com/en-us/azure/virtual-desktop/deploy-azure-ad-joined-vm#access-azure-ad-joined-vms)
>
> Run in **Azure Cloud Shell > PowerShell** with the correct subscription selected. Replace `[n]` with your team number and `Your-Hostpool-Name` with your host pool's name.
>
> ```powershell
> $ResourceGroupName = "RG-WCA-PUNK[n]"
> $HostPoolName = "Your-Hostpool-Name"
> $rdpProperties = "drivestoredirect:s:;usbdevicestoredirect:s:;redirectclipboard:i:0;redirectprinters:i:0;audiomode:i:0;videoplaybackmode:i:1;devicestoredirect:s:*;redirectcomports:i:1;redirectsmartcards:i:1;enablecredsspsupport:i:1;redirectwebauthn:i:1;use multimon:i:1;enablerdsaadauth:i:1;targetisaadjoined:i:1"
>
> Update-AzWvdHostPool -ResourceGroupName $ResourceGroupName -Name $HostPoolName -CustomRdpProperty $rdpProperties
> ```

## Success Criteria
- Pooled host pool is deployed in **North Europe**, with session hosts **Available**.
- Hosts run the latest **Windows 11 Enterprise multi-session with Microsoft 365 Apps** and are **Microsoft Entra ID-joined only**.
- Application groups are registered with the workspace and assigned to the team's user group.
- A team user can access the desktop with **Microsoft Entra ID SSO**.
- Published applications, for example **Word and Excel**, launch successfully as RemoteApps, with **RemoteApp** set as the preferred application group type.

## Learning Resources
- [Create Azure Virtual Desktop Hostpool](https://learn.microsoft.com/en-us/azure/virtual-desktop/create-host-pools-azure-marketplace)
- [Manage app groups for Azure Virtual Desktop portal](https://learn.microsoft.com/en-us/azure/virtual-desktop/manage-app-groups)
- [Connect to Azure Virtual Desktop with the Remote Desktop client for Windows](https://learn.microsoft.com/en-us/azure/virtual-desktop/users/connect-windows?tabs=subscribe#install-the-windows-desktop-client)
