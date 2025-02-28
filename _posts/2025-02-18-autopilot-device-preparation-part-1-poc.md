---
title: Autopilot Device Preparation - Part 1 - POC
date: 2025-02-18T21:22:00.000Z
categories: Intune
tags: Autopilot
pin: false
math: false
mermaid: false
toc: true
comments: true
---
INTRO

## Entra join settings

Users need to be allowed to join devices to Microsoft Entra ID. 

Entra ID > Devices > Device Setting > under Users may join devices to Microsoft Entra, select either All or Selected:

1. If All is selected, all users can join their devices to Microsoft Entra ID.

2. If Some is selected, you need to select who will be able to entra join.

![](/assets/img/uploads/entrajoin.png)



## Mobility settings

In order for Windows Autopilot device preparation to work, devices need to be able to enroll in Intune automatically.

Intune > Enrollment > Automatic Enrollment select either All or Selected
1. If Some is selected, only users in the groups specified in the link under Groups can automatically enroll their devices in Intune.

2. If All is selected, all users can automatically enroll their devices in Intune.



![](/assets/img/uploads/autoenrollment-1.png)

![](/assets/img/uploads/autoenrollment-2.png.png)

## Device group

## Autopilot Device Preparation Policy

## Testing
