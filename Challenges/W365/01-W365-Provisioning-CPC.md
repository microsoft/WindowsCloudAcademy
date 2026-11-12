# Challenge 1: Provisioning a Windows 365 Enterprise Cloud PC

[Previous Challenge](./03-AVD-Monitoring.md) - **[Home](../../README.md)** - [Next Challenge](./02-W365-RDP-Properties.md)

## Introduction

In this challenge, you will provision a **Windows 365 Enterprise Cloud PC** for a team user. Unlike a pooled AVD desktop, a Cloud PC provides a personal Windows desktop with dedicated resources, apps, files, and settings.

You will configure licensing, create a provisioning policy using a **Microsoft-hosted network**, and grant the user local administrator rights for this lab. After provisioning, you will connect to the Cloud PC and verify its configuration.

## Challenge

Use your existing team group, `GRP-P[n]-Users`, replacing `[n]` with your team number. One Windows 365 Enterprise license is available for this challenge.

### 1. Prepare the user and licenses

- Select a team user who is a member of `GRP-P[n]-Users`.
- Assign the available **Windows 365 Enterprise** license to that user, directly or through group-based licensing. Do not assign more licenses than are available.
- Verify that a **Microsoft E7** license is assigned to the user and that the required Windows Enterprise, Microsoft Intune, and Microsoft Entra ID services are enabled.

### 2. Create and assign the provisioning policy

In the **Microsoft Intune admin center**, create a Windows 365 provisioning policy with the following settings:

| Setting | Required value |
|---|---|
| Policy name | `PP-P[n]-YourPolicyName` |
| Join type | **Microsoft Entra join** |
| Network | **Microsoft-hosted network** |
| Image | A **Windows 11 gallery image** |
| Device name template | A custom name, for example `CPC-P1-%RAND:5%` for team 1 |
| Assignment | `GRP-P[n]-Users` |

> **Important: Use your own team number in the device name template.**
> - The resulting device name must be **5-15 characters long**.
> - Include a **random component of at least five characters**, using `%RAND:5%` or a larger value within the name length limit.
> - For example, team 1 uses `CPC-P1-%RAND:5%`; team 25 uses `CPC-P25-%RAND:5%`.

### 3. Configure local administrator rights

- Create a **Cloud PC configurations** policy with **Enable local admin** enabled.
- Assign it to `GRP-P[n]-Users`. This grants each targeted user administrator rights on their own Cloud PC.

### 4. Verify the Cloud PC

- Monitor provisioning until the Cloud PC reports **Provisioned**.
- Connect as the licensed team user using **Windows App** or a supported browser.
- Verify the custom Windows device name, Intune enrollment, and the user's local administrator rights.

## Pro Tip

Local administrator rights are required for this lab, not a production recommendation. Use standard user permissions unless elevated access is necessary.

## Success Criteria

- The team user has the required licenses and is targeted by the provisioning policy.
- The Cloud PC is **Provisioned**, uses the custom device name, and is enrolled in Intune.
- The user can connect to their Cloud PC and has local administrator rights.

## Learning Resources
- [Deployment overview](https://learn.microsoft.com/en-us/windows-365/enterprise/deployment-overview)
- [Windows 365 requirements](https://learn.microsoft.com/en-us/windows-365/enterprise/requirements)
- [Cloud PC configurations](https://learn.microsoft.com/en-us/windows-365/enterprise/cloud-pc-configurations)
- [Create a provisioning policy](https://learn.microsoft.com/en-us/windows-365/enterprise/create-provisioning-policy)
