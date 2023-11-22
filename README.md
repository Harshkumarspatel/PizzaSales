# PizzaSales
Data Analysis of Pizza Sales record

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results](#results)
- [Recommendations](#recommendations)

### Project Overview
This data analysis project aims to provide valuable insight into the sales performance of a pizza store over a year. By analyzing various aspects of the sales data, I seek to indentify trends over months and days, gain deeper understanding of store's performance and make data driven recommendations.



![image](https://github.com/Harshkumarspatel/PizzaSales/assets/151779392/a38077f7-ec38-4028-bd8d-f38a3c464e8d)



### Data Sources
The primary dataset used here is the "pizza_sales.csv" file. Which contain detail of every pizza sold by the store.

### Tools
- Excel - for data cleaning
- MySQL - for data analysis
- PowerBI - to create report 

### Data Cleaning
In the initial data preparation phase following tasks were performed:
1. Data loading and Inspection
2. Handling missing values
3. Data cleaning and formatting

### Exploratory Data Analysis
EDA involved exploring sales data to answer following questions:
- What are the peak sales days/months?
- Which pizza categories are top sellers?
- Which size of pizza is highest seller?

### Data Analysis
Some the MySQL queries were used as follows:
#### Monthly Trend for Orders
```sql
select DATENAME(MONTH, order_date) as Month_Name, COUNT(DISTINCT order_id) as Total_Orders
from pizza_sales
GROUP BY DATENAME(MONTH, order_date);
```
#### % of Sales by Pizza Category
```sql
SELECT pizza_category, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue,
CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT
FROM pizza_sales
GROUP BY pizza_category;
```

### Results

1. Month of January is best performing for the store while May is worst performing month.

![image](https://github.com/Harshkumarspatel/PizzaSales/assets/151779392/eaf7119c-98ce-4589-a0db-b32034a711b4)


2. The revenue of pizza sales is almost equal for all pizza categories where Classic category have minor lead over the others, As it also have the highest number of pizza sold over the year.

![image](https://github.com/Harshkumarspatel/PizzaSales/assets/151779392/d9422144-4547-4308-a52f-b20595c74425)


3. The large size pizza is best performing pizza size for the store with above 46% share.

![image](https://github.com/Harshkumarspatel/PizzaSales/assets/151779392/23836d00-b9c8-4c5b-853f-3e2f92fea5b7)


### Recommendations
Based on the analysis, I recommend following actions to the store:
- Focus on the weekends sales, store can give some offers to the customers during these days.
- Same way during summer vacation time, store can do some marketing to increase sales.
- Store can add some new category to attract customers.



 
