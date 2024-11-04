# LITA_CAPSTONE_PROJECT

##SALEDATA_PERFORMANCE
___

# SALES_DATA_PERFORMANANCE_ANALYSIS

##Project Documentation for Sales Performance Analysis and Customer Segmentation
Project 1: Sales Performance Analysis for a Retail Store


###Project Objective/Overview
---
•	This Data Analysis project aim to generate an insight into the sales performance of a retail store over the past year. Analyzing sales data to identify top-selling products, regional performance, and monthly sales trends by using various perimeters to evaluate sales performance from the data received and get enough insight to make reasonable decisions which them enable us to tell compelling stories around our data. 

•	Develop an interactive Power BI dashboard summarizing sales metrics.


 ###Data Sources
---
   The primary source of Data used here is SalesData from an Excel sheet provided by the LITA for the final project

•	File Name: SalesData

•	Key Columns: Product, Region, OrderDate, Quantity, UnitPrice

•	Data Notes: The dataset provides product-specific sales details across regions and timeframes.


 ###Tools Used
---
•	Excel: For data exploration, summary reports, and calculations.

•	MYSQL Server: Structured Query Language for Data querying and insight extraction.

•	Power BI: Visualization of findings.


 ###Data Cleaning And Preparation
---
In the initial phase of the Data cleaning and preparations, i perform the following actions:

- Data loading and Inspection

- handling missing variables

- Data cleaning and formating


 ###Exploratory Data Analysis
---
Exploratory Data Analysis  involved the exploring of the Data to answer some questions a bout the Data such as :

- What is the highest Sales Performance

- The highest Performing Region

- The top selling Product

- The overall Monthly sales Trend

###Data Analysis:
---
o	Utilized pivot tables to calculate total sales by product, region, and month.

o	Used formulas to compute metrics like average sales per product and total regional revenue.

o	Added a Power Query column to categorize sales volume as Low (1–20 units), Medium (21–50), or High (>50) based on the [Unit Sold] column, as provided in the attachment instructions (LITA CAPSTONE DATASET_S…).


•	###MYSQL Analysis:

o	After importing the dataset into MYSQL Server, the following queries were run to generate insights:

o	Total Sales by Product Category:


###Code:

SELECT * Product, SUM (Quantity * UnitPrice) AS TotalSales FROM SalesData GROUP BY Product;

o	Sales Transactions by Region:


###Code:

SELECT * Region, COUNT(OrderID) AS SalesTransactions FROM SalesData GROUP BY Region;

o	Highest-Selling Product by Total Sales:

###Code:

SELECT Product, SUM (Quantity * UnitPrice) AS TotalSales FROM SalesData GROUP BY Product ORDER BY TotalSales DESC LIMIT 1;

o	Monthly Sales for Current Year:

###Code:

SELECT MONTH(OrderDate) AS Month, SUM (Quantity * UnitPrice) AS MonthlySales FROM SalesData WHERE YEAR(OrderDate) = 2023 GROUP BY Month;

o	Top 5 Customers by Purchase Amount:

###Code:

SELECT CustomerId, SUM (Quantity * UnitPrice) AS TotalPurchase FROM SalesData GROUP BY CustomerId ORDER BY TotalPurchase DESC LIMIT 5;

o	Products with No Sales in the Last Quarter:

###Code:

SELECT Product FROM InventoryData WHERE Product NOT IN (SELECT DISTINCT Product FROM SalesData WHERE OrderDate >= '2023-07-01' AND OrderDate <= '2023-09-30');

•	Power BI Dashboard:

o	Visualized insights from Excel and SQL analysis to include:

	Sales overview

	Top-performing products

	Regional sales distribution

	Monthly sales trends


 ###Key Insights from Sales Performance Analysis

•	Top-Selling Product: Shoes had the highest sales at $3,087,500.

•	Regional Sales Contribution: The South region contributed the largest percentage of total sales at 44.16%.

•	Monthly Sales Trends: Highest monthly sales were recorded in February.

•	Top Customers: Customer Cus1488 had the highest purchase amount at $29,340.

###Visualization

![image](https://github.com/user-attachments/assets/7665aba5-87fe-4747-9a7f-7751b900a282)

![image](https://github.com/user-attachments/assets/a1254629-bc8f-4059-ba8e-d982e78af50b)





________________________________________


