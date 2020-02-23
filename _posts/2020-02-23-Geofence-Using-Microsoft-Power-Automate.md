---
layout: post
title: "Geofence Using Microsoft Power Automate"
description: "Trigger a flow based on geographic location using microsoft power automate mobile application"
category: articles
tags: [power, automate, flow, geo, services, text, mobile, microsoft, trigger, excel, table]
comments: false
---
If you are trvalling across the states of India, I am sure you must have received SMS notification that you have entered particular state and roaming charges are applicable. Well, this is the simplest example of tracking subscriber's geo location and catering services accordingly.

In the world of IOT, geofencing is very popular.	If a device enters/exits particular geographic area, automation triggers the corresponding process. 

Microsoft has brought the **GeoFence connector** in Power Automate and in latest realse Feb2020 it has been made generally available [generally available.](https://docs.microsoft.com/en-us/power-platform-release-plan/2019wave2/power-automate/running-flows-geofence-generally)

![Release ](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/geofence2.png  "Release")

Connector is simple, find the address on the bing map or provide lattitude and longitude of the geographic location. Adjust the zoom level on the map to define the virtual circular fence over that geogrpahic location. If your mobile device is connected to GPS and internet, your flow is triggered when you enter or exit  geofence.

![Connector ](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/geofence1.png  "Connector")

With JSON parser action we can control the excecution of the flow based on  trasition of mobile device.

	{
	  "currentLongitude": "*****",
	  "radius": 14,
	  "currentLatitude": "*****",
	  "transitionType": 2
	}

In output of connector, "transitionType": 2 is when you exit the geofence and "transitionType": 1 is when you enter the geofence. I cound not really found the documentation of this values but I have tried and tasted these values.

As a hobbiest you can create a flow and use this trigger from Live account and populate and excel sheet stored on Onedrive.

![ ](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/geo4.png  "Populate Excel Table")


![ ](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/Geo3.jpg  "Excel Table")
