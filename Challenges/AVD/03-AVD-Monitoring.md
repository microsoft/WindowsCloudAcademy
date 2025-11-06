# Challenge 3: Enable AVD Insights

[Previous Challenge](./02-AVD-RDP-Properties.md) - **[Home](../../readme.md)** - [Next Challenge](../W365/01-W365-Provisioning-CPC.md)

## Introduction

In this challenge, you will enable AVD Insights to collect monitoring data from the AVD control plane (e.g., user connection times, login errors) and session hosts (e.g., system event logs, performance counters like CPU usage) to gain a comprehensive view of your environment’s health and performance.

## Challenge

Create a **Log Analytics Workspace** to collect all monitoring data for your Resource Group.

Open the **AVD Insights configuration workbook** from your existing host pool and enable monitoring data collection.


## Success Criteria

- AVD Insight is enabled and displays monitoring data from the AVD control plan and AVD session hosts.
- You can see your network latency. 

### Learning Resources
- [Create a Log Analytics workspace](https://learn.microsoft.com/en-us/azure/azure-monitor/logs/quick-create-workspace?tabs=azure-portal)
- [Enable Insights to monitor Azure Virtual Desktop](https://learn.microsoft.com/en-us/azure/virtual-desktop/insights)
- [Azure Virtual Desktop Insights glossary](https://learn.microsoft.com/en-us/azure/virtual-desktop/insights-glossary)
- [Use cases for Azure Virtual Desktop Insights](https://learn.microsoft.com/en-us/azure/virtual-desktop/insights-use-cases)
