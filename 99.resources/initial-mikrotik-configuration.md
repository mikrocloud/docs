---
title: "Initial Configuration"
toc: false
---

This section will guide you through the initial setup of your MikroTik device, including:

* Resetting and clearing any existing configurations.
* Establishing an Internet connection.
* Upgrading the device to the latest firmware.

### Step 1: Verify That Your MikroTik Router Is Functioning

Plug in your MikroTik router and wait for it to boot up. The boot process typically takes a few seconds to a minute.
Once booted, the device should provide an indication, such as a display on the front LCD panel, an audible beep, or flashing lights.

### Step 2: Physically Connect the MikroTik Router

Connect your MikroTik router to the upstream device using an Ethernet cable.
Plug one end of the cable into the MikroTik's ETH1 port on the front panel.
Connect the other end to the Ethernet port of the upstream device.

### Step 3: Reset the MikroTik Router to Factory Settings

There are multiple methods to reset your MikroTik router. Choose the method that best suits your needs.

#### Option 1: Reset via the LCD Panel

Using the LCD panel on the front of the MikroTik router, locate the option to reset the device to factory settings.
Enter the 4-digit PIN code when prompted.

The **default PIN is 1234**.
:::note
Note: If you haven’t changed your PIN, use this code.
:::
The router will reboot, and after approximately 10-20 seconds, it should display a message indicating:
* The local IP address is **192.168.88.1**.
* An additional IP address may also be shown, which can be ignored for now.

#### Option 2: Reset via the Winbox Utility

MikroTik provides a utility program called Winbox that allows you to find devices on your network and manage their configuration.
Detailed instructions for downloading and using Winbox can be found [here](https://help.mikrotik.com/docs/display/ROS/WinBox).


### Establish Internet Access
Before proceeding further, the MikroTik itself will need to be able to reach the internet.
##### Check for an IP Address
Using Winbox click `IP` on the left-side, main menu. From the sub menu, click `DHCP Client`.

If you see an entry that shows **ether1** in the interface column, and an IP address that is not all `0's (0.0.0.0)` in the `IP Address` column, then you can skip to the next step and proceed to [Confirm Internet Access](#confirm-internet-access)


#### Get an IP address with DHCP
1. clcik on the `Add New` button.
2. Type **defconf** in the comment field.
3. Select **ether1** in the Inteface drop-down menu.
4. Ensure that `Use Peer DNS` is ticked.
5. Click `Apply`
6. click `OK`

You should now see an entry and there should be a valid IP address in the **IP Address column**

#### Confirm Internet Access
Using Winbox, open a terminal by clicking on the `New Terminal` button.
* You may need to enter the username and password you set for the device earlier.

When you have logged in and see a command prompt, type in the following command

`ping mkcld.io`
* Then press **Enter**

If you see a continuous stream of pings, then you have internet access and you can continue.

### Update Firmware On The MikroTik
Using Winbox, use the left-side menu and choose **System --> Packages**

1. Click on `Check for Updates`
2. Select **stable** from the `Channel` drop down menu.
3. Click the `Check for Updates` button.
4. Note the **Installed Version** and **Latest Version** numbers.

### Update Current Major Version of the Firmware
If the version numbers don't match, download & install the latest version.

:::warning
The device will restart after the new firmware is installed. Once that's done, log in and return to the **Check for Updates page**.
:::

#### Upgrade to the Latest Major Version
If the Channel drop-down menu includes an "upgrade" option, select that and then download & install the most recent major version.

Return to the `Check for Updates` page one last time and ensure that you have the latest version of the most recent upgrade.

:::note
More detailed information on upgrading can be found at http://help.mikrotik.com/docs/display/ROS/Upgrading+and+installation
:::


## Congratulations on Setting Up Your Initial Access
🎉 Congrats, your MikroTik router is now ready to add to MikroCloud, you can go to [this](/documentation/getting-started/adding-your-first-router) page to add your router to your MikroCloud Portal.
