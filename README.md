# E-Commerce-Sales-Analysis-SQL-Power-BI-

### Overview
This project analyzes an e-commerce dataset to uncover key business insights related to sales performance, customer behavior, and product trends. The goal is to transform raw transactional data into actionable insights that can support data-driven decision-making.

### Business Problem
E-commerce businesses generate large volumes of sales data, but often struggle to extract meaningful insights. This project aims to answer key business questions such as:
- Which products and categories generate the most revenue?
- How do sales trends change over time?
- Which regions or customer segments perform best?
- How do discounts impact profitability?

### Dataset
The dataset contains transactional e-commerce data, including:
- Order details (Order ID, date)
- Product information (Category, sub category)
- Sales and Profit metrics
- Customer and regional data

### SQL Analysis
SQL was used for data cleaning, transformation, and analysis.
Key operations performed:
- Data aggregation (Total Revenue)
- Joins across two tables
- Grouping category and time
- Trend analysis using time-based queries

Example insights derived using SQL:
- Top performing product by revenue
- Yearly sales trends

### Tools and Technologies
- SQL (SQLite)
- Power BI
- DB Browser for SQLite

### Exploratory Data Analysis (EDA)
- The dataset spans across multiple dates based on order timestamps
- No major missing values were identified in key fields
- The data was structured into relational tables and joined using order_id

### Key Analysis
#### Total Revenue
SELECT SUM(price) AS total_revenue
FROM order_items;

#### Revenue Over Time
SELECT DATE(o.order_purchase_timestamp) AS order_date, SUM(oi.price) AS revenue
FROM orders o
JOIN order_items oi 
ON o.order_id = oi_order_id
GROUP BY order_date
ORDER BY order_date;

#### Top Products by Revenue
SELECT product_id, SUM(price) AS revenue
FROM order_items
GROUP BY product_id
ORDER BY product_id
LIMIT 10;

#### Sales Volume Analysis
SELECT DATE(o.order_purchase_timestamp) AS order_date, COUNT(*) AS items_sold
FROM orders o
JOIN order_items oi
ON o.order_id = oi.order_id
GROUP BY order date;

### Dashboard Preview
The dashboard provides an overview of revenue trends, product performance, and sales behavior patterns

#### Revenue Over Time
![Revenue](images/Revenue.jpeg)

#### Top Products
![Top Products](images/top-products.jpeg)

#### Sales Pattern
![Sales](images/Sales.jpeg)

### Key Insights
- Total revenue generated was approximately 13.6 million
- A small number of products contribute significantly to total revenue
- Revenue is primarily driven by sales volume, not price variation
- Sales are higher during weekdays compared to weekends

### Business Recommendations
- Focus on increasing sales volume to drive revenue growth
- Promote top-performing products to maximize revenue
- Introduce targeted promotions during weekends to boost sales

### Conclusion
This project demonstrates how raw e-commerce data can be transformed into meaningful insights using SQL and Power BI. It highlights the importance of data-driven decision-making in identifying trends, optimizing performance, and improving business strategy.
