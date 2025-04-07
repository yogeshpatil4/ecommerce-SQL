# 📦 E-Commerce SQL Project

This project focuses on cleaning and preparing e-commerce transactional data using SQL (MySQL) for further analysis and insights generation.

---

## 📚 Table of Contents

1. [Project Structure](#-project-structure)  
2. [Data Cleaning Summary](#-data-cleaning-summary)  
3. [Concepts Covered](#-concepts-covered)  
4. [Tools & Technologies Used](#-tools--technologies-used)  
5. [Conclusion](#-conclusion)  
6. [Author](#-author)

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

- Converted the `order_purchase_timestamp` and `order_approved_at` fields to `DATETIME` format for accurate time-based analysis.

### 🧾 Handling Missing Values

- Removed records from `df_orders` with blank approval timestamps.
- Deleted entries in `df_products` where `product_category_name` was missing.

### 📌 Duplicate Records

- Identified and removed duplicate entries in `df_products` using the `product_id` column, keeping only unique records.

---

## 📘 Concepts Covered

- Data Type Conversion (e.g., `STR_TO_DATE`, `DATETIME`)
- Handling Missing or Null Values
- Removing Duplicates using `ROW_NUMBER() OVER (PARTITION BY...)`
- Filtering Invalid Entries
- Data Normalization & Preparation for Analysis
- Use of CTEs (Common Table Expressions)

---

## 🛠 Tools & Technologies Used

- **MySQL** (for querying and cleaning the dataset)

---

## ✅ Conclusion

The data cleaning process laid a strong foundation for accurate and meaningful analysis. By addressing missing values, standardizing date formats, and removing duplicates, the dataset is now clean and reliable for performing advanced SQL queries, business insights extraction, and future integration into dashboards or BI tools.

---

## 📌 Author

**Yogesh Patil**  
Aspiring Data Analyst | MySQL Enthusiast

---

Feel free to clone this repo and explore the dataset further with your own SQL queries!
