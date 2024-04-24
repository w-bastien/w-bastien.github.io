---
title: Microsoft 365 - My Entra Configuration
date: 2024-04-22T15:30:00.000Z
categories: "[Microsoft 365, Entra]"
tags: "[getting started]"
image: /assets/img/uploads/microsoft365_logo.png
pin: true
math: false
mermaid: false
toc: true
comments: true
---
In this article I will show you the first things to review when you are starting with a new tenant. I will update this article based on the other topic published on my site. All the information I'm providing should not be viewed as best practices it is based on my experience and my own way of work. \
\
When I do project I always keep a few thing in mind :

* Remember why you are doing something / What need are you covering ?
* Keep it simple
* Don't try to plan everything
* But still plan a bit
* Governance, Risk, Compliance and Security always needs to be part of the subject  

# General guidance

1. Don't minimize the workload of maintaining Microsoft 365, it evolve quickly and it is very powerful
2. Don't try to replicate how you work on prem to the cloud, this is a mistake I see a lot in Intune and in Entra

* Are you sure that the way you work is the best way to do ? 
* Are the tools compatible with the way you work ? 

# Governance

Define a naming convention for your group, I always tend to do something like that : \[Product]\*-\[SubProduct]-\[Environment]\*-\[Scope]-\[Name]. So the final result can be : Entra-Licences-PRD-Group-M365E5-Full or Intune-Exception-PRD-Allow-USB-Key. 

Also i'm using camel case.

# Risk and Security

1. Create an emergency account with the global admin permission, this account should be excluded from all conditional access policy it should be strongly monitored and have a strong password
2. Create a group that will be excluded from all conditional access policy (Entra-CA-Exclude-From-All)
3. At least enable the following conditional access policy template, remember to edit them to remove the exclusion of your account and add the emergency account and group to the exclusion :

   * Require multifactor authentication for admins
   * Require multifactor authentication for Azure management
   * Require multifactor authentication
4. Disable User consent for applications

I know that this article is not complete for now, IMO this is the bare minimum you should do when you start
