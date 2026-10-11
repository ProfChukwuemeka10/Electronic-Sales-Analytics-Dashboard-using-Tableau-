# Electronic-Sales-Analytics-Dashboard-using-Tableau-
An interactive Tableau dashboard that analyzes electronic product sales data. It provides insights into sales performance by city, product rankings (Top/Bottom 10), weekly sales trends, and warranty end dates.

Project Overview
This dashboard explores an electronic sales dataset containing order details, products, quantities, prices, order dates, and purchase addresses. Key analytical capabilities include:

Sales performance by city (toggle between Total Sales and Average Sales)
Product ranking by sales revenue (switch between Top 10 and Bottom 10)
Weekly total and average sales trends
Warranty end date tracking (6 months after order date)
Interactive filtering across views via dashboard actions

The workbook uses parameters and calculated fields to enable dynamic analysis while maintaining a clean, user-friendly interface.
Data Source

Source File: Electronic Sales.xlsx
Key Fields:
Order ID
Product
Quantity Ordered
Price Each
Order Date
Purchase Address


Calculated Fields

FieldDescriptionSalesQuantity Ordered * Price EachCityExtracted from Purchase Address (TRIM(SPLIT([Purchase Address], ",", 2)))Valid RecordFilters out incomplete records (null Order Date, Price, Quantity, or Product)Selected City SalesSwitches between SUM(Sales) and AVG(Sales) based on parameterSelected Product RankDense rank of products by Sales (descending for Top 10, ascending for Bottom 10)Warranty End DateDATEADD('month', 6, [Order Date])IndexRow index used for ranking display

Parameters

ParameterOptionsPurposeProduct Ranking ViewTop 10 / Bottom 10Controls product ranking directionCity Sales MeasureTotal Sales / Average SalesControls the measure shown in the City view

Dashboard Structure
Dashboard 1 contains the following worksheets with interactive filter actions:

City Sales Measure by City
Horizontal bar chart showing sales (total or average) by city, sorted descending.
Products by Sales Revenue
Ranked list of products filtered to the selected Top/Bottom 10.
Warranty End Date
Detailed view of Order ID, Product, Order Year, and calculated Warranty End Date.
Weekly Average Sales
Trend of average sales by weekday.
Weekly Total Sales
Trend of total sales by weekday.

Selecting marks on one view filters related views (with some exclusions to preserve context).
Key Features

Parameter-driven switching between Total vs Average Sales and Top vs Bottom product rankings
Cross-filtering between sheets via dashboard actions
Clean formatting with currency labels and sorted views
Focus on valid records only
Color encoding by City for visual consistency

How to Use

Open the .twb file in Tableau Desktop (or Tableau Public).
Use the Product Ranking View parameter to switch between Top 10 and Bottom 10 products.
Use the City Sales Measure parameter to toggle between Total and Average Sales.
Click on bars, products, or other marks to filter related views.
Explore the Warranty End Date sheet for order-level detail.

Technical Notes

Built in Tableau 2023.1
Data connection is Excel Direct
Shared filter for valid records
Table calculations used for ranking and indexing
Dashboard actions configured for selective filtering between worksheets
