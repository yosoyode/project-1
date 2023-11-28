# Analysis Post-University Salaries of Graduates by Major 

## Table of Content

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Analysis](#data-analysis)
- [Reccomendations](#reccomendations)

  
  
 
### Project Overview
This project aims to provide insights into the sales performance of an e-commerce company over the past years. By analysing various aspect of the sales data. we seeek to identify trends, make data-driven decisons, and gain deeper understanding of the company's performance.

### Data Sources
Source: PayScale Inc. - 'salaries_by_college_major.csv'

### Tools
1. Pyhton (pandas) - Data exploration and Data cleaning
2. pyhton (numpy) - Data analysis and manipulation
3. python (matplotlib) - Data plotting
4. python (seaborn) - Data visualisation


### Data Cleaning and Preparation
1. Data loading and inspection
2. Checking and handling missing values
3. Data cleaning and Formartting

### Exploratory Data Analysis 

The exploratory analysis involves exploring the available data to provide answers to questions such as:
1. Which degrees have the highest starting salaries?
2. Which majors have the lowest earnings after college?
3. Which degrees have the highest earning potential?
4. What are the lowest risk college majors from an earnings standpoint?
5. Do business, STEM (Science, Technology, Engineering, Mathematics) or HASS (Humanities, Arts, Social Science) degrees earn more on average?

#### Data analysis
I Used .head(), .tail(), .shape and .columns to explore my DataFrame and find out the number of rows and columns as well as the column names.

I looked for NaN (not a number) values with .findna(), i also used .dropna() to clean up my DataFrame.

I accessed the entire columns of the DataFrame using the square bracket notation: df['column name'] or df[['column name 1', 'column name 2', 'column name 3']]

I accessed individual cells in my DataFrame by chaining square brackets df['column name'][index] or using df['column name'].loc[index]

I also check for largest and smallest values, as well as their positions, can be found with methods like .max(), .min(), .idxmax() and .idxmin()

I sort the DataFrame with .sort_values() and add new columns with .insert()

I used the .groupby() method to create an Excel Style Pivot Table by grouping entries that belong to a particular category.


### Results and Findings

The analysis results are summarised as follows
1. 


### Reccomendations 

Based on the analysis, we reccomend the following actions:




### limitations

I had to remove all zero values from the revenue column, because they would have affected the accuracy of the analsyis, although there are still few outlieirs in the conclusions, but it is hard to over look the efffect in which high inflation has on crime rate due to their correlation.

