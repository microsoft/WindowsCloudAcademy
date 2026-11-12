# Challenge 2: Configure RDP Properties

[Previous Challenge](./01-W365-Provisioning-CPC.md) - **[Home](../../README.md)** - [Next Challenge](./03-W365-App-Deployment.md)

## Introduction

Remote Desktop Protocol (RDP) redirection lets users share their local clipboard, drives, and peripherals with a Cloud PC. For security reasons, Microsoft disables clipboard, drive, USB, and printer redirection by default for Cloud PCs.

In this challenge, you will use the **Microsoft Intune Settings catalog** to enable clipboard and drive redirection on your Cloud PC. You will assign the policy to your device and test copying text and accessing redirected client drives.

## Challenge

Use the Microsoft Entra joined Cloud PC provisioned in Challenge 1. Enable clipboard and client drive redirection for this lab, leaving other redirection settings unchanged.

### 1. Target your Cloud PC

Use the existing **dynamic device group** `GRP-P[n]-Devices`, replacing `[n]` with your team number:

- Update its **dynamic membership rule** to match your Cloud PC's custom device name from Challenge 1.
- Set **Dynamic rule processing** to **On**.
- Wait for membership processing and verify that only your Cloud PC is included before assigning the policy. Do not target other teams' devices.

### 2. Create and assign the policy

In the **Microsoft Intune admin center**, create a configuration policy for **Windows 10 and later** using the **Settings catalog**. Search for **Device and Resource Redirection** and configure:

| Setting | Required value |
|---|---|
| Do not allow Clipboard redirection | **Disabled** |
| Do not allow drive redirection | **Disabled** |

Assign the policy to the **dynamic device group** `GRP-P[n]-Devices`.

### 3. Test redirection

- Sync your Cloud PC with Intune and confirm that both settings report successful application.
- In **Windows App** on your local Windows device, allow clipboard and drive redirection in the connection settings where available.
- Sign out of the Cloud PC session, then reconnect using **Windows App** on a local Windows device.
- Verify that you can copy and paste text in both directions between the local device and the Cloud PC.
- Open **File Explorer** on the Cloud PC and verify that the client drives selected for redirection are accessible.

## 💡 Pro Tips 💡

> **1. Disabled means allowed.** Both settings begin with **Do not allow**, so set them to **Disabled** to permit redirection. If it remains blocked, check for conflicting policies and client-side redirection settings.

> **2. Scope matters.** Use the exact device name or a team-specific prefix such as `CPC-P1-`, not the broad prefix `CPC-`. Dynamic group membership and policy application can take time.

> **3. Our recommended assignment approach.** Outside this lab, we recommend **All devices** with an **Intune assignment filter** in **Include** mode to target the intended devices. For this challenge, use the existing **dynamic device group** to practice membership rules and group-based policy assignments.

## Success Criteria
- The policy targets only your Cloud PC through `GRP-P[n]-Devices` with **Dynamic rule processing** set to **On**.
- Intune reports that both **Do not allow** settings are successfully applied as **Disabled**.
- Copy and paste works in both directions, and selected client drives are accessible from the Cloud PC.

## Learning Resources
- [Manage RDP device redirections for Cloud PCs](https://learn.microsoft.com/en-us/windows-365/enterprise/manage-rdp-device-redirections)
- [Create a device profile in Microsoft Intune](https://learn.microsoft.com/en-us/mem/intune/configuration/device-profile-create)
- [Dynamic membership rules for groups in Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/enterprise-users/groups-dynamic-membership)
- [Use filters when assigning your apps, policies, and profiles in Microsoft Intune](https://learn.microsoft.com/en-us/intune/intune-service/fundamentals/filters)
