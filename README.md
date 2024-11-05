# LITA_Class_Customer_Data

## OUTLINE 
[Project Title](#project-title) 

[Project Overview](#project-overview) 

[Key Findings](#key-findings)

[Data Source](#data-source)

Methodology 

Data Cleaning and preparation

[Data Visualization](#data-visualization) 



### Project Title: Customer Subscription Data

### Project Overview 

This Data Analysis project aims to generate insights into customer data for a subscription service to identify segments and trend over the previous years. By analysing the various parameters in the data received I explored customer data to understand customer behaviour, subscription duration and  subscription types to make reasonable decisions in promoting better services to the customers.

### Key Findings
Identify key trends in:
- Cancellations and
- Renewal of subscription plans


### Data Source

The primary source of the Data used is LITA Capstone Project- Customer Data.xslx

#### Tools used/Methodology 
------
- Microsoft Excel [Download Here](https://www.microscoft.com)
  1. Data cleaning
  2. Analysis
  3. Visualization
- SQL- Structured Query Language
- Power BI- Power Business Intelligence for Data Visualization
- GitHub for Portfolio building

### Data cleaning and preparation 
----
Some basic action were taken, they include:
1. Data downloading from LMS (LITA- Data Analysis Class)
2. Data loading from each platforms such as Excel, SQL and Power BI
3. Data Inspection- Highlighting, inserting into tables and changing formatting or possible errors/blank space
4. Data Cleaning

#### Data Analysis
----
This is where we include some basic lines of code or queries and some DAX expressions used during the analysis;

-----Total number of customer from each region----
``` SQL
Select Sum (CustomerId) as TOTALNORTHSALES From [LITA Customer Data]
where region = 'north'
```
-----Most popular subscription type----
select SubscriptionType,
Where product = 'Shirt'
