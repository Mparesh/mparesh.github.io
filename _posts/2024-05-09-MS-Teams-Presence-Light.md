---
layout: post
title: "Building MS Teams Presence LED Light using Graph API, Azure resources and Arduino"
description: "The project integrates Microsoft Teams status updates with Azure resources and a NodeMCU-powered RGB LED lamp"
category: articles
tags: [microsoft, MS, graph, api, Teams, user, presence, beta, azure, function, iot, iothub, hub, arduino, esp8266, nodemcu, rgb, led, 4x4, lamp, token, entraid, aad]
comments: false
---
Are you tired of being interrupted during important online work meetings at home? Well, this LED lamp can save you! Your MS Team’s status will light up the LED lamp, indicating to those around you when it's best not to disturb you.

## Integration Process
I subscribed to the Graph API beta to receive notifications when Teams status changes. An Azure Function triggers upon receiving the notification and sends a message to the NodeMCU via Azure IoTHub. The NodeMCU, an ESP2866 development board, is Arduino compatible and equipped with onboard WiFi. A library and sample code provided by MS helped me a lot to connect the NodeMCU to Azure IoTHub. As a result, the 4x4 RGB LEDs change color based on the Teams status: green for Available, red for Busy & DND, and amber for Away.

## Diagram
![Diagram](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/8fc0a5454d04a9dff1f599dd440aeed6bf60afd7/asset/MSTeamPresence.png "Diagram")

## Components Overview
Let’s get into the details of how it works. The solution consists of two parts. First is the cloud - A Microsoft environment that consist of MS Teams, Graph API subscription and Azure Function, Azure IoTHub and AAD in background. Second part is the electronics - Arduino compatible microcontroller with WiFi module and 4x4 RGB LED lamp.

1. **MS teams** : MS Teams is teams collaboration app widely used with O365 family products. It has various status like “Available, Busy, Away, Do Not Disturb, Be right back, offline” are set as per usage.
2. **AAD** : Azure Active Directory (Now Entra ID) is Identity Access Manageement (IAM) service. Through AAD a user logs in and then user explicitly gives consent to “Delegated Permission” so that Graph API can work to fetch user’s status.
3. **Graph API** : MS Graph is a gateway to Mirosoft's world of services. It exposes REST APIs to acess data strored across servvies. The one API used here is still in Beta version, not suitable for production envrionment. There are multiple ways to subscribe to notification of “User presence in Teams”. Initial request can be made using any of the following PowerShell, HTTP request or from Graph explorer in browser.
4. **Azure Function** : Azure function services is serverless. No hassle of maintaining hardware Infrastrcutre. Deploy your piece of code in any of the 5 supported programming langauges. Set trigger how and when code should be executed. In this solution the Graph API sends notification to webhook URL which was provided during its initial subscription. Notifications are typically, confirmation for successful subscription, Teams status change notification and API lifecycle notification i.e. time to renew the token. The code is capable of IoT Cloud to Device messaging action. Same piece of code deployed in Azure function handles all these notifications and actions.
5. **IoTHub** : Azure IoT Hub is a cloud service that enables communication between your Internet of Things application and the devices it manages. Here it is used to connect one IoT device. IoT device's "Shared Access key" can be fetched IoT Hub portal to use it Arduino cide. "Cloud to device" messages is routed through the IoTHub.
6. **Arduino** : Nodemcu device uses WiFi to connect to Azure IoTHub using SAS token as per sample code in MS library. When IoT cloud to device message is received it controls the color of 4x4 RGB LED lamp according to received message.

## Observations
- When testing the solution I observed that though teams status sent by graph api to azure function was in near real time but it did NOT come in correct sequence. If my teams status is changed from busy to available to away to offline in very fast fashion, many times the azure function did not receive status in exact specific sequence. However, to overcome this one may need to be mindful in changing Teams status.
- Graph API token lasts only for an hour or so. Also this API is still in beta version, not useful in large deployment in PROD.
- Development cost of electronics is affordable. If you already have Azure subscription, MS licensed products then total cost is not very expensive for 1 prototype.
- Although it is fun to develop the project for hands-on experience, I am still pondering on a thought if it is really worthy use case to do in PROD on a large scale?

## Demo
Youtube Video

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/6C6oODJ-Gak?si=cryshV58UvBE9FSn" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</p>
