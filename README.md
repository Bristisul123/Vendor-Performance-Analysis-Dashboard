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
##🗄️ SQL Analysis

SQL was used to integrate information from multiple relational tables and create a consolidated dataset for vendor and product performance analysis.

The SQL analysis involved:

-Joining multiple relational tables
-Filtering invalid or irrelevant records
-Aggregating sales and purchase transactions
-Calculating vendor-level metrics
-Calculating product-level metrics
-Analyzing freight costs
-Measuring profitability
-Calculating supplier contribution

A consolidated dataset named vendor_sales_summary was created for further analysis.
