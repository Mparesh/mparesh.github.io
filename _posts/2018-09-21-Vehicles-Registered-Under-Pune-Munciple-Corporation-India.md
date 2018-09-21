---
layout: post
title: "Vehicles Registered Under Pune Munciple Corporation - India"
description: "data visualization of Vehicles Registered Under Pune Munciple Corporation, India."
category: articles
tags: [power, BI, pune, open, data, visualization, analytics, India]
comments: false
---

This dataset is taken from PMC open data and Power BI report below is interactive visualization of number of vehicles registered under Pune Municipal Corporation in Maharashtra state of India from Year 2002 to 2017.

Number of vehicles can be considered as one of the key parameters to analyse the growth of a city. So even though dataset has one sheet of 16 rows only but it is very insightful. Report is divided as - Charts showing growth of number of vehicles & types of vehicles that are rapidly increasing, insight of positive and negative trend in growth and finally forecasting the trend for next ten years.

**Data**

First page of Power BI report is a Matrix of complete data. Header is type of vehicles and First column is year, last column is total number of vehicle year-wise. Below the Matrix A “card” shows a round of value (in Millions) of measure “Total Number of Vehicles”. This value changes as per the row selected in Matrix, showing total of that particular year. When not selected any row Card shows 31 Millions and when selected year 2009, total number of vehicle is approx 2 Millions where as exact value in Matrix is 1760402.

**Charts and Treemaps**

On second Page, Treemap shows Motorcycles, scooters, mopeds and cars are the major contributors of total values. So to understand exact values of contributors, two different Line Charts are used. For better visualization one line chart is for Two wheelers like motorcycle, scooters & mopeds.Other line chart is for cars, jeeps and auto rickshaws. Here motorcycles and cars show linear growth compared to mopeds, autos respectively. If two charts were  combined together, because of high low value of autos, jeeps and mopeds could not be visible hence reducing the significance of entire chart. Above these charts two column charts with year as X axis shows growth of total number of vehicles and total number of new vehicles added every year. By hovering mouse on these charts, detailed values can be seen and by clicking on it, all other charts and treemap highlights their corresponding details.

**Positive and Negative Trendline**

On third page, insights of few vehicles which have positive and negative trendline. Decrease in number of auto-rickshaws and stage carriage after year 2011 is significant as at the same time there is increase in school bus started which continues to grow even more after Year 2015. Tankers and station wagons has positive and negative trendline respectively. Contract carriage has ups and downs but value of year 2017 is almost two-fold as that of year 2016.

**Forecasting**

On last page, by using built-in forecasting models two line charts shows growth of motorcycles and total number of vehicles for next 10 points i.e. till year 2027. Confidence interval is set to 95% so prediction value have upper bound and lower bound values as well.

**Implemention**

For implementing this visualization, excel connector was used in Power BI desktop. Basic formatting done using power query UI. There was no need of M functions as data was clean, no missing values were present. During analysis total number of vehicles and new vehicle calculations were done by various DAX function like IF, SUMX, CALCULATE AND PREVIOUSYEAR. This report was published to Power BI service and report URL is embedded in this blogpost.

<iframe width="800" height="600" src="https://app.powerbi.com/view?r=eyJrIjoiZTViYTE5ZGEtZDQ3Mi00MDUzLWI0ZjEtM2Q0YWUzYTQwNTYzIiwidCI6IjliOTFmNGY2LWVmM2EtNDFkZS1hNWE4LTJkYTZkYjg2MDkxYSJ9" frameborder="0" allowFullScreen="true"></iframe>


below is different size

<iframe width="680" height="510" src="https://app.powerbi.com/view?r=eyJrIjoiZTViYTE5ZGEtZDQ3Mi00MDUzLWI0ZjEtM2Q0YWUzYTQwNTYzIiwidCI6IjliOTFmNGY2LWVmM2EtNDFkZS1hNWE4LTJkYTZkYjg2MDkxYSJ9" frameborder="0" allowFullScreen="true"></iframe>
