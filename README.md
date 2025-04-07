# 🛒 E-commerce SQL Analysis Project
## 📚 Table of Contents
- [📁 Datasets Used](#-datasets-used)
- [🧹 Data Cleaning Performed](#-data-cleaning-performed)
- [🔍 Key Business Questions Answered](#-key-business-questions-answered)
- [🧰 Tools Used](#-tools-used)
- [🛠️ Skills Covered](#-skills-covered)
- [✅ Conclusion](#-conclusion)

## 📦 Dataset Used

This project uses a collection of CSV files representing a simplified e-commerce platform. The datasets are:

- **df_Customers.csv**: Contains customer details such as customer ID, city, and state.
- **df_Orders.csv**: Includes order-specific information such as order ID, order status, purchase and approval timestamps.
- **df_OrderItems.csv**: Contains individual items within orders including product ID, price, and quantity.
- **df_Products.csv**: Lists product details including product ID, category, and product name.
- **df_Payments.csv**: Holds information about payment methods, values, and number of installments.

## 🧹 Data Cleaning

To ensure accurate analysis, several data cleaning steps were performed using SQL:

- **Converted datetime columns** (`order_purchase_timestamp` and `order_approved_at`) to proper DATETIME format using `STR_TO_DATE`.
```sql
UPDATE df_orders 
SET order_purchase_timestamp = 
STR_TO_DATE(order_purchase_timestamp,'%Y-%m-%d %H:%i:%s');

ALTER TABLE df_orders MODIFY order_purchase_timestamp DATETIME;


DELETE  FROM ecommerce.df_orders
WHERE order_approved_at="";

UPDATE df_orders SET order_approved_at=
STR_TO_DATE(order_approved_at,'%Y-%m-%d %H:%i:%s');

ALTER TABLE df_orders MODIFY order_approved_at DATETIME;

  ```

- **Removed rows with missing approval timestamps** from the `df_orders` table.
- **Deleted rows with empty product category names** from the `df_products` table.
- **Removed duplicate product entries** by using a CTE and `ROW_NUMBER()` to identify and keep only the first occurrence of each `product_id`.

These steps ensured consistent and clean data before starting the analysis.


## 🔍 Key Business Questions Answered
### Customer Insights
- Top 10 customers by total spending
- Customer distribution by state/city
- Average number of orders per customer
- High-value customers with the highest total payments
- More to be defined...

### Sales Performance
- Monthly sales trend analysis
- Total revenue, total orders, and total quantity sold
- Top-selling products by revenue and quantity
- Revenue distribution by city/state

### Product Analysis
- Category-wise revenue breakdown
- Best-selling and underperforming products
- Seasonal sales patterns of products

### Order Behavior
- Order count and value by payment type
- Single-item vs. multi-item orders
- Cart size trends over time

### Revenue & Customer Growth
- Monthly revenue trends
- New customer acquisition rate

### Customer Segmentation & Behavior
- Customer segmentation based on AOV quartiles
- Revenue contribution by top 10% of customers
- Cohort analysis of first-time buyers

### Anomaly Detection
- Identifying anomalies in payment values

## 🧰 Tools Used
- **Power BI** (Data Visualization & Dashboarding)
- **SQL** (Data Analysis & Querying)
- **Excel** (Initial Data Exploration & Cleaning)

## 🛠️ Skills Covered
- Data Cleaning & Preparation
- Data Modeling
- SQL for Business Insights
- Power BI Visualization
- DAX (Data Analysis Expressions)
- Business Intelligence Reporting

## ✅ Conclusion
This project provides a comprehensive analysis of e-commerce sales and customer behavior using Power BI and SQL. The insights gained help in strategic decision-making by identifying trends, customer segments, and key revenue drivers. The dashboards effectively present business-critical KPIs, improving overall business intelligence.
