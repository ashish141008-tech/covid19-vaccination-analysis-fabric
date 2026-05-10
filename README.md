
# 🌍 COVID-19 Vaccination Analysis using Microsoft Fabric & Power BI

> End-to-end Data Analytics project focused on COVID-19 vaccination trends, global coverage, and vaccine distribution using Microsoft Fabric, SQL, and Power BI.

---

# 📌 Project Overview

This project analyzes global COVID-19 vaccination data to uncover trends, country-wise vaccination progress, and vaccine manufacturer distribution.

The complete workflow was built inside **Microsoft Fabric**, including:
- Lakehouse setup
- SQL-based data cleaning & analysis
- Power BI dashboard creation
- Interactive visual storytelling

---

# 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Microsoft Fabric | Data Engineering & Analytics |
| Lakehouse | Data Storage |
| SQL | Data Cleaning & Analysis |
| Power BI | Dashboard & Visualization |
| DAX | KPI Measures |

---

# 📂 Dataset Information

Two datasets were used in this project:

## 1️⃣ Vaccinations Dataset
Contains:
- Country
- Date
- Total Vaccinations
- Daily Vaccinations
- Fully Vaccinated People
- Vaccination Metrics

---

## 2️⃣ Manufacturer Dataset
Contains:
- Vaccine Name
- Date
- Total Vaccinations
- Manufacturer Distribution

---

# 🚀 Project Workflow

## 🔹 Step 1: Created Lakehouse in Microsoft Fabric
- Uploaded raw CSV files into Fabric Lakehouse
- Connected datasets with SQL endpoint

---

## 🔹 Step 2: Data Cleaning using SQL
Performed:
- NULL value handling
- Data type conversion
- Missing value treatment
- Aggregation logic
- Window function analysis

### SQL Concepts Used
- `CAST()`
- `COALESCE()`
- `ISNULL()`
- `LAG()`
- `GROUP BY`
- Window Functions

---

## 🔹 Step 3: Data Analysis using SQL

### Analysis Performed
- Global vaccination trends
- Top vaccinated countries
- Vaccine distribution analysis
- Daily vaccination growth
- Country-wise comparisons

---

## 🔹 Step 4: Dashboard Creation in Power BI
Built interactive visuals including:
- KPI Cards
- Bar Charts
- Line Charts
- Donut Charts
- Map Visuals
- Country Slicers

---

# 📊 Dashboard Features

## ✅ KPI Cards
- Total Countries
- Total Vaccinations
- Total Daily Vaccinations

---

## ✅ Visualizations
- 📈 Global Vaccination Trend
- 🌍 Vaccination Coverage Map
- 🏆 Top 5 Countries by Vaccination
- 💉 Global Vaccine Distribution
- 🎛️ Interactive Country Slicer

---

# ⚠️ Challenges Faced & Solutions

## 1️⃣ Fabric Permission Restrictions
### Problem
Could not create tables/views directly inside Fabric due to permission limitations.

### Solution
Used:
- CTEs
- SQL query transformations
- DAX Measures

instead of physical table creation.

---

## 2️⃣ Relationship Modeling Issue
### Problem
Initially created relationship between:
- `vaccinations`
- `manufacturer`

using `date`, which caused:
- many-to-many issues
- aggregation conflicts
- broken visuals

### Solution
Kept both tables independent because manufacturer dataset lacked country-level granularity.

---

## 3️⃣ Aggregation Issue
### Problem
Using:
```sql
SUM(total_vaccinations)
