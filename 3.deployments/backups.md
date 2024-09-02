---
title: "Backups"
toc: true
---

This document provides an overview of how to manage configuration backups within MikroCloud. It covers how backups are schedules, viewed and compared to ensure that your device configurations are consistently saved and properly managed.

---
## Overview
Configuration backups are crucial for maintaining the integrity and recoverability of your device settings. In MikroCloud, configuration backups are made daily at specific times, this helps to ensure that you have up-to-date snapshots of your devices and their configurations should anything go wrong.

### Backup Schedules:
| Item | Description|
| --- | --- |
| **Frequency:** | Backups are performed daily. |


---
## Managiong Configuration Backups
You can access the backup scripts and manage backups in **2 different ways**

### Method 1: From the Device Overview Page
1. From your dashboard, navigate to your `Sites`.
<!--  Insert image -->
![picture 0](https://cdn.mkcld.io/8add84ee5c781c9eb605135f7a72d5df40196d048a45f31f34331e89922ce26f.jpg)  

2. Select the site you want to check the backups for.

3. From your device's Overview page, click on `Config Backups`.
<!-- Insert Image -->
![picture 0](https://cdn.mkcld.io/c1c8846eb922cb4b5512bbd8e5709b4e34b6911278808f89e70d91870deeeaa7.jpeg)  

4. This will open up a page that will show you all of the backups made for the device.


#### On this page, you can do the following:
1. View Backups by clicking on the `View` button.
2. Make a manual backup by clicking on `Backup Site` button at the top of the page.
3. Compare Backups, this will take you to the `Scripts -> Backup Scripts` page, where you can compare multiple backups with each other.
4. Download a backup by clicking on the `Download` button.

<!-- Insert Image -->
![picture 1](https://cdn.mkcld.io/a6a19c01400640e3b3dec4e6faf6d5e987aa9789b84cd47fe7c083b75d452167.jpeg)  

### Method 2: From Your Dashboard
1. From your dashboard, navigate to `Scripts -> Backup Scripts`.
<!-- Insert Image -->
![picture 2](https://cdn.mkcld.io/84cc1c1ac324ee53346855dc942b37532225ab2c1bbcc79346f8827aad839336.jpeg)  


2. Search for the device which you want to view the backups for.
3. Click on the checkbox for the device.
<!-- Insert image -->


:::Note
Clicking on the name of the device will take you to the site's `Overview Page`.
:::

4. After selecting the device, a list of backups will open up.
* You can select either 1 backup, or multiple backups. (When selecting multiple backups, these will automatically be compared to each other.)

<!-- Insert Image -->

#### Features
<!-- * All lines/ items <span style="color: red;">highlighted in  red</span> means that there is a difference in the configuration.
* <span style="background-color: red; color: white;">This text is highlighted in red.</span> -->
* All lines/ items <span style="background-color: rgba(255, 18, 18, 0.7); color: white;">highlighted in  red</span> means that there is a difference in the configuration.