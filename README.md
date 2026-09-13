# 📊 Inventory & Vendor Performance Analysis

## 📌 Project Overview

This project focuses on analyzing **inventory, purchasing, sales, pricing, and vendor performance** to uncover meaningful business insights and support data-driven decision-making.

The project follows an end-to-end **Data Analytics and Business Intelligence workflow**, starting with a relational **SQLite database**, followed by **SQL-based data integration and transformation**, **Python exploratory data analysis**, and an interactive **Power BI dashboard**.

The analysis evaluates vendor contribution, purchasing patterns, sales performance, profitability, supplier concentration, product performance, and other key business metrics.

---
## 📊 Power BI Dashboard

An interactive **Power BI dashboard** was developed to provide a comprehensive view of vendor performance, purchasing, sales, profitability, and supplier concentration.

### 📸 Dashboard Preview

![Vendor Performance Dashboard](Vendor%20performance%20Dashboard.png)

### 📌 Dashboard KPIs

- **Total Purchase**
- **Total Sales**
- **Gross Profit**
- **Profit Margin**
- **Total Freight**
- **Vendor Contribution**
## 🎯 Business Objectives

The main objectives of this project are to:

- Analyze **vendor purchasing and sales performance**
- Identify important suppliers based on **purchase contribution**
- Evaluate **vendor profitability and sales performance**
- Analyze **product-level sales and profit margins**
- Measure **supplier concentration** and purchasing dependency
- Examine the relationship between **sales and profit margin**
- Identify products that may require **pricing or promotional attention**
- Analyze **freight costs** and their impact on vendor performance
- Build an interactive **Power BI dashboard**
- Generate actionable insights to support **vendor and inventory management**

---

## 🛠️ Tools & Technologies

| Technology | Purpose |
|------------|---------|
| **Python** | Data analysis and exploratory data analysis |
| **Pandas** | Data manipulation and aggregation |
| **NumPy** | Numerical analysis |
| **Matplotlib** | Data visualization |
| **Seaborn** | Statistical visualization |
| **SQL** | Data extraction, joining, filtering, and aggregation |
| **SQLite** | Database management |
| **Power BI** | Interactive dashboard and business intelligence |
| **Excel** | Data preparation and analysis |
| **Google Colab** | Python development environment |

## 🗂️ Dataset

The project uses a relational inventory and vendor database containing **millions of transactional records**.

### Main Tables

### `sales`

Contains product-level sales transactions, including:

- `InventoryId`
- `Store`
- `Brand`
- `Description`
- `Size`
- `SalesQuantity`
- `SalesDollars`
- `SalesPrice`
- `SalesDate`
- `Volume`
- `Classification`
- `ExciseTax`
- `VendorNo`
- `VendorName`

### `purchases`

Contains purchasing transaction information, including:

- `VendorNumber`
- `VendorName`
- `Brand`
- `PurchasePrice`
- `Quantity`
- `Dollars`

### `purchase_prices`

Contains product pricing and vendor information, including:

- `Brand`
- `Description`
- `Price`
- `Size`
- `Volume`
- `Classification`
- `PurchasePrice`
- `VendorNumber`
- `VendorName`

### `vendor_invoice`

Contains vendor invoice and freight-related information.

### `begin_inventory`

Contains beginning inventory information.

### `end_inventory`

Contains ending inventory information.

---

## 🔄 Project Workflow

```text
Raw SQLite Database
        ↓
Data Exploration
        ↓
SQL Data Integration
        ↓
Data Cleaning & Transformation
        ↓
Vendor & Product Aggregation
        ↓
Business Metric Calculation
        ↓
Python Exploratory Data Analysis
        ↓
Data Visualization
        ↓
Power BI Dashboard
        ↓
Business Insights

```
## 🗄️ SQL Analysis

SQL was used to integrate information from multiple relational tables and create a consolidated dataset for vendor and product performance analysis.

The SQL analysis involved:

- Joining multiple relational tables
- Filtering invalid or irrelevant records
- Aggregating sales and purchase transactions
- Calculating vendor-level metrics
- Calculating product-level metrics
- Analyzing freight costs
- Measuring profitability
- Calculating supplier contribution

### Example SQL Analysis

```sql
SELECT 
    p.VendorNumber,
    p.VendorName,
    p.Brand,
    pp.Description,
    p.PurchasePrice,
    pp.Volume,
    pp.Price AS ActualPrice,
    SUM(p.Quantity) AS TotalPurchaseQuantity,
    SUM(p.Dollars) AS TotalPurchaseDollars
FROM purchases p
JOIN purchase_prices pp 
    ON p.Brand = pp.Brand
WHERE p.PurchasePrice > 0
GROUP BY 
    p.VendorNumber,
    p.VendorName,
    p.Brand,
    pp.Description,
    p.PurchasePrice,
    pp.Volume,
    pp.Price;
```

## 🧹 Data Cleaning & Transformation

The data was cleaned and transformed before performing the final analysis.

Major data preparation steps included:

- Removing invalid or irrelevant records
- Handling missing values
- Filtering records with meaningful sales activity
- Aggregating transactional data
- Joining vendor, product, sales, and purchase information
- Creating calculated business metrics
- Preparing an analysis-ready dataset for Python and Power BI

## 🐍 Python Exploratory Data Analysis

Python was used to perform exploratory data analysis and identify trends, patterns, and relationships within the dataset.

The analysis focused on vendor performance, product performance, profitability, purchasing behavior, and sales trends.

# 📌 Python Libraries
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
# 💡 Key Business Insights

## 1. High Supplier Concentration

The **top 10 vendors account for approximately 99.05% of total purchase value**, indicating significant purchasing dependency on a small group of suppliers.

## 2. Dominant Supplier

**MARTIGNETTI COMPANIES** contributes approximately **85.99% of total purchase value**, making it the most influential supplier in the dataset.

## 3. Supplier Diversification Opportunity

The high concentration of purchases suggests an opportunity to evaluate **supplier diversification strategies** to reduce dependency and potential supply-chain risk.

## 4. Profitability-Based Product Analysis

Comparing sales performance with profit margins helps identify products that may benefit from:

- Promotional strategies
- Pricing adjustments
- Cost optimization
- Supplier negotiation

## 5. Data-Driven Vendor Management

Combining **purchasing, sales, profitability, and freight metrics** provides a comprehensive approach to evaluating vendor performance rather than relying on sales or purchasing figures alone.

---

# 📁 Project Structure

```text
Vendor-Performance-Analysis-Dashboard/
│
├── README.md
│
├── data/
│   ├── cleaned_inventory_data.xlsx
│   └── inventory.db
│
├── notebooks/
│   ├── cleaning_data.ipynb
│   └── performance_analysis_eda.ipynb
│
├── powerbi/
│   └── vendor_performance.pbix
│
└── screenshots/
    └── dashboard_overview.png

```
## 🎯 Project Goal

The primary goal of this project is to analyze vendor, purchasing, sales, and product performance data to identify key business trends, measure profitability, evaluate supplier contribution, and uncover opportunities for improving purchasing and vendor management decisions.
