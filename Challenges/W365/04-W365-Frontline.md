# Challenge 4: Deploy Windows 365 Frontline Shared Desktop or Cloud Apps (preview)

[Previous Challenge](./03-W365-App-Deployment.md) - **[Home](../../README.md)**

## Introduction

**Windows 365 Frontline** in shared mode provides a cost-effective way for shift-based workers to access a secure **dedicated Cloud PC desktop** that resets after each session, ensuring privacy and flexibility. 

**Windows 365 Cloud Apps (preview)** lets users stream only the apps they need, like Office or custom business tools, without provisioning a full desktop, reducing complexity and cost for task-based roles.

A Windows 365 Frontline license can be used in shared mode for dedicated desktops or for delivering cloud apps.

## Challenge

In this challenge, you can choose to deploy your single Windows 365 Frontline license either in **dedicated desktop mode** or in **cloud apps mode** (Preview). 

Each participant has **only one** Windows 365 Frontline license available, so decide which option you would like to test:

### Option 1 - Windows 365 Frontline Shared in dedicated Desktop mode

- Create a provisioning policy
- Experience: **Full Cloud PC desktop**
- License type: **Frontline**
- Frontline type: **Shared**
- Your cloud PC should be set up to use **Microsoft Hosted Networks** and only supports **Microsoft Entra Join** for identity and access.
- Region: **North Europe**
- **Make sure your Cloud PC has a custom name that is not the default, for example: CPC-P1-%RAND:5%"**
- Assign your user group, but ensure the number of Cloud PCs is set to **one**.

### Option 2 - Windows 365 Frontline Shared in Cloud Apps mode (Preview)

- Create a provisioning policy
- Experience: **Cloud Apps (Preview)**
- License type: **Frontline**
- Frontline type: **Shared**
- Your cloud PC should be set up to use **Microsoft Hosted Networks** and only supports **Microsoft Entra Join** for identity and access.
- Region: **North Europe**
- **Make sure your Cloud PC has a custom name that is not the default, for example: CPC-P1-%RAND:5%"**
- Assign your user group, but ensure the number of Cloud PCs is set to **one**.

## Success Criteria

### Option 1 - Windows 365 Frontline Shared in dedicated Desktop mode
- Your Cloud PC in dedicated desktop mode is now available, and you can log in.
- You will receive a new user profile each time you sign in.

### Option 2 - Windows 365 Frontline Shared in Cloud Apps mode (Preview)
- Your Cloud PC in Cloud Apps mode is now available, and you have published example apps such as Word and Notepad.
- You can log in and start using a Cloud app.

## Learning Resources
- [What is Windows 365 Frontline?](https://learn.microsoft.com/en-us/windows-365/enterprise/introduction-windows-365-frontline)
- [Create provisioning policies](https://learn.microsoft.com/en-us/windows-365/enterprise/create-provisioning-policy)
- [Windows 365 Cloud Apps (preview)](https://learn.microsoft.com/en-us/windows-365/enterprise/cloud-apps)
