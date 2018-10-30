---
layout: post
title: "Global Landslide Catalog"
description: "Visualization of NASA open Data : Global Landslide Catalog (1988 - 2017)"
category: articles
tags: [power, BI, NASA, landslide, mudslide, pune, malin, rankx, DAX, open, data, Visualization, global, satark, india]
comments: false
---

I remember it was July 2014, another rainy day in Pune. I was at work in the evening and a colleague showed me photos of Malin incident. It was scary. A landslide incident which took place early in the morning of 30th July killed around 150 people in small village called Malin not much far from Pune city, in Maharashtra state of India. Continues monsoon rain caused mudslide on the slope of mountain and whole village had gone under mud and debris. Soon after that “Satark India” an amateur group built their own model to predict such incidents and spread awareness through online and print media. Related to this, earlier this year NASA had updated open data named Global Landslide catalog that has all information of landslides from 1988 to 2017. Below interactive visualisation is created using Microsoft Power BI based on OData feed of dataset published by NASA.

First step I did was Data formatting in Power Query. I used Replace option in UI and function called TransformColumnNames along with Text.Proper function. Then started with defining Data type in power query and power BI’s Modelling options. On first page of this report Bing map highlights locations of the incidents. Hovering mouse over any highlighted location gives insights of that particular incident. These insights are based on columns added in Tooltips field of Map visual. The location accuracy mentioned in data is varied from exact location i.e. 0km to 250km. Three Cards visuals are used to show total number of incidents mentioned in data and its impact such as fatalities and injuries. Below that a matrix table shows the list of 10 worst affected countries, calculated using RANKX DAX function. A line chart with Year on the X axis and number of incidents, fatalities and injuries on Y axis. This line chart has ‘Drill’ feature to view data year-wise or month-wise or complete timeline of month-year wise. Another matrix is used to show each country in Rows and each Month in columns. Count of incidents was put into Value field of matrix and using conditional formatting (background colour) gives exact look similar to heat-map visual. Incidents, Fatalities and Injuries are three important datapoints in this dataset and gives detailed information using various kinds of visuals.


Second page has Donut chart that gives information about the landslide size, category, trigger and setting. A table that gives all information of landslide incidents present in dataset.
Further on right top corner of both pages has a ‘Slicer’ that can be used to filter data based on the year. By filtering the Year, complete report visual changes according to period of time is selected. On the first page by clicking on country name data can be seen interactively whereas a slicer on second page is used to filter out specific country name.


**OData Refresh Settings**

In PowerBI service, under Dataset option ‘scheduled refresh’ configuration can be done. As shown in snapshot below, authentication method is ‘Anonymous’ because there is no requirement to sign into dataset.

![https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/OData_Anonymous_signin_1.JPG]( https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/OData_Anonymous_signin_1.JPG “Data Source Credentials”)


![https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/OData_Anonymous_signin_2.JPG]( https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/OData_Anonymous_signin_2.JPG “Configure Sign-in”) 


As NASA has not mentioned update frequency, I have set to maximum possible rate, weekly once.
![ https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/OData_scheduled_refresh1.JPG]( https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/OData_scheduled_refresh1.JPG “Schedule Refresh”) 


![https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/OData_scheduled_refresh2.JPG]( https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/OData_scheduled_refresh2.JPG “Next Refresh Details”) 


**Alert Notification**

A card showing count of Incidents on first page, I pinned it to dashboard. I wanted to receive alert if new incident is added, so I put threshold value a bit greater than current number of incidents i.e. 11035. There is also an amazing facility to connect this threshold as a trigger to Microsoft Flow.


![ https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/Alert_Notification_1.JPG] (https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/Alert_Notification_1.JPG “Manage Alert”)

![ https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/Alert%20Notification_2.JPG] (https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/Alert%20Notification_2.JPG “Alert Details”)


**Power BI Visualization**


<iframe width="800" height="600" src="https://app.powerbi.com/view?r=eyJrIjoiZjBlYjBiYzMtMjdkOC00MGViLTlkMjYtMjRkZmQ3YWYwNzYxIiwidCI6IjliOTFmNGY2LWVmM2EtNDFkZS1hNWE4LTJkYTZkYjg2MDkxYSJ9" frameborder="0" allowFullScreen="true"></iframe>
