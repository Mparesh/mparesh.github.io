---
layout: post
title: "Geofence Using Microsoft Power Automate"
description: "Trigger a flow based on geographic location using microsoft power automate mobile application"
category: articles
tags: [power, automate, flow, geo, services, text, mobile, microsoft, trigger, excel, table]
comments: false
---
If you have trvalled across the states of India, I am sure you must have received SMS notification informing you that you have entered particular state and roaming charges are applicable. Well, this is the simplest example of tracking subscriber's geo location and catering services accordingly.

In the world of IOT, geofencing is very popular. If a device enters/exits particular geographic area, automation triggers the corresponding/designated process. 

Microsoft has brought the **Geofence connector** in Power Automate and in latest realse Feb 2020 it has been made generally available [generally available.](https://docs.microsoft.com/en-us/power-platform-release-plan/2019wave2/power-automate/running-flows-geofence-generally)

![Release ](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/geofence2.png  "Release")

Choose trigger Location - "When I enter or exit an area". Connector is simple, find the address on Bing map or provide lattitude and longitude of the geographic location. Adjust the zoom level on the map to define the virtual circular fence over that geogrpahic location. Now, if your mobile device is connected to GPS and internet, your flow is triggered when you enter or exit  geofence. It is all automatic! :)

![Connector ](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/geofence1.png  "Connector")

With JSON parser action, we can control the excecution of the flow based on trasition of mobile device.

	{
	  "currentLongitude": "*****",
	  "radius": 14,
	  "currentLatitude": "*****",
	  "transitionType": 2
	}

One of the output parameters of this connector is transitionType. "transitionType": 2 is when you exit the geofence and "transitionType": 1 is when you enter the geofence. I cound not really found the documentation of this values but I have tried and tasted these values.

Based on this parameter, flow triggers the mobile notificaion. Flow is designed as below:

**Geo - Mobile Notification Flow**
![Geo - Mobile Notification ](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/geo5.png  "Geo - Mobile Notification")

**Mobile Notification**
![ ](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/IMG_5447.PNG  "Mobile Notification")

Another use of this connector


>As a hobbiest you can even create a flow and use this trigger from Live/Outlook account and populate and excel sheet stored on Onedrive.

Create a table in Excel Online stored on Onedrive. Choose action as "Add a row in a table" and connect the sheet to power automate.

**Add a row in a table**
![ ](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/geo4.png  "Populate Excel Table")

**Excel Table**
![ ](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/Geo3.jpg  "Excel Table")


By using Datedif formula in such excel table you can calculate how many hours you have spent at workplace or at home!
