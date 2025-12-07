title: 'APS, you and your cell phone'
tags:
  - 'Looping,  Nokia, APS, #WeAreNotWaiting'
categories:
  - Looping
  - Smartphone
author: Tim Gunn
date: 2019-12-25 15:43:00
---
<img src="/images/apsphone.jpg" width="300">

To those who have experienced looping on a smartphone, the experience is fantastic is it not? Carrying around a device that can also double as your artificial pancreas, makes so much sense. 

We have started seeing an overwhelming push from smartphone manufacturers to make sure that your battery lasts as long as long as it can.

iOS and Android versions from 8+ will now proactively sleep apps that sip battery and have background processes running. 

This is great for most people, as they get more battery life and who doesn't want that eh? But what about the people who use a smartphone as medical device? What about us "Loopers"? 

This is where it can get complex, and this is where most looping setups will fail, it all comes down to CGM data collection.

In particular CGM Bluetooth devices that spend most of the time 'sleeping'.

On the Dexcom CGM system, the transmitter stays awake for less than 15 seconds every 5 minutes. Then during that window your phone will try to connect to your transmitter, open the connection up, provide a reading and then close the connection.

These small windows of opportunity to get CGM data are consistent and there is no way to make these windows bigger without sacrificing battery life on the transmitter itself. Any small hiccup in the chain can stop a cellphone from getting a CGM reading, so developers will always try and make sure the code executes to connect and get the reading done in time. Not all phones are equal and setting on each phone are not equal either. 

The most common setting which prevents CGM collection is battery saving, it does this by a combination of factors, sleeping sections of hardware on the phone that are not used (ie: Bluetooth), and sleeping processes that run in the background. In some cases when the hardware has been slept by the above manner it can take setting a fake alarm to wake the hardware up in a timely manner!


#### How do make sure battery saving is turned off? ####
###### Android: ######

Settings > Battery > Standby intelligent power saving = off

Settings > Battery > Adaptive Battery  = off

Some Android Phones will have some other battery saving settings, turn those off.

In AndroidAPS and xDrip, the apps are whitelisted from stock Android Battery Saving, but this will not stop other battery saving applications from sleeping them.

Ensure that all other battery saving tech is turned off, esp if running a Huawei/Oppo/Honor/Xiaomi phone.

###### iPhone ###### 

iOS with the Dexcom App and Loop should run fine on a tested/supported version of iOS. Do not enable Low-Power Mode or turn off Bluetooth while using your phone. 

#### So what phones are best to collect CGM data on? ####

###### Android: ######
Any Android One handset (or Android at stock); Manfucturers such as Nokia, Motorola's One devision and Google's Pixel. 

###### iPhone: ######
Any iPhone should be suitable for CGM collection.


If you loop with a smartphone, you should treat your phone as a medical device.

What do I mean by that? Be cautious before proceeding with anything that is making changes to your phone, installing apps, software updates etc. The last thing you want is a broken loop!

Operating system updates can break your loop so, check on social media, github issues etc for postings about new updates etc. Also keep your CGM/APS apps up to date.

Hope this helps.