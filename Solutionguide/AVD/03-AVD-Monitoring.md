# Solutionguide 3: Enable AVD Insights

## Challenge 
Create a **Log Analytics Workspace** to collect all monitoring data for your Resource Group.

Open the **AVD Insights configuration workbook** from your existing host pool and enable monitoring data collection.

## Success Criteria

- AVD Insights is enabled and displays monitoring data from both the AVD control plane and AVD session hosts.
- Network latency and user login attempts are visible within the AVD Insight dashboard.

## Step 1 - Create Log Analytics workspace

1.  Sign in to the [Azure Portal](https://portal.azure.com/).

2.  Search for **Log Analytics workspaces** and select it from the list.

3.  Click **+ Create** to create a new Log Analytics workpsace 

![This image shows where to create a new Log Analytics workspace.](../../Images/SolutionGuide/AVD/03-AVD-LogAnalyticsWorkspace-01.png)

4.  On the Basics page, refer to the following screenshot to fill in the required fields. Select your Subscription, Resource Group and define a Log Analytics workspace name. As Location choose **North Europe**. 

![This image shows where you will enter the information for the Log Analytics workspace.](../../Images/SolutionGuide/AVD/03-AVD-LogAnalyticsWorkspace-02.png)

Then click **Review + Create** and, after successful validation, click **Create** again. 

You cannot proceed until the Log Analytics Workspace has been created.

## Step 2 - Enable AVD Insights for your host pool

1.  Sign in to the [Azure Portal](https://portal.azure.com/).

2.  Search for **Azure Virtual Desktop** and select it from the list.

3.  Under Manage, select **Host pools** and select **Your AVD host pool**.

4. 

![This image shows where you can find the AVD Insights dashboard.](../../Images/SolutionGuide/AVD/03-AVD-Insights-01.png)

5. 

![This image shows where you can open the configuration workbook.](../../Images/SolutionGuide/AVD/03-AVD-Insights-02.png)