# E-Commerce-Sales-Analysis-SQL-Power-BI-

### Overview
This project analyzes e-commerce sales data to uncover key trends in revenue, product performance, and customer purchasing behavior. The analysis was conducted using SQL and visualized using Power BI. 

### Objectives
- Analyze total revenue and sales performance
- Identify top-performing products
- Understand revenue trends over time
- Compare revenue vs sales volume
- Analyze weekday vs weekday sales patterns

### Tools and Technologies
- SQL (SQLite)
- Power BI
- DB Browser for SQLite

### Dataset
The dataset consists of two tables:
- Orders: Contains order-level information such as order ID and purchase timestamp
- Order Items: Contains product-level details such as product ID and price
These tables are linked using order_id

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
This project demonstrates the use of SQL for data analysis and Power BI for data visualization to generate actionable business insights from raw e-commerce data. 
