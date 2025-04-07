# 📦 E-Commerce SQL Project

This project focuses on cleaning and preparing e-commerce transactional data using SQL (MySQL) for further analysis and insights generation.

---

## 📚 Table of Contents

1. [Project Structure](#-project-structure)  
2. [Data Cleaning Summary](#-data-cleaning-summary)  
3. [Concepts Covered](#-concepts-covered)  
4. [Tools & Technologies Used](#-tools--technologies-used)  
5. [Sample Query & Result](#-sample-query--result)  
6. [Conclusion](#-conclusion)  
7. [Author](#-author)

---

## 📁 Project Structure

The dataset includes the following five tables:

| Table Name       | Description                                      |
|------------------|--------------------------------------------------|
| `df_customers`   | Contains customer IDs and their location data    |
| `df_orders`      | Contains order and timestamp-related details     |
| `df_orderitems`  | Contains details of each item in an order        |
| `df_payments`    | Includes payment method and value information    |
| `df_products`    | Contains product details including categories     |

---

## 🧹 Data Cleaning Summary

The following cleaning tasks were performed using SQL to ensure the data is consistent and ready for analysis:

### ✅ Timestamp Conversion

```sql
-- Convert order purchase timestamp to proper DATETIME format
UPDATE df_orders 
SET order_purchase_timestamp = STR_TO_DATE(order_purchase_timestamp, '%Y-%m-%d %H:%i:%s');

ALTER TABLE df_orders 
MODIFY order_purchase_timestamp DATETIME;
