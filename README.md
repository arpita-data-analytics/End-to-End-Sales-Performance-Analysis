# End-to-End Sales Analytics Capstone (MySQL & Power BI)

## 📌 Project Overview
This project delivers an end-to-end sales analytics solution built using **MySQL** and **Power BI**. Starting from raw transactional and lookup tables, I designed a normalized relational database schema, enforced data integrity constraints, wrote analytical SQL queries to uncover business KPIs, and built an interactive multi-page Power BI executive dashboard to visualize revenue trends, regional distribution, product performance, and customer segments.

---

## 🛠️ Tech Stack & Tools
* **Database & Querying:** MySQL, MySQL Workbench (DDL, DML, Joins, CTEs/Subqueries, Window Functions)
* **Business Intelligence & Visualization:** Power BI Desktop (Data Modeling, DAX Measures, Interactive Dashboards)
* **Version Control:** Git & GitHub

---

## 🗄️ Database Architecture & Data Modeling
The `sales_analytics` database is structured around a central fact table (`Sales Order`) connected to dimension and reference tables (`Customers`, `Products`, `Regions`, and `2017 Budgets`).

### Data Integrity & Schema Enforcement
Before performing analysis, I validated the dataset and enforced relational constraints:
* **Duplicate & Null Validation:** Checked primary key candidate columns across all tables (`Index`, `Customer Index`, `OrderNumber`, `Product Description Index`, `Product Name`) to ensure uniqueness and zero null values.
* **Primary Keys:** Defined single and composite primary keys (e.g., composite key on `OrderNumber` and `Product Description Index` in `Sales Order`).
* **Foreign Keys:** Established referential integrity linking `Sales Order` to `Customers`, `Products`, and `Regions`.
* **Date Standardization:** Converted raw string dates (`%d-%m-%Y`) into proper SQL date formats using `STR_TO_DATE()` for accurate time-series and Year-over-Year (YoY) analysis.

*(Optional: Add a screenshot of your MySQL Workbench EER Diagram below)*
![Database Schema](images/eer_diagram.png)

---

## 🔍 Key SQL Analyses Performed
The `SQL CAPSTONE PROJECT.sql` script is organized into structured business modules:
1. **Executive KPIs:** Total Orders, Total Units Sold, and Total Revenue (`Line Total`).
2. **Sales Channel Performance:** Revenue, order volume, Average Order Value (AOV), and percentage contribution across channels using window functions (`SUM() OVER ()`).
3. **Geographic & Regional Analysis:** Country-level sales breakdown, top 10 revenue-generating cities, and their cumulative share of total company sales.
4. **Product Portfolio Insights:** Product-wise revenue, units sold, sales contribution percentages, and Average Selling Price (ASP).
5. **Customer Behavior & Segmentation:**
   * Top 10 customers by revenue and customer-level AOV.
   * Repeat vs. one-time customer retention breakdown.
   * High-frequency buyers (`>= 50` orders) ranked by AOV.
   * Customer sales ranking using `RANK() OVER ()`.
   * Tiered customer value segmentation (**High Value** `>= 3,000`, **Medium Value** `>= 1,500`, **Low Value** `< 1,500`) using `CASE` statements.
6. **Time-Series & Growth Trends:** Monthly and yearly revenue aggregations, plus Year-over-Year (YoY) growth percentage calculated via the `LAG()` window function.

---

## 📊 Power BI Dashboard
The Power BI report (`POWER BI SQL CAPSTONE.pbix`) connects to the modeled dataset to provide interactive filtering by Year, Channel, Country, and Customer Segment.

*(Add screenshots of your Power BI dashboard pages here)*
![Dashboard Overview](images/dashboard_overview.png)

---

## 📂 Repository Structure
```text
Sales-Analytics-SQL-PowerBI/
│
├── SQL CAPSTONE PROJECT.sql        # Complete MySQL script (schema, constraints, & analytical queries)
├── POWER BI SQL CAPSTONE.pbix      # Interactive Power BI dashboard file
├── images/                         # Screenshots of Power BI dashboard pages & EER diagram
└── README.md                       # Project documentation# End-to-End-Sales-Performance-Analysis
"End-to-end sales analytics capstone project featuring relational database modeling, SQL data validation &amp; advanced querying, and an interactive Power BI executive dashboard."
