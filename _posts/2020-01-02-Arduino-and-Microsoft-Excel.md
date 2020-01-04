---
layout: post
title: "Arduino and Microsoft Excel"
description: "You must try out this cool combination of Arduino and Excel to display real time data flowing through the serial port of your computer."
category: articles
tags: [data, streamer, addin, plugin, Visualization, time, format, text, excel, utcnow, arduino, serial, communication, sensor, realtime, rs232, ambient, light]
comments: false
---

If you are an [Arduino](https://en.wikipedia.org/wiki/Arduino "https://en.wikipedia.org/wiki/Arduino") hobbyist and a fan of [Microsoft Excel](https://en.wikipedia.org/wiki/Microsoft_Excel "https://en.wikipedia.org/wiki/Microsoft_Excel") then you must try out this cool combination to display data flowing through the serial port of your computer.

Or if you are a Pro in any of the arduino or excel you can explore amazing capabilities of data visualization.

Or even if you are at a beginner level, I bet you will definitely like to play around.


**SERIAL COMMUNICATION**

In Embedded systems, communication via serial port is still widely used. The simplicity and usability of this is really impressive. All the arduino boards have either on-chip or on-board circuitry (UART) to make voltage levels compatible between devices. So these boards are capable to communicate with computers (old) having DB9 connectors as well as via USB connector. This communication is based on [RS232 protocol.](https://www.edgefxkits.com/blog/max232ic-and-interfacing-needs/ "https://www.edgefxkits.com/blog/max232ic-and-interfacing-needs/")


**MICROSOFT EXCEL**

Excel is basically a spreadsheet to enter data and make operations like storing data, writing formulas for calculations, creating pivot table and graphical representation of data. Add-in or plug-in can be installed to simplify complex operations. Here I have used add-in called [Data Streamer.](https://www.microsoft.com/en-us/education/hackingstem/datastreamer "https://www.microsoft.com/en-us/education/hackingstem/datastreamer")


> Data Streamer Add-In supports capturing, visualizing, and analyzing real-time sensor data in Excel spreadsheets.



**THE SET UP**

I have ambient light sensor TSL2561 connected to Arduino Uno board by I2C interface. I have used libraries and code (I tweaked it a little) by [Adafriut.](https://en.wikipedia.org/wiki/Adafruit_Industries "https://en.wikipedia.org/wiki/Adafruit_Industries") Arduino is programmed to read sensor value every second and it sends value out via serial port to PC/laptop.
Data streamer add-in can read the same serial port to which arduino is connected to. I am only reading data and writing back to arduino. So by putting appropriate values in Settings sheet, you can view the sensor reading Data-In sheet.

Arduino Uno

![Arduino Uno](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/ArduinoUno_small.jpg "Arduino Uno")

Sensor TSL2561

![Sensor TSL2561](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/tsl2561_small.jpg "Sensor TSL2561")

Excel Demo

![Excel Demo](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/ezgif.com-video-to-gif.gif "Excel Demo")

**PROS AND CONS**

1. Arduino hardware design and software codes are published in public domain and free to use.
1. No need of Real Time Clock (RTC) module in your circuit. Excel Add-in can handle timestamps as per PC/laptop timezone.
1. Sensor reading interval is absolutely configurable in aduino code.
1. Data storage is not needed in arduino module, data can be saved in excel. Do your own operations on this data. Data can manually be exported in csv format.
1. You need to have office365 license to use excel with Data streamer add-in.
1. You can enable Auto Save functionality to update excel in One-drive and share it with your colleagues. Also other applications can also access this file.
