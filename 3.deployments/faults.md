---
title: "Faults"
toc: false
---

Tis document provides an overview of the different types of faults that are logged and monitored by MikroCloud. it covers how faults are identified, categorized and logged, along with a detailed look at the **Recent Faults Dashboard and the Faults Dashboard**, as well as how it can be used to monitor these events.

---
## What are Faults?
Faults represent disruptions or issues present at your sites/ network, such as loss of connetivity, service degradation or hardware failures. These events are automatically detected based on thresholds and trigger conditions.


### Faults are Logged in the following ways:
| Condition | Description |
| --- | --- |
| Heartbeat Checks: | Sites are configured to check in with MikroCloud every **30 seconds**. These checks are known as **Heartbeats**.|
| Fault Condition trigger: | If a site misses **10** consecutive heartbeats (a period of 5 minutes), a fault condition is recorded. These system identifies this as the threshold for detecting a potential service disruption. |
| Start Time Calculation: | The start time of a fault condition is backdated by **5 minutes** from the current time, representing when the first heartbeat was missed.|
| Clearing the Fault Condition: | The fault condition is automatically cleared when the next hearbeat is successfully received, indicating that the site has re-established communication. |
| Recorded Downtime: | The downtime is calculated as the difference betwen the fault condition's start and end times, providing an accurate measure of the site's unavailability. If this downtime falls within your configured **business schedule**, this will be added to yor configured **SLA report**. |

<!-- * Sites send **heartbeat** signals to MikroCloud every 30 seconds.
* If **10 consecutive** heartbeats are missed (equivalent to 5 minutes), a fault condition is recorded.
* The start time of a fault is backdates by 5 minutes to the time when the first heartbeat was missed.
* The fault is cleared when the next heartbeat is successfully received.
* Downtime is calculated as the time difference between the start and end of the fault condition. -->

:::Note
For **SLA Schedules**, see the following [section]().

For **Business Hour Policies**, see this [section]().
:::

---
## Types of Faults
Fults are categorized based on the nature of the issue.

| Fault Type | Description |
| --- | --- | 
| **WAN Tunnel Offline** | Thiw fault occurs when the WAN Tunnel(s), responsible for site communication, goes offline. This is typically due to connectivity issues or ISP disruptions. |
| **Site Rebooted** | A site reboot fault is logged when a monitored site undergoes a restart, either due to manual intervention or an unexpected issue. |
| **Site Offline** | This fault is recorded when an entire site loses connecitivty and becomes unresponsive. It indicates a total loss of communication between the site and the monitoring system. |

---
## Recent Faults Dashboard
The Faults Dashboard is a central interface for monitoring real-time and historical faults across all sites. It displays critical information, allowing for quick response and analysis.

* This dashboard will show a chronological list of faults that have occurred, including timestamps and fault types.
* A visual representation of the severity and impact of each fault.

#### Accessing the Recent Faults Dashboard
1. From your `Dashboard`, you will see a tile called **Recent Faults**, this is the recent faults dashboard discussed above.
<!-- Insert Image -->
![picture 0](https://cdn.mkcld.io/088b5412d4a1b4e3dd990041e2af5397622630703ff5503258033282b3491cd5.jpeg)  

:::Note
If you have not had any faults within **24 hours**, there will be no entries here.
:::

---
## Site-Specific Faults
This page provides site-specific insights into the historical performance and reliability of your device. This page will also display a larger amount of faults than the **Recent Faults** tile on your Dashboard.

#### Accessing Site-Specific Fault Event Logs
1. From your **Dashboard**, navigate to your site list.
<!-- Insert Image -->
![picture 0](https://cdn.mkcld.io/8add84ee5c781c9eb605135f7a72d5df40196d048a45f31f34331e89922ce26f.jpg)  

2. Click on the site you wish to view the fault events log for.

3. From your site's **Overview page**, click on the Fault Event Log.
<!-- Insert Image -->
![picture 1](https://cdn.mkcld.io/301fda31f26d8c4bf79bebd684b02e9c62cf39ee42f9ead278ca4f61ec027962.jpeg)  

4. You have now navigated to your site's fault event log.
   * Here is where you can scroll and view all of the faults that have happened at your site.
<!-- Insert Image -->
![picture 2](https://cdn.mkcld.io/c94a7f7e3b46d28cba7aa1086db751edb4d8e29e05d6636c7487b2cd91456585.png)  

