# 🔎 SQL Exploratory Data Analysis (EDA) — Warehouse Dataset

A structured **Exploratory Data Analysis (EDA)** performed entirely in **T-SQL** on the same DataWarehouseAnalytics gold schema. This project systematically explores the database structure, dimensions, measures, and relationships before any modeling or reporting is done.

---

## 📌 Project Overview

| Detail | Info |
|--------|------|
| **Tool** | SQL Server (T-SQL) |
| **Database** | DataWarehouseAnalytics |
| **Schema** | Gold Layer (dim_customers, dim_products, fact_sales) |
| **Total Lines** | 190+ lines of SQL |
| **Data Range** | Dec 2010 – Jan 2014 (4 years of sales data) |

---

## 🗂️ EDA Structure

The analysis is organized into 4 phases:

```
1. Database Exploration    → Schema, tables, columns
2. Dimensions Exploration  → Countries, categories, products, date range, customer ages
3. Measure Exploration     → Aggregates: customers, revenue, products, gender, geography
4. Ranking Analysis        → Top/bottom products, top customers, sold items by country
```

---

## 🔍 Key Findings from EDA

| Question | Finding |
|----------|---------|
| 📅 Sales date range | Dec 29, 2010 → Jan 28, 2014 **(4 years)** |
| 🌍 Top country by customers | **United States — 7,482 customers** |
| 🇦🇺 2nd country | Australia — 3,591 customers |
| 👨 Male customers | **9,341** |
| 👩 Female customers | **9,128** |
| 🏆 Top product by revenue | Mountain-200 Black-46 — **$1,373,454** |
| 📦 Most components category | Components — **127 products** |
| 🚴 Highest avg cost category | Bikes — avg cost **$949** |
| 🌎 Most sold items country | United States — **20,481 items** |
| 🥇 Top customer by revenue | Kaitlyn Henderson — **$13,294** |
| ❌ Worst 5 products | Racing Socks-L, Racing Socks-M, Patch Kit/8, Bike Wash, Touring Tire Tube |

---

## ⚙️ What This Project Covers

### Phase 1: Database Exploration
- Queried `INFORMATION_SCHEMA.TABLES` to list all objects
- Queried `INFORMATION_SCHEMA.COLUMNS` to explore column structure of `dim_customers`

### Phase 2: Dimensions Exploration
- Distinct countries customers come from
- Distinct product categories, subcategories, and product names
- First order date, last order date, and total years of sales data
- Youngest and oldest customer birthdays

### Phase 3: Measure Exploration
- Total customers by country (ranked DESC)
- Total customers by gender
- Total products by category
- Average product cost by category
- Total revenue by category
- Total revenue by customer (all 18,484 customers)
- Distribution of sold items across all countries

### Phase 4: Ranking Analysis
- Products ranked by revenue using `ROW_NUMBER() OVER(ORDER BY SUM(sales_amount) DESC)`
- Top 5 worst-performing products by revenue
- Top 10 customers by total revenue
- 3 customers with the fewest orders placed

---

## 🛠️ SQL Concepts Used

- `INFORMATION_SCHEMA` queries for metadata exploration
- `SELECT DISTINCT` for dimension profiling
- `MIN()` / `MAX()` / `DATEDIFF()` for date range analysis
- `COUNT(DISTINCT)` for unique entity counts
- `SUM()` / `AVG()` for measure aggregation
- `GROUP BY` + `ORDER BY DESC` for ranking
- `ROW_NUMBER() OVER()` for product ranking
- `INNER JOIN` across fact and dimension tables
- `SELECT TOP N` for best/worst performers

---

## 📁 Files

```
eda-warehouse-analytics/
│
├── eda_queries.sql      ← All EDA queries (190+ lines)
└── README.md
```

---

## 🚀 How to Run

1. Open **SQL Server Management Studio (SSMS)**
2. Make sure `DataWarehouseAnalytics` database is set up with gold schema
3. Run queries section by section — each block is self-contained
4. Results panel shows output for each exploration query

> **Note:** This EDA project is designed to run **before** the main analytics project — it helps understand the data before building reports.

---

## 📊 Sample Results

**Customers by Country:**
| Country | Total Customers |
|---------|----------------|
| United States | 7,482 |
| Australia | 3,591 |
| United Kingdom | 1,913 |
| France | 1,810 |
| Germany | 1,780 |
| Canada | 1,571 |

**Products by Category:**
| Category | Total Products |
|----------|---------------|
| Components | 127 |
| Bikes | 97 |
| Clothing | 35 |
| Accessories | 29 |

**Top 5 Worst Products by Revenue:**
| Product | Revenue |
|---------|---------|
| Racing Socks- L | $2,430 |
| Racing Socks- M | $2,682 |
| Patch Kit/8 Patches | $6,382 |
| Bike Wash - Dissolver | $7,272 |
| Touring Tire Tube | $7,440 |

---

## 🔗 Related Project

This EDA was performed on the same dataset as the main analytics project:
👉 [SQL Warehouse Analytics](https://github.com/DataWithBaraa/sql-data-analytics-project)

---

## 👤 Author

**Anuraag Kaushal**
[GitHub Profile](https://github.com/DataWithBaraa) | [LinkedIn](https://www.linkedin.com/in/)
