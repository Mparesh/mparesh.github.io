---
layout: post
title: "Formatting Dates in Power Platform"
description: "Microsoft applications have versatile functions to change the format how day, month and year are arranged together to form a complete date. I used few of such easy to use functions in Excel, Flow, Powerapps and PowerBI. There is bunch of predefined functions in each of these applications to change representation of any text and particularly date."
category: articles
tags: [power, BI, flow, powerapps, DAX, apps, data, Visualization, date, format, text, excel, utcnow, sharepoint, DateTimeFormat]
comments: false
---
Sometimes Date format is very confusing for me, be it written on paper or online. Let’s consider a date 06-02-19. So, is it 2nd of June or 6th of February or 19th of February? Microsoft applications have versatile functions to change the format how day, month and year are arranged together to form a complete date. I used few of such easy to use functions in Excel, Flow, Powerapps and PowerBI. There is bunch of predefined functions in each of these applications to change representation of text and particularly date. Note that functions listed in this blogpost are primarily used to change the format of date and not to take other insights of data.


## EXCEL
A simple right click on cell or a column gives option to format cells to choose the different combination of date, month and year. 

![format cells in excel](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/format%20cells.JPG "Format Cells")

There is a function in Excel – TEXT(value, format_text) which does the same by using it in formula bar. Text function is very powerful and useful to display Date in readable format.
 
Column A has Date in DD-MM-YYY format. Column B, C and D are different textual representation of same date in column A. 
```sh
=TEXT(A2, "mmmm")
=TEXT(A2, "dddd")
=TEXT(A2,"mm-dd-yy")
```
![](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/Excel_2.JPG "Excel sheet")

Find More about Text function [here.](https://support.office.com/en-us/article/text-function-20d5ac4d-7b94-49fd-bb38-93d29371225c "https://support.office.com/en-us/article/text-function-20d5ac4d-7b94-49fd-bb38-93d29371225c" )

## PowerBI
DAX function FORMAT(value, format_string) can be used in PowerBi to achieve same functionality shown above in Excel. Consider, Date is one column in a table. Three New columns are added with below DAX formula. Note that Data type of these new columns is automatically set to Text.

```sh
Month = FORMAT('Date'[Date], "MMMM")
Day = FORMAT('Date'[Date], "DDDD")
MM-DD-YY = FORMAT('Date'[Date], "MM-DD-YY")
```
![](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/powerbi_4.JPG "Month Column")
![](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/powerbi_5.JPG "Day Column")
![](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/powerbi_6.JPG "MM-DD-YY")

All these columns are used in Table visual in report view of PowerBI shown below.

![](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/powerbi_3.JPG "Table visual in PowerBI")

## Flow
formatDateTime(timestamp: string, format?: string)
In first example here, is to check whether filename contains today’s date when items are listed from SharePoint List. And another example is to check if file is modified today. utcNow() function gives current date-time of UTC timezone. For comparison it is needed to change format of UTC timestamp corresponding to filename and LastModified property.
Note that for month, code is capital M and small m is code for minute value in time.
```sh
formatDateTime(utcNow(), 'dd-MM-yyyy')
formatDateTime(utcNow(), 'yyyy-MM-dd')
```
![](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/flow_data.JPG "Body")
![](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/flow.JPG "formatDateTime(utcNow(), 'dd-MM-yyyy')")
![](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/flow_condition.JPG "formatDateTime(utcNow(), 'yyyy-MM-dd')")

## PowerApps

 Text( NumberOrDateTime, DateTimeFormatEnum [, ResultLanguageTag ] )
 - NumberOrDateTime - Required. The number or the date/time value to format.
 - DateTimeFormat - Required. A member of the DateTimeFormat enumeration.
 - ResultLanguageTag - Optional. The language tag to use for the result text. By default, the language of the current user is used.

Various predefined combinations of format codes are listed [here.](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/functions/function-text "https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/functions/function-text")

Title1_2 is a label inside BrowseGallery1 which shows the Date column in connected data source by using function ThisItem.Date. Its showing date and time. By using below functions in label Title_1 LongDate format is shown and no time.
```sh
ThisItem.Date
Text(ThisItem.Date, DateTimeFormat.LongDate)
```
![](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/powerapps_4.JPG "ThisItem.Date")
![](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/powerapps_5.JPG "Text(ThisItem.Date, DateTimeFormat.LongDate)")


