---
title: Slack
toc: true
---

This document provides a step-by-step guide for Integrating your MikroCloud portal with Slack using webhooks. This integratin allows you to receive notifications about faults on your devices from MikroCloud directly to your Slack channels.

---

## Prerequisites:
* Access to a Slack workspace with permissions to add apps/ workspaces and manage integrations.

---
## Setting up the Slack Webhook
Now, let's get to the fun stuff and set up a webhook integration.

#### Step 1: Add the Slack Webhook App to your channel.
1. Right-Click on the channel where you want the notifications to be sent.
2. Select `View Channel Details` from the context menu.
<!-- Insert image -->
![picture 0](https://cdn.mkcld.io/8899b9431594f96eeac6b1cc1053fa642e01c46571f3e622fa087a41afde85f3.jpg)  


3. Navigate to `Ingegrations` in the channel details menu.

4. Select `Add an App` to open the application directory.
<!-- Insert Image -->
![picture 1](https://cdn.mkcld.io/aa889a1638c00f7a2020a6f2a37375932f8caac7e32997f001ac7aff3d4f3e4a.jpg)  


5. Search for `"Incomming Webhooks"` in the search bar.
    * See the below screenshot of the specified application.

6. Click on `Install` to the right of the application.

<!-- Insert Image -->
![picture 2](https://cdn.mkcld.io/feb7909d664f580f978c9d826d80a7f0665abf1a50dbfec85f4a133b82d6de2d.jpg)  

:::Note
After you have clicked **Install**, you will be taken to a web page, where you can continue with the integration setup.
:::


7. When on the web page, you will see a page that looks like the below screenshot.
    * Click on the `Add to Slack` button.
<!-- Insert image -->
![picture 3](https://cdn.mkcld.io/e2c8aa1a9ffca679f87b68d64b157643463d3bc29683b6c308a286aa9208de22.jpg)  


8. On the next page, you have to select a channel to which you want the notifications to be pushed from the context menu.

9. Click on the `Add Incomming WebHooks integration` button.
<!-- Insert Image -->
![picture 4](https://cdn.mkcld.io/57e4fd2f6a56e0d52176e236c9580613d724e21dd9bc260a73d404e55f9f07c9.jpg)  


1. Copy the Slack webhook URL.
<!-- Insert Image -->

![picture 5](https://cdn.mkcld.io/bf25bc117f31c63ec2a2e568f7bcfd9f223cf5f328bacdfdee1f76698e42857f.jpg)  


#### Step 2: Integrate your Webhook with MikroCloud
1. From your MikroCloud Dashboard, navigate to `Notifications -> Integrations`
<!-- Insert Image -->
![picture 6](https://cdn.mkcld.io/33450e5a301274b6ad454815c7f7912f6144686a3f5f83015b597c6cb28fed4d.jpg)  


2. On the **Integrations** page, paste the Slack Webhook URL that you copied earlier into the `Slack Notifications` textbox.
<!-- Insert Image -->
![picture 7](https://cdn.mkcld.io/d78fa4ac6b7fedc14f440b9375c54a1bd220f115923fe5dc0fc51f45482765e6.jpg)  


#### Step 3: Test your Integration
1. Click on the `Test` button to the right of your webhook, this will send a test message to your specified channel.


2. Go to your Slack channel and wait for the message to arrive.

   * If it did arrive, it will look something like this:
    <!-- Insert Image -->
    ![picture 8](https://cdn.mkcld.io/68d30f1db8d0f268944421585a489ef821d542b5049daa2539c9387cb30c88e5.jpg)  


    * If it did not arrive, refer to [this](#troubleshooting-your-mikrocloud-slack-integration) documentation.

Your Slack integration is now successfully set up; if any one of your devices experiences a fault, you will be notified from within your slack channel.

---
## Troubleshooting your MikroCloud-Slack Integration
* Verify that your webhook URL is correct.
* Verify that your Slack channel allows external connections.
* Verify that your Slack application is updated.
* Contact support should you still experience any issues.