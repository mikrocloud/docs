---
title: Orchestration Log
toc: false
---

The **Orchestration log** is a powerfull features that provides the transparent visibility into the actions performed by MikroCloud on your devices. It records and displays the scripts, API calls and automated tasks executed across your device fleet, allowing for thorough monitoring and troubleshooting.


This document will help you understand how to use the Orchestratino Log to track changes, review executed API calls and maintain control over you network operations.

---
## Understanding the Orchestration Log interface
The Orchestration log is presented as a table with the following columns:

| Description                                                                                       | Created/ Run                                                                              | Status                                                                  |
| :------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------: | :----------------------------------------------------------------------: |
| The name or purpose of the action, such as **"Create Configuration Backup"** or **"Site Reboot"** | The dates and times when the action was initiated and when it was executed, if applicable | Indicates whether the action is still **Pending, Completed or Failed.** |

#### Example of Log Entries:
![picture 0](https://cdn.mkcld.io/2b742cd848f79f99fd2ea815d4f38fd70ae5e193cf2d5819712508737173fb9d.png)  

---
## Accessing the Orchestration Log
#### Step 1: Navigate to your Site
1. From your Dashboard, navigate to your `Sites`.
<!-- Insert Image -->
![picture 1](https://cdn.mkcld.io/46a1fa4982767eb349284359180b94a39fa19c6fd46df760467468150659955d.jpg)  

2. Click on the specific site for which you want to see the **Orchestration Log**.
<!-- Insert Image -->
![picture 2](https://cdn.mkcld.io/810a882b9a2599ac18f8cefeb8fb9f567ae8a4ab3f5b3fa39b44653b47fa1ef4.png)  


3. When on the Site's Overview Page, click on `Orchestration Log`, this will take you to the device's orchestration log page.

![picture 3](https://cdn.mkcld.io/c043da971c6dc33f79fe375262ea86db7397d62bce2af6a1bcc5b5cc39ba33bb.jpg)  

4. The **Orchestration Log:**
![picture 4](https://cdn.mkcld.io/c412d2909c63f25e2c2aeb21466d7340c9a9275159a64991e0bac26702874133.png)  

## Viewing an Expanded Log Entry
1. Clicking on an entry in the **Orchestration log** opens a detailed view with expanded information about that specific action that was executed.

#### The expanded log entry provides:
| Action: | Description: |
| ---| ---|
|Timestamped Events:| A breakdown of each step in the process, from job creatioin to completion or failure.|
| Device Information: | Details about the target device(s) involved, including site ID, device name, and associated metadata. |
| Job Context: | A JSON payload containing key data points, such as the job ID, Customer ID, idempotency key, and script content if applicable. |
| Status Message: | Specific messages indicating the progress or outcome of the job, such as "Job created", "Downloaded", "Expres execution requested" or "Failed". |

#### Examples for Log Expanded Log Entries
![picture 5](https://cdn.mkcld.io/1c9c60cf9718d3328f9bacbf5a0194f1f35c7ec5f439c1a7d9a5830e7c144ea5.png)  

2. By hovering over a specific log entry, you will see a small button pop up called `Expand`, this will expand the JSON payload for you to inspect
<!-- Insert Image -->
![picture 6](https://cdn.mkcld.io/b7921e6ffa9e683d319a69e46de2d9f082ed83f348ff81f2b93dfa616ddd805a.jpg)  

* From this page, you can also copy the entire JSON payload should you need to use it for further analysis or troubleshooting.
---

This guide provides a comprehensive overview of how to navigate and use the Orchestration Log feature in MikroCloud. By understanding and utiliziing this feature, you can gain deeper insights into the automated actions, manage your network more effectively and ensure better control and transparency over device operations.