---
title: "Installable PWA"
---

## What is a PWA?

Progressive Web Apps (PWAs) are web applications that are regular web pages or websites, but can appear to the user like
traditional applications or native mobile applications. The application type attempts to combine features offered by
most modern browsers with the benefits of a native application experience.

## How to Install the MikroCloud PWA

MikroCloud's portal is a PWA, which means you can install it on your device and use it like a native application.
Once installed, the PWA will appear in your device's application list, and you can launch it from there.
Authentication is handled outside the PWA, so you will be redirected to https://oauth.mikrocloud.com to log in.

To install the MikroCloud PWA, look for the install button in the address bar of your browser.
The button will look like the image below:

![PWA Installation](https://cdn.mkcld.io/863955d959c80fcc389fd0002032b566245954051d25be0fc79f432270ec6522.png)

Once you have installed the PWA, you can launch it from your device's application list.

## PWA Updates

A service worker is started when you launch the PWA, and it will check for updates in the background.
If an update is available, the service worker will download the new version and prompt you to install it.

When an update is available, the PWA will display a message like the one below:

![PWA Update](https://cdn.mkcld.io/38e4f9cc8afe2cb07023c3244c683625130dd142fc78b086cae8cd8223ae7676.png)  
