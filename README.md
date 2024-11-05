 # LITA_Capstone_Project_SalesData
Documentation of my SALESDATA LITA Capstone Project in Data Analysis with Incubator Hub.

### Project Title: Capstone Project

[Project Overview](#project-overview)

[Objectives](#objectives)

[Data Sources](#data-sources)

[Tools Used](#tools-used)

[Methodology](#methodology)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Dashboard Visualization](#dashboard-visualization)

[Business Recommendations](#business-recommendations)

### Project Overview
---
This Project aims to effectively and accurately evaluate and enhance the sales performance of a retail store of an organization by systematically analyzing sales data. The project involves identifying trends, opportunities, measuring, and interpreting key performance indicators (KPIs) , identify high- and low-performing areas, and optimize sales operations. By leveraging data-driven insights, this analysis will provide actionable recommendations to optimize sales strategies, get better customer engagement, and drive business growth. The culmination of this analysis is presented in an interactive Power BI dashboard, designed to visually showcase these findings.


### Objectives
---
My objectives are to: 
- Understand overall sales trends over time.
- Identify top-performing products and categories.
- Analyze regional sales performance.
- Calculate key metrics such as total revenue, average sales per product, and customer spending.
- Visualize insights through an interactive Power BI dashboard.

### Data Sources
---
The primary data source used in this analysis was sourced from the retail store’s internal sales database, covering a detailed record of transactions, product categories, regional data, and customer interactions.

### Tools Used
---
- Microsoft Excel: 
  1. For initial Data cleaning and exploration.
   2. For pivot tables.
   3. For formular-based calculations.
- SQL - Structured Query Language for Querying Dataset to extract specific insights. 
- Power BI - For Data Visualization of insights found in Excel and SQL
- GitHub for Portfolio Building

### Methodology
---

#### 1. Excel Data Exploration

I started by diving into the sales data using Excel. Pivot tables helped me summarize total sales by product, region, and month. I didn't stop there—Excel formulas were utilized to calculate key metrics like average sales per product and total revenue by region. A thorough initial exploration revealed interesting trends and patterns which laid the foundation for my deeper analysis. A screenshot is in my files
At the initial phase of data cleaning and preparation, i prepared the following actions:
1. Data loading and inspection
2. Data cleaning and formatting: the data cleaning process was done using Excel to remove duplicates to ensure data accuracy.

#### 2. SQL Data Analysis

I loaded the dataset into SQL Server for in-depth querying and wrote queries to extract key insights.

#### 3. Power BI Dashboard Visualization

I imported the cleaned and analyzed data into Power BI and created visualizations to represent key findings on:
- Sales Overview
- Top-performing products and categories
- Regional sales comparison
- Incorporated various charts and graphs to make for easy understanding and action. 
- Interactive slicers to enable dynamic analysis

### Exploratory Data Analysis
---
EDA involves the exploring of the Data to answer some questions about the data.

After cleaning the data in Excel, i started the analysis and dashboard creation. In Excel, the following steps were carried out:

**Descriptive Statistics:** Calculated basic statistics and analyzed distributions.

**Visualization:** Created charts and graphs to visualize trends and patterns.

**Dashboard Creation:** Developed interactive dashboards to present key findings effectively.

 ### Data Analysis
 ---
 This is where I included some basic lines of code or queries and even some of the DAX functions used during my analysis such as:
 - Perform an initial exploration of the sales data. Use pivot tables to summarize total sales by product, region, and month.
 - Use Excel formulas to calculate metrics such as average sales per product and total revenue by region.
 - Create any other interesting report

#### SQL Queries

**Insights with SQL**


Retriev the total sales for each product category.
o find the number of sales transactions in each region.
o find the highest-selling product by total sales value.
o calculate total revenue per product.
o calculate monthly sales totals for the current year.
o find the top 5 customers by total purchase amount.
o calculate the percentage of total sales contributed by each region.
o identify products with no sales in the last quarter.
 


**Insights with SQL**

With my dataset loaded into SQL Server, i crafted queries to pull out critical insights such as:

Retieving the Total Sales by Product Category
```SQL
Select Product,sum(Total_Sales) as TotalSales from[dbo].[LITA SALES DATA]
Group by product
```
Finding the number of Sales Transactions in each Region
```SQL
Select Region,Count(OrderID) as No_of_Salestransaction from[dbo].[LITA SALES DATA]
Group by Region
```
Finding the highest-Selling Product by Total Sales value
```SQL
Select Product,Sum(Total_Sales) as Highest_selling_Product from[dbo].[LITA SALES DATA]
Group by Product
Order by 2 desc
```
Calculating the Total Revenue Per Product
```SQL
SELECT product, SUM(Total_Sales) AS Total_Revenue FROM[dbo].[LITA SALES DATA]
GROUP BY product;
```
Calculating the monthly Sales Total for the current year
```SQL
Select OrderDate, sum(Total_Sales) as MonthlySales from[dbo].[LITA SALES DATA]
Where OrderDate between '2024-01-01' and '2024-12-31'
Group by OrderDate
Order by OrderDate
```
Finding the Top 5 Customers by total purchase amount
```SQL
Select top 5 Customer_Id,sum(Total_Sales) as TotalPurchase from[dbo].[LITA SALES DATA]
Group by Customer_Id
Order by TotalPurchase desc
```
Calculating the Percentage of Total Sales Contributied by each Region
```SQL
SELECT Region, 
       SUM([Total_Sales]) AS Sales, 
       ROUND((SUM([Total_Sales]) * 100 / (SELECT SUM([Total_Sales])
	   FROM[dbo].[LITA SALES DATA])), 2) AS SalesPercentage
FROM[dbo].[LITA SALES DATA]
GROUP BY Region;
```
Identifying Products with no sales in the last quarter
```SQL
SELECT product from[dbo].[LITA SALES DATA]
GROUP BY product
HAVING max(OrderDate) < Dateadd(QUARTER, -1, Getdate());
```

### Dashboard Visualization
---

#### Excel Dashboard Overview

![SalesData Pivot](https://github.com/user-attachments/assets/c2e0c081-c839-47a2-96f7-cd645bbb108a)

#### Power BI

The Power BI dashboard i created synthesized all these insights found in Excel and SQL. The dashboard includes a sales overview, top-performing products, monthly sales trend, and regional breakdowns.
 
**Power BI Visualization**


![PowerBI Data Visualization](https://github.com/user-attachments/assets/1dbbef3a-0f43-4aa4-8838-6b6b309325d2)



![PowerBI Data Visualization1](https://github.com/user-attachments/assets/ec8ef3cc-7fdd-4c73-84c4-9558fb87edc5)


### Business Recommendations
---

Based on the insights gained from the analysis and dashboard, my provided recommendations are:

- Product Strategy: Focus should be on promoting top-selling products and discontinuing low-performing ones.
- Regional Strategy: Investing in marketing and sales efforts in high-potential regions is adviced.
- There should be Implementing loyalty programs to retain high-value customers and target low-value customers with personalized offers.

This comprehensive approach not only provided deep insights into the retail store’s sales performance but also armed stakeholders with the information needed to make strategic decisions. This story not only showcases analytical skills but also the ability to transform data into actionable business intelligence.


