---
layout: default
title: Review License Allocation
nav_order: 1
parent: Licensing
---

# Review License Allocations
{:.no_toc}

**Cadence** <span class="label cadence">Weekly</span>

**Sites** <span class="label all">all</span>

|                                  		                  | Initial | Recurring |
|---------------------------------------------------------|---------|-----------|
| <i class="far fa-clock fa-sm"></i> **Estimated Time**   | 20 min | 10 min    |

Benefits:

  - Ensure licenses are available
  - Plan for license growth

## Goal
{:.no_toc}
The goal of this activity is to evaluate license growth and needs using the built in **License Monitor** application. 

## Table of Contents
{:.no_toc}

* TOC
{:toc}

-------------------------

## License Monitor

This page leverages the **License Monitor**. Please refer to the [License Monitor](../tooling/license_monitor.md) page for an overview and relevant documentation links.

### Confirm License Monitor is Operational

Navigate to the **Monitoring apps** and select the **Details** button (info icon) on the **License Monitor** application. Confirm that the application's data is up-to-date.

![license_monitor_operational.png](images/license_monitor_operational.png)

If the **License Monitor** is not up-to-date, please refer to the [License Monitor Documentation](../tooling/license_monitor.md#documentation) for configuration details and troubleshooting steps.

-------------------------

## Check License Growth

First check the QMC to see how many total licenses are available for Professional and Analyzer users. Navigate to the **License Management** section of the QMC. 

![Analyze_Audit_License_Allocations_QMC_License_Management.png](images/Analyze_Audit_License_Allocations_QMC_License_Management.png)

Ensure **License Usage Summary** is selected on the right, and then check the total licenses on the left for both **Professional** and **Analyzer**.

![Analyze_Audit_License_Allocations_QMC_License_Management_UserMaximums.png](images/Analyze_Audit_License_Allocations_QMC_License_Management_UserMaximums.png)

Next, navigate to the **Monitoring Apps** section of the QMC, which will route to the Hub.

![Analyze_Audit_License_Allocations_QMC_MonitoringApps.png](images/Analyze_Audit_License_Allocations_QMC_MonitoringApps.png)

Select the **License Monitor** application.

![Analyze_Audit_License_Allocations_QMC_MonitoringApps_LicenseMonitor.png](images/Analyze_Audit_License_Allocations_QMC_MonitoringApps_LicenseMonitor.png)

Select the **Overview** sheet.

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview.png)

Click the **Duplicate** button on the toolbar.

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_Duplicate.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_Duplicate.png)

Edit the **User Timeline** chart by selecting it and deleting the **Access Type** measure.

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AccessType.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AccessType.png)

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AccessType_Delete.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AccessType_Delete.png)

With **Access Type** removed, open the **Measures** pane and select **Add Trend** under the **User Accessing Apps** measure. 

{::options parse_block_html="true" /}
<div class="card">
<div class="card-header">
<i class="fas fa-exclamation-circle fa-sm"></i> Note
</div>
<div class="card-body">
<p>This feature was introduced in the February 2020 release, and is documented [here](https://help.qlik.com/en-US/sense/Subsystems/Hub/Content/Sense_Hub/Measures/trend-lines.htm){:target="_blank"}. If the site is not on this release or later, alternative methods can be explored [here](https://community.qlik.com/t5/Qlik-Sense-Documents-Videos/Calculating-trend-lines-values-and-formulas-on-charts-and-tables/ta-p/1479463){:target="_blank"} using functions like `linest_m()` and `linest_b()` functions.</p>
</div>
</div>

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AddTrend.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AddTrend.png)

Select **Linear** as the **Trend Type**.

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AddTrend_Linear.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AddTrend_Linear.png)

Move the **Allocation Changed in 7 days** table to the left and add a **Filter Pane** in the empty space to the left of the alterered **User Timeline** chart.

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_DragFilterPane.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_DragFilterPane.png)

Select **Dimension** and choose **Access Type**.

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AddAccessType.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AddAccessType.png)

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AccessTypeAdded.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AccessTypeAdded.png)

Click **Done**.

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_DoneButton.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_DoneButton.png)

Select `Analyzer` in the filter pane and view/analyze the growth rate in analyzer app usage. To do this, grab two points on the chart that intersect with Y axis grid lines. In the sample below these two values are '20' and '30' respectively. Since the two points are 4 months apart, one can deduce that the linear growth rate is approximately 2.5 new analyzers per month. 

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AnalyzerTrend.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_AnalyzerTrend.png)

Repeat for **Professional**. In this sample, the growth line is flat. 

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_ProfessionalTrend.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_ProfessionalTrend.png)

In this exercise, it is apparent that 100 analyzer licenses are available. Since the most recent month shows '32' in use, we can expect that licenses will max out in  (100-32)/2.5  or  ~27 months. These are of course estimates without any other variables in play.

The work done to customize the sheet is auto-saved. To make the sheet clear and readily accessible for next time, rename the sheet to **User License Trend** by clicking in the white space above the app objects as shown by the arrow in the image below, then alter the label to **User License Trend**.

![Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_UserLicenseTrend.png](images/Analyze_Audit_License_Allocations_HUB_License_Monitor_App_Overview_UserLicenseTrend.png)

**Tags**

#weekly

#licensing

#license

#users

#license_monitor

&nbsp;
