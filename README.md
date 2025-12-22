# 🏗️ SQL-Data-Warehouse-Project

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

## 📚 Key Learnings

Through this project, I strengthened my understanding of:

- End-to-end data warehousing workflows  
- Medallion Architecture design and implementation  
- Writing clean, maintainable, and analytical SQL  
- Data modeling for analytics (star schema)  
- Bridging data engineering and data analytics concepts

---

## 👋 About Me

Hi, I'm **Marc Pérez Aladrén**, a data-driven professional with a strong interest in **data analytics, data engineering, and digital transformation** 🚀  

I hold a **Bachelor’s degree in Business Administration** from the University of Barcelona and a **Master’s in Global Digital Marketing**, and I recently worked at **SAP** as a **Digital Transformation Associate**, where I focused on data intelligence, account segmentation, CRM governance, and go-to-market analytics.

This project represents my hands-on approach to learning by building **end-to-end data solutions**, bridging business context with technical execution. I’m particularly interested in roles where data, process optimization, and strategic decision-making intersect.

[![LinkedIn](https://img.shields.io/badge/LINKEDIN-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/marc-p%C3%A9rez-aladr%C3%A9n/)
