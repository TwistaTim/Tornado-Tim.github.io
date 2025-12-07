title: Autosens in AAPS - In Detail
author: Tim Gunn
date: 2020-07-16 10:03:52
tags:
---
![Autosens](/images/AS.png)
Recently while the new 2.7 beta has been running, we have seen some reports stating that Autosens value has not moved much since using it.

I thought I would discuss this in a little greater detail and the background why people are experiencing these changes.

#####  Autosens in AAPS versions pre 2.6
The Autosens implementation in these versions is out of scope and is not in-line with the reference design.

In these versions you will see 2 sensitivity options in the config builder. One for 8 hours and one for 24 hours. Only the 8 hour option (called oref1 sensitivity) is able to calculate or distinguish between a positive deviation from UAM.

The reference design was not designed this way.

So changes were needed to bring AAPS into line with the reference design.

##### Autosens in AAPS versions 2.7 beta+

The 8 hour option was removed, and in place implemented the reference design to use 24 hours of sensitivity, if sensitivity was detected over 8 hours it used the sensitivity from that period instead.

This approach is more conservative than the the Autosens implementation in pre 2.6 versions. Reason: Safety, The reference design has been built this way for a reason.

#####  Possible outcomes from upgrading

It is normal that you may experience less positive Autosens changes (when resistant) and it may take a little longer for Autosens to respond to resistance. 

In my experience since using the Autosens upgrade, it responds just like my previous OpenAPS rig did, so this change was normal and expected.

For users who have never ran OpenAPS before, this will come as a change.

#####  Digging a bit deeper into the deviations

To get a little more understanding on what Autosens is seeing, look at the deviations on the main screen.

Grey Deviations - Carbs on board / Decaying
Green Deviations - Positive Deviations (Resistance)
Red Deviations - Negative Deviations (Sensitivity)
Yellow Deviations - UAM Detected

Tap and hold on the main BG and zoom out to the 24 hour period.


![Deviations](/images/Deviations.png)

How much of the graph is Grey or yellow? If a good portion is filled with grey or yellow it means Autosens is running on very little data to calculate its deviations. Only Red and Green Deviations are used. Hence why your getting a value that doesn't move much.

##### Fixing a seemly fixed Autosens value

This is comes down to how your using the system, but it also comes down to your settings.

Revising carb absorption, IC, ISF ratios, Basal etc may be needed to shorten these periods down so AS can get back to work more quickly.


Look a bit deeper into the 8 hour, and 24 hour autosens data. 
Under the OpenAPS SMB screen, scroll down and view the *sensResult*.
2 ratios will be listed. One for 24 hour and the other 8 hour.
Any value above 1 will indicate resistance, less than 1 will indicate sensitivity.
The period in the bracket is the sensitivity period chosen (8 hours or 24 hours) Based on the reasons above.

![Autosens Raw Data](/images/ASraw.png)

Remember: the reference design in AndroidAPS lacks automatic autotune integration like on OpenAPS, this effectively feature helps adjust profile settings for you automatically in the reference design.

With this in mind and this feature not being in AAPS, regular Autotune runs should be conducted to make sure your settings are on point to make the most out of the reference design as possible.

##### Conclusion

Regular settings revision remains best practice for running a DIY APS system.

If you have further queries in regards to this change or have found a legit bug with the implementation of the change, I am happy to review.

Hope your enjoying the beta so far, keep the bug reports coming in!

Regards

Tim