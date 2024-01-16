# Google Play Store App Analytics

## Table of Content

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data cleaning ](#Data-Cleaning)
- [Data Analysis](#Data-Analysis)
- [Data Visualisation](#Data-Visualisation)
- [Limitations](#Limitations)

### Project Overview
Have you ever thought about building your own an iOS or Android app? If so, then you probably have wondered about how things work in the app stores. we'll replicate some of the app store analytics provided by companies like App Annie or Sensor Tower that helps inform development and app marketing strategies for many companies. This stuff is BIG business!

In this Project, I will compare thousands of apps in the Google Play Store so that i can gain insight into:

How competitive different app categories (e.g., Games, Lifestyle, Weather) are

Which app category offers compelling opportunities based on its popularity

How many downloads you would give up by making your app paid vs. free

How much you can reasonably charge for a paid app

Which paid apps have had the highest revenue

How many paid apps will recoup their development costs based on their sales revenue

### Data Sources
App and review data was scraped from the Google Play Store by Lavanya Gupta in 2018. Original files listed [here](
https://www.kaggle.com/lava18/google-play-store-apps).

### Tools
1. Excel Spreadsheet
2. Python Libriaries (Pandas, Matplotlib, Numpy, Seaborn, plotly) 

### Data Cleaning: Removing NaN Values and Duplicates
1. Drop Unused Columns .drop(axis=1)
2. Find and Remove NaN values in Ratings using .dropna()
3. Find and Remove Duplicates using  .drop_duplicates()

### Exploratory Data Analysis 
***The Highest Ratings, Most Reviews, and Largest Size***

1. I find the highest ratings using .sort_values('Rating', ascending=False)
Only apps with very few reviews (and a low number on installs) have perfect 5 star ratings (most likely by friends and family).

2. I find 5 Largest Apps in terms of Size using .sort_values('Size_MBs', ascending=False)
Here I can clearly see that there seems to be an upper bound of 100 MB for the size of an app. A quick google search would also have revealed that this limit is imposed by the Google Play Store itself. It’s interesting to see that a number of apps actually hit that limit exactly.

3.I find the 5 App with Most Reviews .sort_values('Reviews', ascending=False)
After looking at the number of reviews, I find the most popular apps on the Android App Store which includes (Facebook, WhatsApp, Instagram etc).
What’s also notable is that the list of the top 50 most reviewed apps does not include a single paid app.

#### Plotly Pie and Donut Charts - Visualise Categorical Data: Content Ratings
1. I count the number of occurrences of each rating with .value_counts()

2. I Visualise the content rating with a popular data visualisation library (Plotly), it can be used alongside or instead of Matplotlib.
I created a pie chart by calling px.pie() and then .show() to show the resulting figure, while using .update_traces() to configure other aspects of the chart that I can’t see in the list of parameters.

***Data Cleaning & Converting Data to Numeric Types***
I was able to check the data types using .describe() on the column and .info() on the DataFrame, both installs and price columns shows a non-numeric data type.
I removed the comma (,) character and any other character from the DataFrame using the string’s .replace() method. I then convert the data to a number using .to_numeric().

### Data Analysis
Finding the most Expensive Apps and Calculate a (ballpark) Sales Revenue Estimate
1. I Converted the price column to numeric data.
2. I Remove all apps that cost more than $250 from the DataFrame.
3. Added a column called 'Revenue_Estimate' to the DataFrame.

### Data Visualisation
***Plotly Bar Charts & Scatter Plots: The Most Competitive & Popular App Categories***
1. I used .value_counts() to calculate the number of apps per category
2. I visualised it by creating a plotly bar chart by caling px.bar() and then .show to show the result figure.

Based on the number of apps, the Family and Game categories are the most competitive. Releasing yet another app into these categories will make it hard to get noticed.
But looking at it from a different perspective? What matters is not just the total number of apps in the category but how often apps are downloaded in that category. This will give me an idea of how popular a category is.

### limitations
I had to convert the price column from object data type to numerical in other to be useful for analysis, this would have affected the accuracy of the analsyis.







I had to remove all zero values from the revenue column, because they would have affected the accuracy of the analsyis, although there are still few outlieirs in the conclusions, but it is hard to over look the efffect in which high inflation has on crime rate due to their correlation.

