# Retail Sales Cloud Data Pipeline

## Project Overview
Retail companies often manage sales data in messy Excel files, making it difficult to generate consistent business insights.  
This project demonstrates how to build a **cloud-based data pipeline** that ingests Excel files, transforms them with Python, loads them into **Azure SQL Database**, and delivers interactive dashboards in **Power BI**.

---

## Business Problem
- Sales data stored in spreadsheets is error-prone and not scalable.  
- Business managers need **real-time KPIs** such as revenue, profit, and customer loyalty.  
- Manual reporting is slow and inconsistent.  

This project shows how to **automate reporting** with a cloud-first data engineering pipeline.

---

## Data Source
- [Superstore Sales Dataset (Kaggle)](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)  
  - Orders, products, customers, categories, regions, sales, and profit.  
  - Used to simulate real retail operations.  

---

## 🛠 Tools & Technologies
- **Python (pandas, SQLAlchemy)** – ETL: Extract & clean Excel, transform fields, load into SQL.  
- **Azure SQL Database** – Cloud storage of structured tables (Orders, Customers, Products).  
- **SQL (T-SQL)** – KPI queries (top products, revenue trends, customer retention).  
- **Power BI** – Dashboard for interactive reporting.  

---

## Project Workflow
1. **Extract (Excel → Python)**  
   - Loaded raw Excel sales file.  
   - Standardized column names, cleaned missing values.  

2. **Transform (Python)**  
   - Converted dates to datetime format.  
   - Derived new fields: Order Year, Margin % (Profit ÷ Sales).  

3. **Load (Python → Azure SQL)**  
   - Created schema with staging + fact/dim tables.  
   - Loaded transformed data into cloud SQL tables.  

4. **Query (SQL Server)**  
   - KPI queries: revenue by category, top 10 products, repeat customers, profit margin.  

5. **Visualize (Power BI)**  
   - KPI cards: Total Sales, Profit, Orders, Customers.  
   - Sales by Category & Region.  
   - Customer retention trend.  

---

## Key Insights
- Identified top-performing product categories driving most revenue.  
- Detected low-profit products despite high sales volume.  
- Regional analysis revealed markets with untapped potential.  
- Cohort analysis showed strong repeat purchases in certain customer segments.  

---

## Business Impact
This project demonstrates how a **data analyst with data engineering skills** can:  
- Automate Excel-to-dashboard reporting.  
- Provide managers with **scalable, cloud-based insights**.  
- Support data-driven decisions in sales strategy and customer targeting.  

---

## Deliverables
- Python ETL scripts (`extract`, `transform`, `load`).  
- SQL schema + KPI queries.  
- Power BI dashboard (screenshots + `.pbix` file).  
- README documenting the pipeline & business impact.  

