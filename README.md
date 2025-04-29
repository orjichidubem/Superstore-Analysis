# Superstore-Analysis

### Project Overview
---
This project analyzes superstore sales dataset, this analysis explores sales performance, customer behavior,  and identify trends, insights and recommendation for business improvement.

### Data Source
The analysis is based on the "superstore.csv dataset" sourced from a retail company internal sales database, containing the following information on:

- CustomerID.
- Region.
- Postal Code.
- Customer Name.
- Product Nmae.
- Country.
- city.
- state.
- Sales.
- Quantity.
- Profit.
- OrderID.
- Order Date.

### Tools
1. Excel: Data Cleaning.
2. SQL Server: Data Analysis.
3. PowerBI: Data Visualization.

### Data Cleaning

Data cleaning was carried out at the intial stage to ensure data quality. The following task were performed:
1. Data cleaning and inspection.
2. Removal of duplicates.
3. Data cleaning and formatting.
4. Creating additional numeric columns.

### Exploratory Data Analysis

The EDA process involves analyzing the Superstore sales dataset to understand the distribution of variables, identify patterns and trends, detect potential issues, and answer key questions: 

1. What is the overall sales trend.
2. Top 10 customers.
3. Top 10 sub-categories based on profit.
4. Sales by state and city.
5. Sales by ship mode.

### Data Analysis 

Data analysis was done by SQL Server.

```SQL
--Q1. What is the overall sales trend.
select order_date, ship_date, sales
from superstore
where order_date between '2014-01-01' and '2017-12-31'
and ship_date betwwen '2014-01-01' and '2017-12-31'
order by order_date, ship_date asc;
```

```SQL
--Q2. Top 10 customers.
select top 10 Customer_Name, sum(sales) as TotalPurchase
from superstore
group by Customer_Name
order by TotalPurchase desc;
```

```SQL
--Q3. Top 10 sub-categories based on profit.
select top 10 sub_category, sum(profit) as ToalProfit
from superstore
group by sub_category
order by TotalProfit desc;
```

```SQL
--Q4. Sales by state and city.
select state, city, sum(sales) as sales_by_location
from superstore
group by state, city
order by sales_by_location desc;
```

```SQL
Q5. Sales by ship mode.
select ship_mode, sum(sales) as sales_by_shipmode
from superstore
group by ship_mode
order by sales_by_shipmode desc;
```

### Results And Findings

The analysis of superstore sales data from 2014 to 2017 reveals:
1. Overall sales trend shows steady growth with seasonal fluctuations.
2. The top 10 customers contribute significantly to sales.
3. Sales vary by region, with the south region leading the pack.
4. Copies and phones sub-categories drive sales and profitability.

These findings provide insights into sales performance, customer behavior, and product trends, informing strategic decisions to drive growth and improvement.

### Recommendations

Based on my analysis, here are some recommendations:

1. Focus on high demand product. Ensure that the high demand product sub-categories are always in stock.
2. Offer personalized service to key accounts to build strong relationships and increase customer satisfaction.
3. Invest in marketing effort on high growth regions, such as the south region.
4. Analyze shipping data to identify opportunities to reduce costs and improve efficiency.
5. Consider expanding product offerings in high growth categories.
6. Regularly analyze sales data to identify trends, opportunities and challenges.

### Limitations 

- The analysis is based on a specific data-set (2014-2017) and may not reflect current market trends or conditions.
