# 📈 AdventureWorks Sales & Returns Dashboard (Excel)

An interactive Excel dashboard analyzing sales performance and product returns for AdventureWorks Bike Shop — built with Power Query, Power Pivot, PivotTables, and PivotCharts.

![Sales Performance Dashboard Preview](./screenshot-sales-dashboard.png)

## 📊 Overview

This workbook turns the AdventureWorks sales, product, customer, and territory data into a fully interactive Excel dashboard for tracking business performance:

- What's total revenue, profit, profit margin, active customers, and order volume?
- Which categories and products drive the most orders, revenue, and profit?
- How does revenue break down by country and change over time?
- Who are the top customers by sales?
- Which products/countries/subcategories have the highest return rates?

## 🗂️ Data Model

Data is loaded via **Power Query** and modeled in **Power Pivot** (Excel's Data Model) as a star schema — the same structure used across the AdventureWorks analytics project:

- `Calendar Lookup` — date table for time intelligence
- `Categories Lookup` / Subcategory data — product hierarchy
- `Customer Lookup` — customer names and demographics
- `Territory Lookup` — country / continent
- A central Sales fact table with orders, revenue, profit, and returns

## 📑 Workbook Structure

| Sheet | Purpose |
|---|---|
| `Sheet1` | Raw/staging data area |
| `pivot` | Backend PivotTables powering all dashboard charts (hidden helper sheet) |
| ` sales Dashboard` | Main interactive Sales Performance dashboard |
| `Return Dashboard` | Dedicated dashboard for return analysis |

## 🧮 Key PivotTables Behind the Dashboard

| PivotTable | Feeds |
|---|---|
| Kpis | Revenue, Profit, Profit Margin, Active Customers, Orders KPI cards |
| order by category | "Order by category" bar chart |
| Category by sale | "Revenue by category" pie chart |
| Category (profit) | "Profit by category" donut chart |
| Top 10 product by revenue | "Top 10 Product by Sales" bar chart |
| sales by customer | "Top 10 Customer by sales" bar chart |
| sales by year | "Revenue by year (trend)" line chart |
| revenue by country | "Revenue by country" map chart |
| Return quantity by country / by category / by Date | Return Dashboard visuals |
| Subcategory / sub category return / Territory / Return product | Supporting drill-down tables |

## 🛠️ Steps I Used to Build This Project

1. **Loaded the AdventureWorks source tables** (Calendar, Categories, Customers, Territory, Sales) into Excel using **Power Query**, cleaning and shaping each query before loading.
2. **Loaded the queries into the Excel Data Model (Power Pivot)** rather than as plain worksheet tables, so relationships could be built between fact and lookup tables.
3. **Built relationships** between the sales fact table and the `Calendar Lookup`, `Customer Lookup`, `Categories Lookup`, and `Territory Lookup` dimension tables — mirroring a star schema.
4. **Created a parameter query** (`Parameter1`) to support dynamic/what-if elements in the model.
5. **Built PivotTables** off the Data Model for every KPI and breakdown needed (KPIs, category/subcategory performance, top products, top customers, revenue by year, revenue by country, and return metrics by country/category/date/product).
6. **Placed all PivotTables on a hidden "pivot" backend sheet** to keep the calculation layer separate from the presentation layer.
7. **Built PivotCharts** from each PivotTable (bar charts, pie/donut charts, line chart, map chart) and formatted them to match a consistent AdventureWorks blue/white color scheme.
8. **Designed the "Sales Dashboard" sheet** — arranged KPI cards, category/product/customer charts, the revenue-by-country map, and the revenue trend line into a single-screen executive dashboard, with the AdventureWorks logo and undo/redo-style navigation icons.
9. **Built a separate "Return Dashboard" sheet** focused on return quantity by country, category, date, and product for deeper returns analysis.
10. **Added slicers** (Year, Category, Country, Subcategory, Month) connected across the relevant PivotTables so all dashboard visuals filter together interactively.
11. **Tested and validated** the KPI numbers and chart interactivity, then hid gridlines/helper sheets and locked down the layout for a clean, presentation-ready dashboard.

## 🧰 Tools & Skills Used

- **Excel Power Query** — data import and transformation
- **Excel Power Pivot / Data Model** — star-schema relationships
- **PivotTables & PivotCharts** — all KPIs and visuals
- **Slicers** — cross-filtering interactivity
- **Excel 3D Map / Map Chart** — geographic revenue visualization

## 🚀 How to Use

1. Download `Final_project_excel.xlsx`.
2. Open it in **Excel** (Power Query/Power Pivot features require Excel 2016+ or Microsoft 365).
3. Use the slicers on the left (Year, Category, Country, Subcategory, Month) to filter the dashboard, and switch between the **Sales Dashboard** and **Return Dashboard** sheets.

## 📁 Files in This Repo

```
├── Final_project_excel.xlsx           # Full Excel dashboard workbook
├── screenshot-sales-dashboard.png     # Preview image of the main dashboard
└── README.md                          # This file
```

## 👤 Author

**Mohamed Farouk**
Data Quality Reviewer & Analyst | Building a portfolio in Power BI, Excel, and data analytics
[GitHub: Mohamedfarouk96](https://github.com/Mohamedfarouk96)

---

> ⚠️ Note: The build steps above summarize the general workflow based on the workbook's structure (queries, data model relationships, PivotTables, and sheets). If any detail doesn't match exactly how you built it, feel free to tweak the wording before publishing.
