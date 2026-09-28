# 🛒 E-Commerce Sales & Profitability Analysis

An end-to-end **E-Commerce Sales Analytics project** using **SQL, Excel, and Power BI** to analyze sales performance, profitability, customer behavior, product performance, regional performance, and order trends.

The project follows a complete analytics workflow:

**Raw Data → SQL Analysis → Excel Analysis → Power BI Data Modeling → DAX → Business Insights**

---

## 📊 Project Overview

This project analyzes **1,500 e-commerce transactions** across products, categories, customers, regions, payment methods, and order statuses.

The objective was to transform raw transaction data into meaningful business insights and answer questions such as:

- Which products generate the highest revenue?
- Which products and categories are most profitable?
- Which regions generate the highest sales and profit?
- Which customers contribute the most revenue?
- What is the overall profit margin?
- Which payment method is most frequently used?
- What are the return and cancellation rates?
- How does sales performance change over time?

---

## 🛠️ Tools & Technologies

- **SQL** – Data querying, aggregation, segmentation and ranking
- **Microsoft Excel** – Data analysis, Pivot Tables, Pivot Charts and dashboard
- **Power BI** – Data modeling, interactive dashboards and visualization
- **DAX** – KPI calculations, profitability and performance analysis
- **Power Query** – Data cleaning and transformation

---

## 📌 Key KPIs

| KPI | Result |
|---|---:|
| Total Sales | **₹2.13 Cr** |
| Total Profit | **₹53.96 Lakh** |
| Total Orders | **1,500** |
| Total Customers | **249** |
| Average Order Value | **₹14,227** |
| Profit Margin | **25.29%** |
| Total Quantity Sold | **3,361** |

---

# 🔍 SQL Analysis

SQL was used to perform the initial data analysis and answer business questions.

### Analysis performed

- Total sales and profit
- Total orders and customers
- Sales by category
- Sales by region
- Profit by category
- Profit by region
- Top-selling products
- Most profitable products
- Top customers
- Customer segmentation
- Monthly sales analysis
- State-level profitability
- Order status analysis

### Example SQL Query

```sql
SELECT
    Category,
    SUM(Sales) AS Total_Sales,
    SUM(Profit) AS Total_Profit
FROM sales
GROUP BY Category
ORDER BY Total_Sales DESC; to explore the files and dashboard.

Customer Segmentation
SELECT
    Customer_Name,
    SUM(Sales) AS Total_Sales,
    CASE
        WHEN SUM(Sales) >= 10000 THEN 'High Sales'
        WHEN SUM(Sales) >= 5000 THEN 'Medium Value'
        ELSE 'Low Value'
    END AS Customer_Segment
FROM sales
GROUP BY Customer_Name;

📗 Excel Analysis

Excel was used for exploratory analysis, calculations and dashboard development.

Excel techniques used
Data cleaning
Pivot Tables
Pivot Charts
KPI calculations
Sales analysis
Customer analysis
Product analysis
Regional analysis
Monthly sales trends
Payment mode analysis
Profitability analysis
Interactive slicers

📊 Power BI Dashboard

The Power BI report contains 3 interactive pages.

Page 1 — E-Commerce Sales Executive Dashboard

Provides a high-level overview of overall business performance.

KPIs
Total Sales
Total Profit
Total Orders
Total Customers
Average Order Value
Profit Margin
Visualizations
Sales by Category
Monthly Sales Trend
Sales by Region
Top 10 Customers
KPI Cards
Interactive Slicers
Page 2 — Product & Regional Profitability Analysis

This page focuses on product, category and regional profitability.

Product Performance
Rank	Product	Sales	Profit	Margin
1	Laptop	₹93.08 L	₹23.58 L	25.34%
2	Smartphone	₹29.06 L	₹6.95 L	23.92%
3	Study Table	₹14.89 L	₹3.75 L	25.15%
4	Office Chair	₹13.88 L	₹3.67 L	26.43%
5	Bookshelf	₹9.91 L	₹2.66 L	26.84%

Highest product profit margin: Smartwatch — 27.15%

Regional Performance
Region	Sales	Profit	Margin
West	₹61.04 L	₹14.47 L	23.71%
East	₹39.99 L	₹9.76 L	24.39%
North	₹55.85 L	₹14.38 L	25.75%
South	₹56.53 L	₹15.35 L	27.16%

Highest sales: West
Highest profit: South
Highest regional margin: South — 27.16%

Category Performance
Category	Sales	Profit	Margin
Electronics	₹1.44 Cr	₹36.23 L	25.15%
Furniture	₹38.68 L	₹10.07 L	26.04%
Fashion	₹15.96 L	₹3.95 L	24.72%
Home & Living	₹10.43 L	₹2.65 L	25.37%
Grocery	₹4.28 L	₹1.07 L	24.96%
Page 3 — Customer & Order Performance

This page focuses on customer contribution and order performance.

Analysis included
Order Status Distribution
Delivered Orders
Cancelled Orders
Returned Orders
Return Rate
Cancellation Rate
Top 10 Products
Top 10 Customers
Interactive Slicers
Order Status
Status	Orders	Percentage
Delivered	1,372	91.47%
Cancelled	85	5.67%
Returned	43	2.87%
💡 Key Business Insights
1. Electronics drives overall revenue

Electronics generated approximately ₹1.44 Cr in sales, contributing around 67.5% of total revenue.

2. Laptop is the top-performing product by revenue and profit

Laptop generated ₹93.08 Lakh in sales and ₹23.58 Lakh in profit, making it the highest-selling and highest-profit product.

3. West leads sales, while South leads profitability

West generated the highest sales at ₹61.04 Lakh.

However, South generated the highest profit at ₹15.35 Lakh and the highest regional profit margin of 27.16%.

This shows why regional performance should be evaluated using both revenue and profitability.

4. Furniture has the highest category margin

Furniture achieved a 26.04% profit margin, higher than Electronics despite having significantly lower sales.

5. Revenue leadership and margin leadership differ

Laptop generated the highest sales, while Smartwatch achieved the highest product margin of 27.15%.

This highlights the importance of analyzing both revenue and profitability.

6. UPI is the most-used payment method

UPI accounted for 531 orders and approximately 34.05% of total sales, making it the most-used payment method.

7. Most orders were successfully delivered

91.47% of orders were delivered, while the return rate was 2.87% and cancellation rate was 5.67%.

8. August was the strongest sales month

August generated approximately ₹25.88 Lakh in sales and ₹6.16 Lakh in profit.

🧮 Key DAX Measures
Total Sales
Total Sales =
SUM(Sales_Data[Sales])
Total Profit
Total Profit =
SUM(Sales_Data[Profit])
Total Orders
Total Orders =
DISTINCTCOUNT(Sales_Data[Order_ID])
Total Customers
Total Customers =
DISTINCTCOUNT(Sales_Data[Customer_ID])
Average Order Value
Average Order Value =
DIVIDE(
    [Total Sales],
    [Total Orders]
)
Profit Margin
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Sales]
)
Return Rate
Return Rate % =
DIVIDE(
    [Returned Orders],
    [Total Orders]
)
🏗️ Power BI Data Model

The report uses a star-schema data model.

                    Dim_Date
                       │
                       │
                       ▼
Dim_Product ─────► Sales_Data ◄───── Dim_Customer
                       ▲
                       │
                  Dim_Location
Fact Table
Sales_Data
Dimension Tables
Dim_Date
Dim_Product
Dim_Customer
Dim_Location

The model allows interactive filtering across products, customers, locations and dates.

📷 Dashboard Preview

📁 Project Files
E-Commerce_dashboard.pbix – Power BI dashboard
E-commerce Sales Dashboard.xlsx – Excel analysis and dashboard
ecommerce_sales_analysis_dataset.csv – Source dataset
E-commerce Sales Dashboard.png – Dashboard preview
README.md – Project documentation
🎯 Business Objective

The objective of this project was to transform raw e-commerce transaction data into an interactive analytics solution that helps understand:

Revenue and profit performance
Product profitability
Category performance
Regional performance
Customer contribution
Sales trends
Payment preferences
Returns and cancellations
🚀 Skills Demonstrated
Data Analysis
Exploratory Data Analysis
KPI Analysis
Customer Analysis
Product Analysis
Profitability Analysis
Business Insights
SQL
Aggregations
GROUP BY
CASE statements
CTEs
Subqueries
Window Functions
Ranking
Excel
Data Cleaning
Pivot Tables
Pivot Charts
KPI Dashboard
Slicers
Power BI
Data Modeling
Star Schema
Relationships
DAX
Interactive Dashboards
Data Visualization
👩‍💻 Author

Kavya Rami

Aspiring Data Analyst

Skills: Excel | SQL | Power BI | DAX | Python
