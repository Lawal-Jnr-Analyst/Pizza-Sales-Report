# 🍕 Pizza Sales Performance Analysis (End-to-End SQL & Power BI)


## 📊 Project Overview
This project provides a comprehensive analysis of a year's worth of pizza sales data. The goal was to uncover key performance indicators (KPIs) and trends to help a fictional pizza outlet optimize its menu, staffing, and marketing strategies.

I handled the entire pipeline: from data cleaning and KPI calculation using SQL to creating an interactive 2-page dashboard that tells a visual story.


## 🛠️ Tech Stack
- Database: SQL (MySQL/PostgreSQL) – Used for data cleaning and complex aggregations.
- Visualization: Power BI – Used for creating interactive charts and UI/UX design.
- Data Source: CSV containing 2015 transaction data.


## 💡 Key Business Insights
- Revenue Driver: The Thai Chicken Pizza is the top revenue generator ($43k+), indicating a strong market for premium options.
- Volume Leader: The Classic Deluxe Pizza leads in total quantity sold and total orders, making it the "anchor" of the menu.
- Operational Peak: Orders significantly peak on Friday and Saturday nights, particularly in July and May, suggesting a need for optimized staffing during these windows.
- Growth Opportunity: The Brie Carre Pizza sits at the bottom of all metrics (Revenue, Quantity, and Orders), signaling a need for either a recipe revamp or a tactical marketing pivot.


## SQL Portfolio (Code Samples)
I used SQL to ensure data integrity and calculate the metrics displayed in the dashboard.
1. Data Transformation (Standardizing Dates)
         UPDATE pizza_sales 
         SET order_date = STR_TO_DATE(order_date, '%m/%d/%Y');

2. Calculating Monthly Trends
         SELECT monthname(order_date) AS order_month, COUNT(DISTINCT order_id) AS total_orders
         FROM pizza_sales
         GROUP BY order_month
         ORDER BY MIN(MONTH(order_date));

3. Identifying the "Underperformers" (Bottom 5 by Revenue)
         SELECT pizza_name, ROUND(SUM(total_price), 2) AS Total_revenue
         FROM pizza_sales
         GROUP BY pizza_name
         ORDER BY Total_revenue ASC
         LIMIT 5;


## 🖥️ Preview
[Page 1: Executive Summary & Sales Trends](https://github.com/Lawal-Jnr-Analyst/Sunshine-Phone-Sales/blob/main/SUNSHINE%20PHONE%20SALES.jpg)
>click the image above to see a preview of the final dashboard.

[Page 2: Product Performance & Best/Worst Sellers](https://github.com/Lawal-Jnr-Analyst/Sunshine-Phone-Sales/blob/main/SUNSHINE%20PHONE%20SALES.jpg)
>click the image above to see a preview of the final dashboard.


#### 🧑‍💻Author: [Lawal-Jnr-Analyst](https://github.com/Lawal-Jnr-Analyst)
