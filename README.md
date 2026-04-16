# Superstore-sales-analysis

         Project Overview
       
The objective of this project was to analyse a superstore sales dataset and build an interactive Power BI report that provides insights into sales performance, profitability, geographic distribution, customer segments, and product returns.
The final report was designed with four interactive pages:
1. Executive Overview
2. Sales & Profitability Analysis
3. Geographic & Segment Analysis
4. Returns & Shipping Analysis
The dashboard allows users to explore business performance using interactive filters, drill-through, and dynamic visualizations.

          Tools Used
   
Power BI Desktop
 The dataset contains three tables:
              Orders Table
              Returns Table
              People Table

          Data Cleaning and Transformation (Power Query)

Steps Performed
	1.	Loaded Excel dataset
	               Imported Orders, Returns, and People tables.
	2.	Checked Data Types
	                Converted dates to Date format
                               Sales, Profit and Discount converted to Decimal number
	3.	Removed Errors and Null Values
	               Verified missing values in key columns.
	4.	Merged Tables
	               Merged Orders table with Returns table using Order ID.
	5.	Merged People Table with Orders table using Region.
The cleaned data was then loaded into the Power BI data model.

            Data Modelling
            
  Relationships were created between tables.
  Orders (Order ID) → Returns (Order ID)
  Orders (Region) → People (Region)
  This created a star schema data model that provides efficient analysis.
        
            DAX Measures
            
Total Actual Profit = SUM (Orders [Actual Profit]), 
Total Orders = DISTINCTCOUNT (Orders [Order ID]),
Total Returns = DISTINCTCOUNT (Returns [Order ID]), 
Total Sales = SUM (Orders [Net Price]), 
YOY Growth % = DIVIDE ([Total Sales]- [Sales LY], [Sales LY]),
YOY Sales Growth = TOTALYTD ([Total Sales], Orders [Order Date]),
Sales LY = CALCULATE ([Total Sales], SAMEPERIODLASTYEAR (Orders [Order Date]. [Date])), 
Returned Orders = CALCULATE (COUNT (Orders [Order ID]), Orders [Returns. Returned] ="Yes"),
Return Rate % = DIVIDE ([Total Returns], [Total Orders],0), 
Profit Margin = DIVIDE (SUM (Orders [Actual Profit]), [Total Sales],0)

           Report Pages

Page 1 – Executive Overview

 KPI Cards used
                   Total Sales, Profit Margin, Return Rate, YoY Growth, Total Orders.

Visualizations Used
    Line ChartTotal Sales by Year
    Bar ChartTotal Sales by Region
	
Slicers
    Order Date, Region
	
Page 2 – Sales & Profitability Analysis

Visualizations Used
    Pie ChartSales by Category
    Waterfall ChartSales and Profit contribution by Category
     Bar ChartSales by Sub-Category
     Column ChartProfit Margin by Category
	 
Page 3 – Geographic & Segment Analysis

Visualizations Used
     Tree mapSales by State
     Donut ChartSales by Customer Segment
     Bar ChartSales by Customer Name
	 
Page 4 – Returns & Shipping Analysis

Visualizations Used
     KPIsTotal Orders, Total Returns 
     Area ChartReturned Orders by Segment
     Line ChartTotal Orders by Ship Mode
     Matrix TableTotal Sales, Profit, Discount, Return Rate, Profit Margin, YoY Growth

ScreenShots Of Dashboard

<img width="1366" height="768" alt="Index" src="https://github.com/user-attachments/assets/1c2150a6-a4c0-4292-ae42-63ab2edef56e" />
<img width="1366" height="768" alt="Executive overview" src="https://github.com/user-attachments/assets/7f25be28-0db1-4ef2-b411-70d39443dcac" />




     
