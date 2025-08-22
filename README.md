# PowerBI_Projects
**Project1- Sales**

# Sales-Report

## Problem Statement

This dashboard helps the Business owners understand their customers and sales better. By analyzing historical and current sales records, the project focuses on uncovering insights such as top-performing products, customer purchasing behavior, seasonal demand fluctuations, and regional market performance. The objective is to transform raw sales data into actionable insights that support data-driven decision-making. Through visualization, reporting, and forecasting techniques, the project will help stakeholders optimize sales strategies, improve customer targeting, manage inventory effectively, and ultimately enhance overall revenue growth.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a Microsoft Excel Workbook.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : Checked the Datatype of columns in all table. Changed the datatype of Id columns to Text.
- Step 5 : In Promotion table the column names were in second row. Selected the Use first row as headers under Transform.
- Step 6 : In Promotion table added a percentage column using add conditional column based on the price reduction type column to change into numerical value.
- Step 7 : In Fact table few columns were having null values. To fill up that merged Product and Promotion table with Fact table using left outer join on ProductId and PromotionId.
- Step 8 : Price per unit Column added from Product table.
- Step 9 : To get Total sales selected custom column under add column and gave the custom column formula as  Unit Sold* Price Per Unit.
- Step 10 : Discount percentage column added from Promotion table, Also replaced null values with 0.
- Step 11 : To get Discount value selected custom column under add column and gave the custom column formula as (Total Sales * Discount percentage)/100. Changed the datatype to Decimal.
- Step 12 : To get Net Sales selected custom column under add column and gave the custom column formula as Total Sales - Discount. Changed the datatype to Decimal.
- Step 13 : Close and Apply. The transformed data is loaded into PowerBI Desktop.
- Step 14 : Created Data model : Created one to many relationship between Product, Customers and Promotion Table.
-  Step 15 : **Business Requirements**
-    1) Top/Bottom 5 product by Sales/Profit/Quantity Sold.
     2) How do sales trends vary over time (daily, monthly, quarterly, annually)
     3) Show relationship between sales & profit.
     4) Compare sales/profit/quantity sold between any two periods selected by the user.
     5) Average discount offered in each discount category.
     6) Total number of orders.
     7) Show Sales/Profit/Discount/Net Sales/All remaining fields for each order that could be filtered using visual filters. (Product/Date/Customer ID/Promotion Categories)
     8) Show sales by different cities.
- Step 16 : Added a Profit column by assuming Profit value is 10% of Net Sales.
- Step 17 : **Creating Report**
  
-    1) Added separate stacked bar chart for Top and Bottom for Sales, Profit and Quantity. Added Product Name in the Y-axis and Sum of Net Sales in the X-axis. Added Filter based on Product Name for Top 5 and Bottom 5 values by Net Sales.
     2) Added Line chart to Show the Sales Trends over time. Added Date in x-axis and Net Sales in Y-axis.
     3) Added Sacatter Plot to show the relationship between Sales and Profit. X- axis Profit and Y-axis Net Sales without summarizing.
     4) Created two new Tables Date Table 1 and Date Table 2 using CALENDERAUTO() Function. Added two Visual filters (Slicers) for requiremnt 4. Updated the Data Model with these tables. For Date Table 1 created a one to many active relationship and for Date Table 2 created a one to many inactive relationship. Created new measure for Second Date filter since the relationship is inactive. Added Clustered column charts to represent the Sales, Profit and Quantity.
     5) Added Stacked bar chart to show Average discount offered in each discount category. In the x-axis Average Discount Y-axis Promotion Name. To remove the blank unchecked the Black in Filter.
     6) Added Card to show the Total Number of Orders. Added Index column starting from 1 and renamed it to order ID to get the order count. Added order ID in the fields and give distinct count.
     7) Added Table Visual for requirement 7 and Added all columns from Fact table into columns. Added Slicer for filtering based on Date, Customer Name, Product Name and Promotion Names. Added  a Sum column for calaculate sum of Net Sales of Fact Table. Added the sum in th filters and set Show items when the value is not blank. Which will help filtering all the filters based on one selection. 
     8) Added Map visual to show the Sales for different Cities. Changed Data Category to City and added City to Location. Added Net Sales to Bubble size.


  
           
           Although, by default, while calculating average, blank values are ignored.
