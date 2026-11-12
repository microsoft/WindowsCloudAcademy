# Challenge 2: Configure RDP Properties

[Previous Challenge](./01-AVD-Multi-Session-Hostpool.md) - **[Home](../../README.md)** - [Next Challenge](./03-AVD-Monitoring.md)

## Introduction

Azure Virtual Desktop enables you to configure and customize Remote Desktop Protocol (RDP) properties for a host pool. 

Customizing a host pool's Remote Desktop Protocol (RDP) properties, such as multi-monitor experience and audio redirection, lets you deliver an optimal experience for your users based on their needs. 

For security reasons, Microsoft disables clipboard, drive, USB, and printer redirection by default for newly created AVD host pools.

If you'd like to change the default RDP file properties, you can customize RDP properties in Azure Virtual Desktop by either using the Azure portal or by using the -CustomRdpProperty parameter in the Update-AzWvdHostPool cmdlet.

## Challenge 

Use the pooled host pool from Challenge 1. 
 
In this challenge, enable clipboard redirection in both directions. You can optionally enable other redirections required for your use case.

- Pooled (Desktop / Remote App) Host pool 
    - Allow Multiple Displays
    - Smart Sizing should be enabled
    - Enable clipboard redirection in both directions
    - Optionally enable camera, microphone, client drive (including mapped network drives), USB, or printer redirection
    - Keep any redirections you do not need disabled

Preserve the existing Microsoft Entra ID SSO settings. Save the changes, disconnect, and reconnect to test the updated settings. If a redirection remains blocked, check the session-host policies and client settings.

## Success Criteria

- You can copy and paste text in both directions between your local device and the remote desktop or a published RemoteApp.
- Any additional redirections you enabled work as intended; unneeded redirections remain disabled.

## Learning Resources
- [Customize RDP Properties](https://learn.microsoft.com/en-us/azure/virtual-desktop/customize-rdp-properties)
- [Supported RDP Properties](https://learn.microsoft.com/en-us/windows-server/remote/remote-desktop-services/clients/rdp-files)
