---
layout: post
title: "Twitter Sentiment Analysis Using Microsoft Flow, Cognitive services and Power BI"
description: "A small experiment of using few Microsoft services"
category: articles
tags: [power, BI, twitter, flow, cognitive, services, text, analytics]
comments: false
---


This blogpost is exciting! A small experiment of using few Microsoft services strikes me to think about opportunity it gives to understand the depth of analytics and visualizations. The aim is to search a keyword/hashtag in tweets on Twitter and analyse the sentiment and visualize the outcome graphically. Microsoft Flow, Cognitive services and Power BI total three services used here.


**Twitter**

Twitter is micro-blogging social media website. Users post Tweets that can be text, multi-media content and interact with other twitter users. Let us consider, users tweet expressing individual’s feeling of exhausting week that can convey negative sentiment or express peaceful weekend is approaching with happy sentiment. Here I need to analyse Text part of tweets containing word #FridayFeeling which is often trending topic on twitter.


**Microsoft Flow**

Automation tools are generally used to integrate various services and execute tasks. Flow is popular among non-programmers as there is absolutely no coding involved. It also has intuitive way of designing task flows. Here with the help of single Flow Template, I am able to connect all required services together quickly. I could not find any other easier and simpler way to set it up. Flow records the number of times it has run this set up and if the result was success or failure.

- Flow Template snapshot as below

![https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/Flow%20Template.png](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/Flow%20Template.png "Flow template")

**Microsoft Cognitive services**

Text Analytics part of cognitive services rates the input sentence between 0 to 1 where 0 is extremely negative and 1 extremely positive sentiment. 0.5 value is retuned when cognitive service could not rate the sentence or sentence itself is neutral. This value is called as sentiment “score”.


**Microsoft Power BI**

It is one of the best tools available in the field of business intelligence. Power BI service supports streaming dataset. This means everything that that is set up at Flow can be directly connected to power BI and data is pushed in as streams. Based on this data a report can be designed to visualize the data interactively.

- Power BI Streaming Dataset snapshot as below

![Power BI streaming dataset](https://raw.githubusercontent.com/Mparesh/mparesh.github.io/master/asset/Power%20BI%20Streaming%20Dataset.jpg) 

**Data is visualization in Power BI**

1. Text box – Title of the report
2. Table – Total 4 columns to showcase actual Data. Username, Tweet text and its corresponding sentiment Score and the timestamp of tweet. By clicking on any of the header column data is sorted in ascending/descending order. 
3. Gauge – used to visualize the sentiment score. When not selected any tweet from Table, its shows the average sentiment value of all the tweets. When any tweet is clicked in table, gauge value is changed as per sentiment value of selected tweet.
4. Card – Two cards are used to total number of Tweets are present this data and Count of distinct twitter username present the data.
<iframe width="800" height="600" src="https://app.powerbi.com/view?r=eyJrIjoiZTdhNjMwMjEtMjRjYy00ZGNkLWFhMDUtYThhOTQ1OTY0NDZlIiwidCI6IjliOTFmNGY2LWVmM2EtNDFkZS1hNWE4LTJkYTZkYjg2MDkxYSJ9" frameborder="0" allowFullScreen="true"></iframe>


**Advantages:**

- All services are cloud based, so no local hosting of data or no infra is required.
- Set up is easy and quick with the help existing Flow template. No coding is required. Seamless integration of all services.
- Trigger-based or time-based start of the flow is easily configurable.


**Drawbacks:**

- Twitter connector in Flow gives no fields related to twitter user profile info. So I guess important fields are missed during complex analytics.
- Power BI service has no feature of adding DAX to insert new column or measure. So limited scope of analysis in turn less visualization.

**References**

- [https://www.youtube.com/user/mspowerbi](https://www.youtube.com/user/mspowerbi "Power BI YouTube Channel")
- [https://www.youtube.com/watch?v=WWod8ETS7J8](https://www.youtube.com/watch?v=WWod8ETS7J8 "Demo by Leila Etaati")
- [https://india.flow.microsoft.com/en-us/galleries/public/templates/2680d2227d074c4d901e36c66e68f6f9/run-sentiment-analysis-on-tweets-and-push-results-to-a-power-bi-dataset/](https://india.flow.microsoft.com/en-us/galleries/public/templates/2680d2227d074c4d901e36c66e68f6f9/run-sentiment-analysis-on-tweets-and-push-results-to-a-power-bi-dataset/ "Flow Template")
- [https://azure.microsoft.com/en-in/services/cognitive-services/text-analytics/](https://azure.microsoft.com/en-in/services/cognitive-services/text-analytics/ "Congnitive Services")
