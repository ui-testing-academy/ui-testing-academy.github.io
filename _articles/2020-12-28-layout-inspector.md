---
layout: article
title: 'Layout Inspector'
description: 'Find view information with Layout Inspector.'
permalink:  /:categories/:title/
categories: [platforms, android, tools]
author: alex_zhukovich
---
The **Layout Inspector** tool has the ability to do UI debugging and analysis of the User Interface for UI testing. The "Layout Inspector" is a part of Android Studio; this means that you cannot run it as a standalone application. You can run it via the "Tools -> Layout Inspector" menu.

This tool allows us to analyze different applications; however, it depends on the permissions of the device or emulator. We can analyze any app if the device has root permissions; otherwise, we can only explore debug versions of applications (usually these are apps we are developing). An Android emulator without Google Play Services delivered with ROOT permissions; this means that we can explore any application on these emulators. However, we can only analyze debug versions of apps installed on any device or emulator without *ROOT* permissions.

**Note:** Layout Inspector from this tutorial is available in Android Studio 4.0 or higher.

![image](/assets/images/platforms/android/tools/layout-inspector/layout-inspector.png)

As you can see from the screenshot, visually, this tool has got 3 sections:
* **View Tree** provides a hierarchy of views in the layout
* **Layout Preview** shows a "live screenshot" of your app with layout bounds of each view
* **Attributes Panel** allows you to check any property connected with each view on the screen

A new version of the **Layout Inspector** has a "Live Update" feature, which helps us see real-time changes to the app's active screen. If we change the screen on the device or emulator, it will be automatically updated in the "Layout Inspector" tool. This feature is enabled by default (![image](/assets/images/platforms/android/tools/layout-inspector/layout-inspector-menu-with-live-update.png)), but you can easily turn it off in the main window of "Layout Inspector".

This feature speeds up the analysis of different screens because we don't need to "ask" about the new snapshot manually. However, we have one important drawback at the current version of Android Studio (4.1.1):

There is no possibility to save a captured snapshot with/without "Live Updates" features.