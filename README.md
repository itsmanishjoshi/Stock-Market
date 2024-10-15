# Stock Market Analysis Project

## Table of contents
- [Project Overview](#Project-Overview)
- [Business Demand Letter](#Business-Demand-Letter)
- [Business Request and user stories](#Business-Request-and-user-stories)
- [Tools used](#Tools-used)
- [Data Preperation](#Data-Preperation)
- [Data Cleansing & Transformation](#Data-Cleansing-&-Transformation)
- [Data Modeling](#Data-Modeling)
- [Data Visualisation](#Data-Visualisation)
- [Data Source](#Data-Source)
- [Results / Findings](#Results-Findings)
- [Conclusion](#Conclusion)


## Project Overview
This Data Analysis Project aims to provide comprehensive insights into stock market performance over the past few years. By analyzing historical stock data, the goal is to identify market trends, evaluate stock price movements, and derive actionable insights for making data-driven investment decisions. The project will help investors better understand stock behaviors over time and against benchmarks.

## Business Demand Letter [View]
Client: John – Portfolio Manager

Hi Manish,

I hope you are doing well. We are looking to improve our stock analysis reports and transition from basic charts to more advanced visual dashboards. Specifically, we want to focus on stock price movements over time, comparing performance across sectors and individual companies. It would also be beneficial to filter by various factors like stock symbols, industries, and time periods. Additionally, we often compare stock performance against market indices, so I've included historical index data in a spreadsheet. Our primary focus will be on the past 4 years of data, and I would like a dashboard that allows for easy comparison. Let me know if you need any further details.

Best regards,
John

## Business Requests and User Stories View

1. Portfolio Manager: To get a dashboard overview of stock market performance over time.
2. Investment Analyst: A detailed overview of stock price movements by individual stock symbols.



## Tools Used
- Pandas: Data Cleaning, Data Wrangling, and Analysis
- Tableau: Creating Interactive Visualizations and Dashboards

## Data Preparation
During the initial data preparation phase, the following tasks were performed:

1. Data loading and inspection.
2. Handling Missing Data.
3. Data cleaning and preperation.

## Data Cleansing & Transformation (Pandas)
To create a functional data model for analysis and meet the business requirements laid out in the user stories, the following transformations were performed using Pandas:

1. Merging stock price data with industry and sector information.
2. Calculating moving averages and stock returns over specified time periods.

Below are some panda's code for cleansing and transforming necessary data.
