---
layout: post
title: "Building MS Teams Presence Light using IoT and Arduino"
description: "The project integrates Microsoft Teams status updates with Azure resources and a NodeMCU-powered RGB LED lamp"
category: articles
tags: [microsoft, MS, graph, api, Teams, user, presence, beta, azure, function, iot, iothub, hub, arduino, esp8266, nodemcu, rgb, led, 4x4, lamp, token, entraid, aad]
comments: false
---
Are you tired of being interrupted during important online work meetings at home? Well, this LED lamp can save you! Your MS Team’s status will light up the LED lamp, indicating to those around you when it's best not to disturb you.

I subscribed to Graph API beta version to get notifications when Teams status is changed. As soon as the change notification is received an Azure Function is triggered and it sends message to NodeMCU using Azure IoTHub. A NodeMCU (ESP2866 development board) is an Arduino compatible tiny computer (technically it’s a microcontroller) it has onboard WiFi. Thanks to Microsoft for a library and sample code to connect Nodemcu to Azure IoTHub, it made my life easy. So based on the Teams status my 4x4 RGB LEDs changes its color.
