title: 'Automation, use it wisely'
author: Tim Gunn
tags:
  - 'androidaps, automation'
categories: []
date: 2019-12-31 07:37:00
---
![AndroidAPS Automation](/images/aaps-automation.png "AndroidAPS Automation")

Automation is relatively recent addition to AndroidAPS. 
It came to fruition in AndroidAPS v2.5 and since then we have seen some great examples on how it can be used. Gaining further control and guidance the APS system in certain situations.

If you are considering to use it, be aware of the following caveats:

* Profile switching renders Autosens useless for a min of 6 hours.

* Profile switching will not reset the profile back to your base profile (you have to make another rule to set this back or do it manually).

* Increased risk of Hypoglycemia if profile switch does not expire or reset back to base profile.

Some Notes to how Autosens works:


* Autosens is a algorithm which looks at Blood Glucose Deviations (Positive/Negative/Neutral. It will try and figure out how sensitive/resistant you are based on these deviations.

* The oref implementation in OpenAPS runs off a combination of 24 and 8 hours worth of data. It uses either one which is more sensitive.

* AndroidAPS only runs off 8 (to enable UAM) or 24 hour as a user option.

* Changing a cannula or changing a profile will reset Autosens ratio back to 0%.

* Autosens adjusts your basal and ISF for you (ie: mimicking what a Profile shift does).

* if continuously eating carbs over an extended period, autosens will be less effective during that period. (Carbs are excluded from BG delta calculations) 

So some basic guidelines:

1) Make sure Profile switches are made sparingly and preferably at a last resort. Profile switches should have a reset condition so the profile can return to normal again to minimize risk of hypoglycemia.

2) Try not make conditions too easy (for example: ```if bg > 80 mgdl and bg < 180mgdl) ``` ) **doubly important if the action is a profile switch***

3) Try and use Temp Targets instead of Profile Switches. Temp Targets do not reset Autosens back to 0.

Moving into developing AndroidAPS versions 2.6 to 2.7 we will bring the Autosens to more closely follow the Openaps implementation.

Watch this space and enjoy automation!