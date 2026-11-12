# Challenge 3: Enable AVD Insights

[Previous Challenge](./02-AVD-RDP-Properties.md) - **[Home](../../README.md)** - [Next Challenge](../W365/01-W365-Provisioning-CPC.md)

## Introduction

In this challenge, you will enable **Azure Virtual Desktop Insights** for your existing pooled host pool. You will collect connection diagnostics and session host performance data in a **Log Analytics workspace**, then use the Insights dashboard to explore user connections, network latency, and resource usage.

## Challenge

Use the host pool and session hosts from the previous challenges.

### 1. Configure diagnostic data collection

- Create a **Log Analytics workspace** in your team's resource group (`RG-WCA-PUNK[n]`) in **North Europe**, replacing `[n]` with your team number.
- Open **Insights** on your host pool and launch the **configuration workbook**.
- Use **Resource diagnostic settings** to enable the required diagnostics for both the **host pool** and the **AVD workspace**, sending them to your Log Analytics workspace.

### 2. Configure session host monitoring

- In **Session host data settings**, create a **Data Collection Rule (DCR)** using the workbook's recommended performance counters and Windows Event Logs.
- Select your Log Analytics workspace as the destination.
- Use the workbook to install the **Azure Monitor Agent (AMA)** on every session host and associate each host with the DCR. Complete any managed identity prerequisites indicated by the workbook.
- Refresh the workbook and resolve any remaining configuration warnings.

### 3. Generate activity and explore Insights

- Connect as a team user and use a published application or desktop to generate monitoring data.
- Open the **Insights dashboard**, select your host pool and an appropriate time range, and review connection activity, network latency, and session host CPU and memory usage.

## Pro Tip

Monitoring data is not available immediately. Allow time for ingestion and refresh the dashboard. If data remains missing, check the configuration workbook, diagnostic settings, and agent/DCR configuration.

## Success Criteria

- The configuration workbook confirms that resource diagnostics and session host data collection are configured.
- Insights displays user connection activity and network latency from a test connection.
- Session host performance data, including CPU and memory usage, is visible.

## Learning Resources
- [Create a Log Analytics workspace](https://learn.microsoft.com/en-us/azure/azure-monitor/logs/quick-create-workspace?tabs=azure-portal)
- [Enable Insights to monitor Azure Virtual Desktop](https://learn.microsoft.com/en-us/azure/virtual-desktop/insights)
- [Azure Virtual Desktop Insights glossary](https://learn.microsoft.com/en-us/azure/virtual-desktop/insights-glossary)
- [Use cases for Azure Virtual Desktop Insights](https://learn.microsoft.com/en-us/azure/virtual-desktop/insights-use-cases)
