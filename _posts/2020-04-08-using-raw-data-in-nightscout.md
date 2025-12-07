---
title: Using Raw Data in Nightscout
author: Tim Gunn
date: 2020-04-08 23:25:01
tags:
layout: post
---
If you are using Nightscout to do remote surveillance and reporting on interstitial glucose, you may not be aware of a very cool feature.

This feature can show and monitor values which are hidden from view in a typical CGM application.

This is the RAW data which comes back from CGM (Dexcom G4,G5 and some G6 transmitters).

You can use this data while the CGM is warming up and not providing a SGV value.

But the way I often look at the raw data, is determining what is happening with my glucose values before the SGV values start to change.

Raw data changes more quickly and can fluctuate more than the SGV so it cannot always be relied upon. When the sensor is noisy is an example when to disregard raw readings. However if you have a CGM reporting "???" you can check on the raw data to see how jumpy the readings are and to give yourself a little more insight on the state of your sensor and or glucose values during that time.

Another thing raw data is good for is checking whats going on with your glucose before it changes the SGV value.

Example below: white dots indicating the raw values.
It shows that my glucose was falling quicker than what the SGV values after a pre-bolus and that means I need to commence eating sooner than thought.
The subsequent glucose rise was also more rapid than what is shown by the SGV values.


![Raw Data](/images/rawdata.png "Raw Data")

So by using raw data appropriately you can gain a little more insight and start to get a more quicker insight into your values with less "lag" as well.

By default in Nightscout, raw data is turned off, and needs enabling.

You can enable this by adding
```SHOW_RAWBG=always```
into your NS Config. Alternatively if you are using Heroku to host Nightscout  use ```SHOW_RAWBG``` and ```always``` in the Heroku Application settings.