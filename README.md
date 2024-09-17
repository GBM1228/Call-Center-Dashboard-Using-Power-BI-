# PwC Switzerland Power BI Job Simulation on Forage-Call Centre Trends

<img width="670" alt="Call center" src="https://github.com/user-attachments/assets/524dc92f-80c9-4832-980a-2660441fed35">

## About This Project

For my second task in the PwC Virtual Internship on Power BI, I designed a comprehensive dashboard centered on Call Center Trends. As a Data Analyst, 
my responsibilities included Creating a dashboard in Power BI for Claire that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset. 

## Table Of Contents

[Problem Statement](#ProblemStatement)

[Data Sourcing](#DataSourcing)

[Data Preparation](#DataPreparation)

[Data Visualization](#DataVisualization)

[Data Analysis](#DataAnalysis)


## Problem Statement

The main objective of this analysis is to:

* Create a dashboard in Power BI for Claire that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset. Get creative! 

Possible KPIs include (to get me started, but not limited to):

* Overall customer satisfaction
* Overall calls answered/abandoned
* Calls by time
* Average speed of answer
* Agent’s performance quadrant -> average handle time (talk duration) vs calls answered

  ## Data Sourcing

The Dataset used for this analysis was given by [Pwc switzerland](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html)

[Dataset](https://github.com/user-attachments/files/17021041/01.Call-Center-Dataset.1.xlsx)

## Data Preparation

Data transformation was performed using Power Query, followed by loading the refined dataset into Microsoft Power BI Desktop for in-depth analysis and reporting.

The dataset for Call Centre Trends has 11 columns and 5000 rows.

|Column Name|
|---|
|Call Id	|
|Agent|
|Date|
|Time|
|Call Reason|
|Call Status|
|Disposition|
|Response Speed|
|AvgTalkDuration|
|Customer Satisfaction|
|Day|

The following steps were taking for the data cleaning and transformation  :

* Promoting headers 
* Changing data types
* Added conditional column
* Reordered columns
* Renaming Column name for clarity
* Exstracted minute
* Renaming Column name for clarity
*  Duplicated column
*  Exstracted day name

## Data Visualization

Microsoft Power BI Desktop was utilized to create a data visualization, uncovering key insights and trends within the dataset:

##### Call cCenter Dashboard shows the :

* Total Calls
* Total Answered Calls
* Total Abandoned Calls
* Resolved Calls%
* Not Resolved Calls%
* Total Agents
* Total Calls by Agents
* Total Calls by Day
* Calls by Reasons%
* Calls by Customers Satisfaction
* Average Talk Duration and Response Speed by Agents
* Agents Performance
<img width="670" alt="Call center" src="https://github.com/user-attachments/assets/b13d7c76-1efe-4b22-88e5-6ddd975168f9">

## Data Analysis

The following measures were developed:

* Total Calls = COUNT('Cleaned Data'[Call Id] )+0
* Total Answered calls = COUNTX(FILTER('Cleaned Data', 'Cleaned Data'[Call Status] = "Answered"), 'Cleaned Data'[Call Id]) +0
* Total Calls Abandoned = COUNTX(FILTER('Cleaned Data', 'Cleaned Data'[Call Status] = "Abandoned"), 'Cleaned Data'[Call Id])+0
* Total calls Resolved = COUNTX(FILTER('Cleaned Data', 'Cleaned Data'[Disposition] = "Resolved"), 'Cleaned Data'[Call Id])+0
* Total Calls Not Resolved = (COUNTX(FILTER('Cleaned Data', 'Cleaned Data'[Disposition] = "Not Resolved"), 'Cleaned Data'[Call Id]))+0
* Total Agents = DISTINCTCOUNT('Cleaned Data'[Agent])+0
* Total customers satisfied = COUNTX(FILTER('Cleaned Data', 'Cleaned Data'[Customer Satisfaction] = "Satisfied"), 'Cleaned Data'[Call Id])+0
* Total customers Not Satisfied = COUNTX(FILTER('Cleaned Data', 'Cleaned Data'[Customer Satisfaction] = "Not Satisfied"), 'Cleaned Data'[Call Id])+0
* Average response speed = AVERAGE('Cleaned Data'[Response Speed])+0
* %Resolved Calls = DIVIDE([Total calls Resolved],[Total Calls])+0
* %Not Satisfied calls = ([Total customers Not Satisfied]/[Total Calls]*100)+0
* %Not Resolved Calls = DIVIDE([Total Calls Not Resolved],[Total Calls])+0
* %Answered Calls = ([Total Answered calls]/[Total Calls]*100)+0
* %Abandoned calls = ([Total Calls Abandoned]/[Total Calls]*100)+0
* %Satisfied = ([Total customers satisfied]/[Total Calls]*100)+0


