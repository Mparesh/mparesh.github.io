---
layout: post
title: "Global Landslide Catalog"
description: "Visualization of NASA open Data : Global Landslide Catalog (1988 - 2017)"
category: articles
tags: [power, BI, telecom, Subscriber, churn, customer, revenue, rankx]
comments: false
---

I remember it was July 2014, another rainy day in Pune. I was at work in the evening and a colleague showed me photos of Malin incident. It was scary. A landslide incident took place early in the morning of 30th July killed around 150 people in small village called Malin not much far from Pune city, in Maharashtra state of India. Continues monsoon rain caused mudslide on the slope of mountain and whole village had gone under mud and debris. Soon after that “Satark India” an amateur group built their own model to predict such incidents and spread awareness. Earlier this year NASA had updated open data named Global Landslide catalog that has all information of landslides from 1988 to 2017. Below interactive visualisation is created using Microsoft Power BI based on OData feed of dataset published by NASA. 

First step I did is Data formatting in Power Query. I used Replace option in UI and function called TransformColumnNames along with Text.Proper function. Then started with defining Data type in power query and power BI modelling options. On first page of this report Bing map highlights locations of the incidents. Hovering mouse over any location gives insights of that particular incident. These insights are based on columns added in Tooltips field of Map visual. The location accuracy mentioned in data is varied as exact location i.e. 0km to within 250km. Three cards are used to show total number of incidents mentioned in data and its impact such as fatalities and injuries. Below this a matrix table shows the list of 10 worst affected countries, using RANKX DAX function. A line chart is Year on the X axis and Y axis shows number of incidents, fatalities and injuries. This line chart has drilling feature to view data year-wise or month-wise or complete timeline of month-year wise. And another matrix is used to show each country in Rows and each Month in columns. Number of incidents is value in this matrix and conditional formatting (background colour) gives the look similar to heat-map visual. To Incidents, Fatalities and Injuries are three important datapoints in this dataset and gives detailed information using various kinds of visuals. 


Second page has Donut chart that gives information about the landslide size, category, trigger and setting. A table that gives all information of landslide incidents present in dataset. Further on right top corner of both pages has a slicer that can be used to filter data based on the year. By filtering the Year, complete report visual changes according to period of time is selected. On the first page by clicking on country name data can be seen interactively whereas a slicer on second page is used to filter out specific country name.


**OData Refresh Settings**
PowerBI service is li
