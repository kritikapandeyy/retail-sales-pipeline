# Retail Sales E-Commerce Data Pipeline

## Project Overview
Retail and e-commerce companies often receive large volumes of raw CSV files that are messy, unstructured, and hard to analyze directly.
This project demonstrates how to build a cloud-first data pipeline using the Olist Brazilian E-Commerce Dataset:
- Python (pandas, SQLAlchemy): Extract & clean CSVs, transform fields.
- Azure SQL Database: Cloud storage with staging and star schema tables.
- SQL (T-SQL): Create schema, run KPI queries, manage incremental loads.
- Power BI: Build interactive dashboards for sales, deliveries, customer retention, and payments.

---

## Business Problem
- Sales data stored in spreadsheets is error-prone and not scalable.  
- Data arrives in multiple CSVs (orders, items, customers, sellers, payments, reviews, geolocation).
- Without structure, KPIs are inconsistent and hard to compute (late deliveries, repeat customers, etc.).
- Manual Excel reporting is slow and not scalable. 
- This project shows how to **automate reporting** with a cloud-first data engineering pipeline.

---

## Data Source
[Brazilian E-Commerce Public Dataset (Kaggle)]([https://www.kaggle.com/datasets/vivek468/superstore-dataset-final](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce/data))  
  Contains ~100k orders across 2016–2018 with multiple linked tables as orders, order_items, products, customers, sellers, order_payments, order_reviews, product_category_name_translation, geolocation and more.

---

## Tools & Technologies
- **Python**: pandas, SQLAlchemy, pyodbc, dotenv → ETL (extract, transform, load).
- **Azure SQL Database**: cloud storage & relational modeling.
- **SQL (T-SQL)**: star schema design, KPI queries, incremental processing.
- **Power BI**: dashboards, DAX measures, cohort and retention analysis.

---

## Project Workflow

#### 1. **Extract (CSV → Python)**
- Load raw CSVs from the Olist dataset.
- Standardize column names, parse dates, and validate data types.

#### 2. **Transform (Python)**
- Translate product category names (Portuguese → English).
- Derive new fields:
  - Delivery delay days
  - On-time vs. late delivery flag
  - Margin % (profitability proxy)
- Add audit columns (e.g., load timestamp, source file name).

#### 3. **Load (Python → Azure SQL)**
- Stage each CSV into `stg.*` tables.
- Build **data warehouse schema** with fact + dimension tables:
  - **factSales** (from `orders` × `order_items`)
  - **factPayments**
  - **factReviews**
  - **dimCustomer**
  - **dimSeller**
  - **dimProduct**
  - **dimDate**
  - **dimGeography**

#### 4. **Query (SQL)**
- Write KPI queries such as:
  - Revenue and order trends by month
  - On-time delivery percentage
  - Repeat customer counts
  - Payment method shares
  - Average review scores

#### 5. **Visualize (Power BI)**
- Build dashboards with:
  - KPI cards: Sales, Orders, Freight %, Delivery Performance
  - Bar/line charts: Sales by Category, Region, Month
  - Cohort analysis: Customer retention over time
  - Donut chart: Payment method split
  - Drilldowns: Product → Category → Subcategory, Customer State → City

## Deliverables
- Python ETL scripts (`extract`, `transform`, `load`).  
- SQL schema + KPI queries.  
- Power BI dashboard (screenshots + `.pbix` file).  
