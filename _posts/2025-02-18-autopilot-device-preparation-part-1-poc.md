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
This step by step tutorial guides through using Intune to perform a Windows Autopilot device preparation user-driven scenario when the devices are Microsoft Entra joined.

The purpose of this tutorial is a step by step guide for all the configuration steps required for a successful Windows Autopilot device preparation user-driven Microsoft Entra join deployment using Intune.

## Entra join settings

Users need to be allowed to join devices to Microsoft Entra ID. 

**Entra ID > Devices > Device Setting > under Users may join devices to Microsoft Entra, select either All or Selected**

1. If All is selected, all users can join their devices to Microsoft Entra ID.
2. If Some is selected, you need to select who will be able to entra join.

## Mobility settings

In order for Windows Autopilot device preparation to work, devices need to be able to enroll in Intune automatically.

**Intune > Enrollment > Automatic Enrollment > under MDM user scope, select either All or Selected**

1. If All is selected, all users can automatically enroll their devices in Intune.
2. If Some is selected, only users in the groups specified in the link under Groups can automatically enroll their devices in Intune.



## Device group

Windows Autopilot device preparation uses a device group as part of the Windows Autopilot device preparation policy. The device group specified in the Windows Autopilot device preparation policy is the device group where devices are added automatically during the Windows Autopilot device preparation deployment. The device group specified in the Windows Autopilot device preparation policy needs to be an assigned security group.

Devices are automatically added to this device group during the Windows Autopilot device preparation deployment

This group need to have service principal **Intune Provisioning Client** as owner

![](/assets/img/uploads/autopilotgroup.png)

If the service principal does not exist you can create it using powershell :

`Install-Module Microsoft.Graph.Authentication`

`Install-Module Microsoft.Graph.Applications`

`Connect-MgGraph -Scopes "Application.ReadWrite.All"`

`New-MgServicePrincipal -AppID f1346770-5b25-470b-88bd-d5744ab7952c`

## Autopilot Device Preparation Policy

Now create the device preparation policy

Intune > Devices > Enrollment > Device preparation policies > Create

![](/assets/img/uploads/autopilotpolicy.png)

![](/assets/img/uploads/autopilotpolicy2.png)

## Testing

Now you can try to enroll a device by selecting **Set up for work or school account**

![](/assets/img/uploads/work-or-school.png)

When finished you will have an Entra join and Intune manged device

![](/assets/img/uploads/enrolled.png)

![](/assets/img/uploads/intuneenrolleddevice.png)

# Conclusion

Now user can enroll device, in the next article we will work on how to improve the security because in the current state a user can enroll any device from anywhere without MFA
