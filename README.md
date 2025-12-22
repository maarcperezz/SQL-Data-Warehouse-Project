# 🏗️ SQL-Data-Warehouse--And-Analytics-Project

Welcome to the **Data Warehouse and Analytics Project** repository 📊  
This project showcases the end-to-end design and implementation of a modern **Data Warehouse**, from raw data ingestion to business-ready analytics. It is built as a **portfolio project** to demonstrate practical SQL, data modeling, and analytical skills following industry best practices.

The project is inspired by the **DataWithBaraa SQL Data Warehouse Project**, adapted and extended as part of my personal learning journey into data-focused roles 🚀

---

## 📌 Project Requirements

This project aims to simulate a real-world data warehousing scenario, focusing on clarity, data quality, and analytical usability.

---

## 🛠️ Building the Data Warehouse (Data Engineering)

### 🎯 Objective
Design and implement a modern **Data Warehouse** using SQL, consolidating sales data from multiple source systems to enable reliable analytics and informed decision-making.

### 📋 Scope & Key Requirements

- **📂 Data Sources**: Import data from two source systems (**ERP** and **CRM**) provided as CSV files  
- **🏗️ Data Architecture**: Implement a **Medallion Architecture** (Bronze, Silver, Gold layers)  
- **🧹 Data Quality**: Clean, standardize, and validate data before it is exposed for analytics  
- **🔗 Integration**: Merge multiple sources into a single, analytics-friendly data model  
- **📐 Modeling**: Create **fact and dimension tables** using a star schema approach  
- **📦 Scope**: Focus on the latest available dataset (no historization required)  
- **📝 Documentation**: Provide clear documentation to support both business users and analytics teams  

---

## 🏛️ Data Architecture Overview

The Data Warehouse follows the **Bronze–Silver–Gold (Medallion) Architecture**, ensuring separation of concerns and data quality at each stage.

<img width="1426" height="937" alt="Imagen1" src="https://github.com/user-attachments/assets/8a84ab0c-66d3-40a5-b207-1aa98b478ccb" />


### 🥉 Bronze Layer — Raw Data
- Raw ingestion of CSV files into database tables  
- Minimal transformations to preserve source data integrity  
- Initial handling of schema alignment and basic validation  

### 🥈 Silver Layer — Clean & Standardized Data
- Data cleansing and normalization  
- Removal of duplicates using **CTEs and window functions**  
- Handling null values with **CASE statements** and **COALESCE**  
- Standardization of categorical fields  
- Joining datasets from multiple sources  

### 🥇 Gold Layer — Business-Ready Data
- No physical data loading (views only)  
- Star schema with fact and dimension tables  
- Optimized for reporting, BI tools, and ad-hoc analysis  
- Provides clean, well-structured datasets for stakeholders

---

## 🧰 Tools & Technologies

- **🧠 SQL** (data transformation and analytics)  
- **🗄️ Relational Database** (SQL Server / PostgreSQL / MySQL – adaptable)  
- **📄 CSV files** as data sources  
- **🖊️ Draw.io** for data modeling and architecture diagrams  
- **🔗 GitHub** for version control and documentation
- **📝 Notion** for project notes and documentation ([Data Warehouse Project – Notion workspace](https://pushy-minute-9aa.notion.site/Data-Warehouse-Project-2cba0a1f8cc680c08acbd876ad55fe2c?source=copy_link))

---

## 📊 Analytics & Insights

The analytics layer builds on top of the **Gold layer**, leveraging business-ready data to generate insights using SQL.  
This section is divided into **Exploratory Data Analysis (EDA)** and **Analytical Reporting**, mirroring real-world analytical workflows.

---

## 🔎 Exploratory Data Analysis (EDA)

The goal of the EDA phase is to understand the structure, scope, and behavior of the data before building analytical reports.

### 🧭 1. Database Exploration (Structure & Metadata)

**Objective:** Quickly understand what exists in the database and how it is organized.

Key activities:
- Explore tables and views using metadata (`INFORMATION_SCHEMA.TABLES`)
- Inspect column-level metadata (`INFORMATION_SCHEMA.COLUMNS`)
- Filter metadata for specific tables (e.g. `dim_customers`, `dim_products`)

**Outcome:**  
A clear overview of database structure, naming conventions, and data availability.

---

### 🧩 2. Dimension Exploration (Cardinality & Granularity)

**Objective:** Understand the categorical dimensions and their level of detail.

Key activities:
- Retrieve unique values using `SELECT DISTINCT`
- Analyze dimensions such as:
  - Customer country 🌍
  - Product category & subcategory 🏷️
- Explore hierarchies:
  - Category → Subcategory → Product

**Outcome:**  
Clear understanding of **low vs high cardinality** dimensions and their impact on aggregation levels.

---

### 📅 3. Date Exploration (Time Range & Boundaries)

**Objective:** Identify the time span and boundaries of the dataset.

Key activities:
- Identify earliest and latest dates using `MIN()` and `MAX()`
- Calculate time spans with `DATEDIFF()`
- Apply analysis to:
  - Order dates
  - Customer birthdates
- Derive customer age from birthdate

**Outcome:**  
Understanding of historical coverage, customer age distribution, and data freshness.

---

### 💰 4. Measure Exploration (Core Business KPIs)

**Objective:** Compute the main business metrics using SQL aggregates.

Key metrics calculated:
- Total revenue (`SUM(sales_amount)`)
- Total quantity sold
- Average selling price
- Number of orders (`COUNT` vs `COUNT(DISTINCT)`)
- Total customers and products

A consolidated **KPI summary query** was built using `UNION ALL`, combining:
- `measure_name`
- `measure_value`

**Outcome:**  
A high-level numerical overview of business performance.

---

### ⚖️ 5. Magnitude Analysis (Measure by Dimension)

**Objective:** Compare metrics across different dimensions.

Examples:
- Customers by country 🌍
- Customers by gender 👥
- Products by category 🏷️
- Revenue by category 💸
- Revenue by customer 🧑‍💼
- Quantity sold by country 🌐

**Outcome:**  
Identification of patterns, dominant segments, and distribution of business value.

---

### 🏆 6. Ranking Analysis (Top & Bottom Performers)

**Objective:** Identify best and worst performers using ranking logic.

Techniques used:
- `TOP (N)` with `ORDER BY`
- Window functions:
  - `ROW_NUMBER()`
  - `RANK()`
  - `DENSE_RANK()`

Examples:
- Top 5 products by revenue 🥇
- Bottom 5 products by revenue ❄️
- Top customers by revenue 💎
- Lowest-performing customers by order volume 📉

**Outcome:**  
Clear visibility into performance extremes and business priorities.

---

## 📈 Analytical Reports (Gold Layer Views)

To operationalize analytics, insights were materialized as **SQL views** in the Gold layer.

---

### 👥 Customer Report

A comprehensive customer-level report providing:
- Customer identifiers and demographics
- Customer lifespan and recency
- Total orders, revenue, and quantities
- Average order revenue
- Average monthly revenue
- Customer segmentation based on revenue performance

This report enables deep customer comparison and value-based segmentation.

---

### 📦 Product Report

A dedicated product-level analytical view designed to deliver actionable product insights.

Key features:
- Product details (name, category, subcategory)
- Cost and pricing information
- Product lifespan and last sale date
- Total orders, customers, quantity sold, and revenue
- Average selling price
- Average order revenue
- Average monthly revenue

#### 🔖 Product Segmentation
Products are classified into performance tiers based on total revenue:
- **High performers**
- **Mid-range performers**
- **Low performers**

**Outcome:**  
A complete, business-ready product performance report that supports comparison, optimization, and strategic decision-making.

---

## 📚 Key Learnings

Through this project, I consolidated an **end-to-end understanding of how data warehouses support analytical decision-making**, from raw ingestion to business-ready insights.

**Key takeaways include:**

- Designing and implementing a modern **Data Warehouse** using a **Medallion Architecture (Bronze, Silver, Gold)** to progressively improve data quality and usability  
- Applying **SQL as an ETL tool**, handling data ingestion, cleansing, deduplication, standardization, and transformation across multiple layers  
- Building **analytical data models** using a **star schema**, with fact and dimension tables optimized for reporting and BI consumption  
- Performing **structured Exploratory Data Analysis (EDA)** in SQL, including database inspection, dimension analysis, date exploration, and KPI validation  
- Developing **business-oriented analytics**, such as magnitude analysis, ranking analysis, and segmentation, to identify performance patterns and outliers  
- Creating **reusable analytical reports as SQL views**, enabling consistent customer and product insights directly from the Gold layer  
- Bridging **data engineering and analytics**, understanding how upstream modeling and data quality decisions directly impact downstream insights and reporting  

This project strengthened both my **technical SQL skills** and my ability to **think analytically about data as a business asset**, closely mirroring real-world data team workflows.

---

## 👋 About Me

Hi, I'm **Marc Pérez Aladrén**, a data-driven professional with a strong interest in **data analytics, data engineering, and digital transformation**.

I hold a **Bachelor’s degree in Business Administration** from the University of Barcelona and a **Master’s in Global Digital Marketing**, and I recently worked at **SAP** as a **Digital Transformation Associate**, where I focused on data intelligence, account segmentation, CRM governance, and go-to-market analytics.

This project represents my hands-on approach to learning by building **end-to-end data solutions**, bridging business context with technical execution. I’m particularly interested in roles where data, process optimization, and strategic decision-making intersect.

[![LinkedIn](https://img.shields.io/badge/LINKEDIN-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/marc-p%C3%A9rez-aladr%C3%A9n/)
