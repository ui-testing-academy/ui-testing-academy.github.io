---
layout: article
title: 'UI Automator Viewer'
description: 'Find view information with UiAutomator Viewer.'
permalink:  /:categories/:title/
categories: [platforms, android, tools]
author: alex_zhukovich
---
The **UI Automator Viewer** tool provides a screenshot of an active application on a device or emulator. We can scan and analyse a screen of any application which is installed on the device. 

This application is not a part of Android Studio; it means that we should run it from `{ANDROID-SDK}/tools/bin` folder.

> The **UI Automator Viewer** requires the JDK 8.

![image](/assets/images/platforms/android/tools/ui-automator-viewer/ui-automator-viewer.jpg)

As you can see from the screenshot, visually, this tool has got 3 sections:
* **View Tree** provides a hierarchy of views in the layout
* **Screenshot** shows a screenshot of your app with layout bounds of each view
* **Properties Table** allows you to check any property connected with each view on the screen

The UI Automator Viewer tool provides essential information about the view, like resource ID, package, text, content-description, etc.

We can analyze any application installed on the device or emulator.