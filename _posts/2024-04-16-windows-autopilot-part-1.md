---
title: Windows Autopilot - Part 1 - Setup
date: 2024-04-16T16:18:00.000Z
categories: "[Intune, Autopilot]"
tags: "[configuration]"
image: /assets/img/uploads/microsoft_intune-logo_brandlogos.net_6p2c7.png
pin: false
math: false
mermaid: false
toc: true
comments: true
---
1. Requirements
2. Configure auto-enrollment

   This is a Microsoft Entra settings that will allow the device to find the mdm url automatically to do so :

   [Entra](entra.microsoft.com) > Settings > Mobility > Microsoft Intune


3. Create dynamic group

   `(device.devicePhysicalIDs -any (_ -startsWith "[ZTDid]"))`

   `(device.devicePhysicalIds -any (_ -eq "[OrderID]:Luxembourg"))`
4. Create a deployment profile
5. Create an Enrollment Status Page profile
6. Testing

[](https://learn.microsoft.com/en-us/autopilot/software-requirements)

[](https://learn.microsoft.com/en-us/autopilot/configuration-requirements)

[](https://learn.microsoft.com/en-us/autopilot/configuration-requirements)

[](https://learn.microsoft.com/en-us/autopilot/configuration-requirements)

[](https://learn.microsoft.com/en-us/autopilot/configuration-requirements)
