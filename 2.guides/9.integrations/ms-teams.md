---
title: MS Teams
toc: true
---

<!-- :::Warning
This page is currently being worked on, please check back frequently to see when it updates.
::: -->

This document provides a step-by-step guide for integrating your MikroCloud portal with Microsoft Teams using webhooks. This integratin allows you to receive notifications about faults on your devices from MikroCloud directly to your Microsoft Teams channels.

---
## Prerequisites
* Access to a Microsoft Teams workspace with permissions to manage channels and add connectors.

:::warning
Some Office365 subscriptions do not allow external connectors, please check that your subscription allows connectors.
:::

---
## Setting up the Microsoft Teams Webhook
Now, let's get the webhook integration up and running.

#### Step 1: Create Webhook
1. Open Microsoft Teams and navigate to the channel where you want to receive the notifications.
2. Right-Click on the channel name and select `Manage Channel`.

<!-- Inser Image -->
![picture 0](https://cdn.mkcld.io/2ec312598d56c6153f021fa1c3d0a49e4373187249a235101f1d5e5c4e0bdef3.jpg)  

3. Expand the `Connectors` section within the channel `settings` menu.
4. Click on `Edit` to open the connectors configuration page.
<!-- Insert Image -->
![![picture 1](https://cdn.mkcld.io/d83c7e8c95bc6949c2c5655e6e75d25336625b02ea61f5ed05d1ff83eeaa21f0.jpg)  
 1](https://cdn.mkcld.io/fe64a51fc18b1656a631f160bf99a1b508df81916450812181561f306b6983f3.jpg)


5. On the new page, search for **Incomming Webhook** in the search bar.
6. Click `Add` Next to the `Incomming Webhook` integration option.
![picture 3](https://cdn.mkcld.io/f756f0879f3f48f5e722e23dd7b2209cb1f997dd6621c0916a4edf5bf2bcbdee.jpg)  

7. On the new page, you will have to click on `Add` again.
![picture 4](https://cdn.mkcld.io/0e4477c9cc789efe3b748687ad6c51a5316637f6bd395fc7dda2c2d1a4596a59.png)  

After clicking **Add**, you will be redirected to a configuration page where you can set up the webhook.

8. On the configuration page, click `Configure` to start setting up the webhook.
<!-- Insert Image -->
![picture 5](https://cdn.mkcld.io/df9464f6f4b21233e5e1750d1ba9d9b31183acf5fe4025c43c77449672547d5a.jpg)  



9. Give the webhook a name (e.g. **"MikroCloud Notifications"**) and customize the image if needed.
10. Click `Create` to finalize the configuration.
<!-- Insert Image -->
![picture 6](https://cdn.mkcld.io/4e5fae30e55768a43beb2a975560590bf6ba1e6adc4fd08fda1b9c3a6f65cb1f.jpg)  


11.  Copy the webhook URL that is provided.
<!-- Insert Image -->
![picture 7](https://cdn.mkcld.io/f354768eef6f9aeff2e31893cc73475b88d7a05d089bf698f79000e8d2b0b2cc.jpg)  


#### Step 2: Integrate your Webhook with MikroCloud:
1. From your MikroCloud Dashboard, navigate to `Notifications -> Integrations`.
<!-- Insert Image -->
![picture 8](https://cdn.mkcld.io/ea7661a4640adf86a2f03958ca9a9bdcd886b233112929f9266d2e84d0afd49a.jpg)  


2. On the **Integrations** page, paste the Microsoft Teams webhook URL that you copied earlier into the `Teams Notifications` textbox.
<!-- Insert Image -->
![picture 9](https://cdn.mkcld.io/db0b9908aa44e200f49ebb4562b6fa9c8a1fca02989f684c11dd465fdf49a8c2.jpg)  


#### Step 3: Test your Integration
1. Click on the `Test` button next to your webhook URL to send a test message to your specified Teams channel.
2. Go to your Microsoft Teams channel and wait for the test message to arrive.
    * If it did arrive, the message will look something like this:
    <!-- Insert Image -->
    ![picture 10](https://cdn.mkcld.io/6a3b4d6782a5d944ef6d1fb5c6102374b471dc935d13e79731c85d0c4c83cbea.png)  

    * If it did not arrive, refer to [this](#troubleshooting-your-mikrocloud-teams-integration) documentation.

Your MS Teams integration is now successfully set up; if any one of your devices experiences a fault, you will be notified from within your Teams channel.

---
## Troubleshooting your MikroCloud-Teams Integration
* Verify that your webhook URL is correct.
* Verify that your MS Teams channel allows external connections.
* Verify that your Slack application is updated.
* Contact support should you still experience any issues.