---
title: Changes are coming to AndroidAPS
author: Tim Gunn
date: 2020-07-02 10:57:05
tags:
layout: post
---
![upload successful](/images/AAPSpng.png)
Version 2.7 of AndroidAPS is coming along nicely with the first beta release being launched.

If you are beta testing this, thanks for your comments and feedback and most importantly bug reports (these help us allot!).

I wanted to share some algorithm and feature highlights of the upcoming version 2.7 and the changes that impact the way you will interacting with AndroidAPS. This is a very small insight into the massive development push behind this revision.

One area of we wanted to focus allot on was the algorithm powering AAPS. (oref from [OpenAPS](https://openaps.org/)). We also wanted having more of a deeper interaction and to standardize it, so you can use more functionality of this incredibly powerful algorithm. We have now brought the "OpenAPS SMB" algorithm up to the 0.7.0 version of the reference design algorithm. 

As part of this process:

##### Autosens

Autosens has got an overhaul, we have removed the option to have a sole 24 or 8 hours of sensitivity. Instead we have followed the reference design from OpenAPS where the sensitivity window is elastic and changes as you change.

Autosens will now pick 24 hours of sensitivity deviations or 8 hours and will choose which ever one is more sensitive.

If you are using the current oref1 sensitivity model (sole 8 hour), this means you may find on occasions autosens a little slower to respond. This is normal and expected.

##### Carbohydrates Required
As part of the reference design, these alerts were given out by the algorithm but not used, now they are. So now you can be notified when APS states it cannot rescue you by zero temping, therefor needing carbs.

Carbs Required notifications can be enabled locally (only shown in AAPS) or to Android.

When Carbs are required: The main screen carb icon will pulse red and it will show how many grams of carbs are required. After responding to carbs required by adding more carbs, the required amount will be removed. The carb icon will remain pulsing red until oref (the algorithm) is satisfied no more carbs are needed. 
Screenshot below of it in action:
![upload successful](/images/carbreq.png) 
Native Android Carbs Required Notifications can be snoozed for 5,15 and 30 min.
Notifications are automatically  suspended for 15 min post any treatment (Bolus or Carb Entry)

Note: Carb suggestions/notifications require the SMB algorithm to be enabled.
![upload successful](/images/carbreqnotif.png)


##### Dynamic Target Adjustment: 
We have enabled a cool feature that you can turn on if you wish for people running the OpenAPS SMB algorithm, this is dynamic target adjustment. 
When either "Sensitivity Raises Target" and or "Resistance lowers Target" is enabled, the target glucose from your profile will then start to dynamically change in relation to your sensitivity changes. This can help stop the need to set Temp Targets when experiencing insulin sensitivity or resistance.
When your target has been adjusted dynamically the Target Glucose Box will turn Green to state your target differs from your base profile.


![upload successful](/images/DynamicTargetAdjustment.png)

Thats all I will cover for now, more will be coming as we advance towards a RC and Final version.

Thanks

Tim and the AAPS Dev Team