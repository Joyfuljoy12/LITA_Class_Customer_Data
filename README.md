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
```SQL
select SubscriptionType,
        CASE
          WHEN SubscriptionType IN ('Basic') then '1'
          WHEN SubscriptionType IN ('Premium') then '2'
          Else '3'
End as SubscriptionGroup,
sum(Revenue) as Totalsales from [LITA Customer Data]
where CustomerId in ('201', '202','203','204', '205', '206', '207', '208', '209', '210')
Group by SubscriptionType
order by 3 asc
```
-----Total revenue by subscription ----
``` SQL
Select Sum (revenue) as BASICREVENUE From [LITA Customer Data]
where SubscriptionType = 'Basic'
```
-----Top 3 region----
``` SQL
Select top 3 * from [LITA Customer Data]
where cancelled in (1,0)
```

-----Total number of active cancellation----
``` SQL
Select count (Canceled) as ACTIVECANCELLATION From [LITA Customer Data]
where canceled = 1
```

-----Total number of false cancellation----
``` SQL
Select count (Canceled) as falseCANCELLATION From [LITA Customer Data]
where canceled = 0
```

-----Canceled their subscription within 6 months----
```SQL
select CustomerId,
        CASE
          WHEN CustomerId IN ('201') then '1'
          WHEN CustomerId IN ('202') then '2'
          WHEN CustomerId IN ('203') then '3'
          WHEN CustomerId IN ('204') then '4'
          WHEN CustomerId IN ('205') then '5'
          WHEN CustomerId IN ('206') then '6'
          WHEN CustomerId IN ('207') then '7'
          WHEN CustomerId IN ('208') then '8'
          WHEN CustomerId IN ('209') then '9'
          Else '0'
End as CustomerId,
count(Canceled) as Totalcanceled from [LITA Customer Data]
where SubscriptionSTART in ('2022-01-31', '2022-06-30') AND Cancled in (0)
Group by CustomerId
```
-------Average subscription duration----
```SQL
Select avg (subscription_duration) as average from [LITA Customer Data]
```
#### Data Visualization

![image](https://github.com/user-attachments/assets/07b091ed-0630-4bc6-931d-5b59c3b4d56d)

![image](https://github.com/user-attachments/assets/3915d921-9c88-4192-9874-1b9afc583694)

![image](https://github.com/user-attachments/assets/681c78c7-6df0-4d7f-be03-74f5dcd8c1f9)


