# 📊 Inventory & Vendor Performance Analysis — Python, SQL, SQLite, Excel & Power BI

An end-to-end **inventory and vendor performance analysis project** focused on analyzing purchasing, sales, product performance, profitability, supplier contribution, and freight costs to generate actionable business insights.

The project follows a complete **Data Analytics and Business Intelligence workflow**, starting with a relational **SQLite database**, followed by **SQL-based data integration and analysis**, **Python data cleaning and exploratory data analysis**, **Excel-based data preparation**, and an interactive **Power BI dashboard**.

The analysis evaluates vendor contribution, purchasing patterns, sales performance, profitability, supplier concentration, product performance, and freight costs to support **data-driven procurement, inventory, and vendor management decisions**.

---

## 📊 Dashboard Overview

An interactive **Power BI dashboard** was developed to provide a comprehensive overview of vendor performance, purchasing, sales, profitability, freight costs, and supplier concentration.

### 📸 Dashboard Preview

![Vendor Performance Dashboard](Vendor%20performance%20Dashboard.png)

The Power BI dashboard provides an interactive view of key business metrics through KPI cards, vendor analysis, product performance charts, profitability analysis, and supplier contribution visualizations.

### 📌 Dashboard KPIs

- **Total Purchase**
- **Total Sales**
- **Gross Profit**
- **Profit Margin**
- **Total Freight**
- **Vendor Contribution**

---

## ❓ Business Questions

The analysis was designed to answer the following business questions:

- Which vendors contribute the most to total purchasing value?
- How concentrated is the company's purchasing across suppliers?
- Which suppliers have the highest purchase contribution?
- Which vendors have strong sales performance?
- Which products generate the highest sales?
- Which products have the highest and lowest profit margins?
- What is the relationship between sales performance and profit margin?
- Which vendors generate high purchasing costs but comparatively lower sales?
- How do freight costs vary across vendors?
- Which products may require pricing or promotional attention?
- Are there opportunities to diversify the supplier base?
- How can vendor performance be evaluated using multiple business metrics?

---

## 🔄 Project Pipeline

### 1. SQLite — Source Database

The project started with a relational **SQLite inventory database** containing millions of transactional records across multiple tables.

The database contains information related to:

- Sales
- Purchases
- Product pricing
- Vendor invoices
- Beginning inventory
- Ending inventory

The relational structure allowed information from multiple business processes to be integrated for comprehensive vendor and product performance analysis.

---

### 2. SQL — Data Integration & Business Analysis

SQL was used to integrate information from multiple relational tables and create a consolidated dataset for vendor and product performance analysis.

The SQL analysis involved:

- Joining multiple relational tables
- Filtering invalid or irrelevant records
- Aggregating sales transactions
- Aggregating purchase transactions
- Calculating vendor-level metrics
- Calculating product-level metrics
- Analyzing freight costs
- Measuring profitability
- Calculating supplier contribution
- Comparing purchasing and sales performance

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
### 3. Python — Data Cleaning & Transformation

Python was used to clean, transform, and prepare the data for exploratory analysis and visualization.

#### Data Cleaning

The data preparation process included:

- Handling missing values
- Removing invalid or irrelevant records
- Filtering transactions with meaningful business activity
- Standardizing data types
- Checking for duplicate records
- Validating numerical fields
- Aggregating transactional data
- Joining vendor and product information
- Preparing analysis-ready datasets

#### Business Metric Engineering

Several business metrics were calculated to evaluate vendor and product performance, including:

- Total Purchase Quantity
- Total Purchase Value
- Total Sales Quantity
- Total Sales Value
- Gross Profit
- Profit Margin
- Total Freight
- Stock Turnover
- Sales-to-Purchase Ratio
- Vendor Contribution

---

### 4. Python — Exploratory Data Analysis

Python was used to perform exploratory data analysis and identify trends, patterns, relationships, and potential business opportunities within the dataset.

The analysis focused on:

- Vendor purchasing patterns
- Supplier contribution
- Product sales performance
- Profitability
- Purchase versus sales relationships
- Freight costs
- Supplier concentration
- High-performing products
- Low-performing products

#### 📌 Python Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### 5. Power BI — Dashboard Development

The processed data was imported into **Power BI** to create an interactive business intelligence dashboard.

The dashboard combines purchasing, sales, profitability, vendor contribution, and freight metrics into a single analytical interface.

The report includes:

- KPI cards
- Vendor contribution analysis
- Top vendor analysis
- Product performance analysis
- Sales and profitability comparisons
- Supplier concentration analysis
- Freight cost analysis
- Interactive filters and slicers
- Business performance comparisons

---

## 🗂️ Data Dictionary

The project integrates information from several relational tables.

### `sales`

Contains product-level sales transaction information.

| Column | Description |
|--------|-------------|
| `InventoryId` | Unique inventory identifier |
| `Store` | Store associated with the transaction |
| `Brand` | Product brand |
| `Description` | Product description |
| `Size` | Product size |
| `SalesQuantity` | Quantity sold |
| `SalesDollars` | Total sales value |
| `SalesPrice` | Selling price |
| `SalesDate` | Date of sale |
| `Volume` | Product volume |
| `Classification` | Product classification |
| `ExciseTax` | Excise tax amount |
| `VendorNo` | Vendor identifier |
| `VendorName` | Vendor name |

### `purchases`

Contains purchasing transaction information.

| Column | Description |
|--------|-------------|
| `VendorNumber` | Vendor identifier |
| `VendorName` | Vendor name |
| `Brand` | Product brand |
| `PurchasePrice` | Purchase price |
| `Quantity` | Purchased quantity |
| `Dollars` | Total purchase value |

### `purchase_prices`

Contains product pricing and vendor information.

| Column | Description |
|--------|-------------|
| `Brand` | Product brand |
| `Description` | Product description |
| `Price` | Actual selling price |
| `Size` | Product size |
| `Volume` | Product volume |
| `Classification` | Product classification |
| `PurchasePrice` | Product purchase price |
| `VendorNumber` | Vendor identifier |
| `VendorName` | Vendor name |

### `vendor_invoice`

Contains vendor invoice and freight-related information.

### `begin_inventory`

Contains beginning inventory information.

### `end_inventory`

Contains ending inventory information.

---

## 📊 Dashboard Features

The Power BI dashboard provides an interactive view of inventory and vendor performance.

Key dashboard features include:

- **Total Purchase KPI**
- **Total Sales KPI**
- **Gross Profit KPI**
- **Profit Margin KPI**
- **Total Freight KPI**
- Vendor contribution analysis
- Top vendor ranking
- Product sales analysis
- Product profitability analysis
- Purchase versus sales comparison
- Supplier concentration analysis
- Freight cost analysis
- Interactive filtering and slicers

---

## 📈 Key Metrics

The project calculates several business metrics to evaluate vendor and product performance.

### Gross Profit

```text
Gross Profit = Total Sales - Total Purchase
```
### Profit Margin
```text
Profit Margin = Gross Profit / Total Sales
```
### Vendor Contribution
```text
Vendor Contribution = Vendor Purchase Value / Total Purchase Value
```
These metrics provide a consistent framework for comparing vendors and products based on financial and operational performance.

# 💡 Key Business Insights

## 1. High Supplier Concentration

The **top 10 vendors account for approximately 99.05% of total purchase value**, indicating significant purchasing dependency on a small group of suppliers.

This high concentration suggests potential supplier dependency and supply-chain risk.

---

## 2. Dominant Supplier

**MARTIGNETTI COMPANIES** contributes approximately **85.99% of total purchase value**, making it the most influential supplier in the dataset.

The supplier's large contribution means that changes in its pricing, availability, or purchasing terms could have a significant impact on overall procurement operations.

---

## 3. Supplier Diversification Opportunity

The high concentration of purchases suggests an opportunity to evaluate **supplier diversification strategies**.

Diversifying the supplier base could help reduce:

* Supply-chain dependency
* Vendor-specific risk
* Pricing dependency
* Procurement disruption risk

---

## 4. Profitability-Based Product Analysis

Comparing sales performance with profit margins helps identify products that may require further business attention.

Potential actions include:

* Promotional strategies
* Pricing adjustments
* Cost optimization
* Supplier negotiation
* Inventory management improvements

---

## 5. Data-Driven Vendor Management

Combining **purchasing, sales, profitability, and freight metrics** provides a comprehensive approach to evaluating vendor performance rather than relying only on purchasing or sales figures.

Vendors can be evaluated using:

* Purchase contribution
* Sales performance
* Gross profit
* Profit margin
* Freight cost
* Stock turnover
* Sales-to-purchase ratio

This provides a more balanced approach to vendor evaluation and procurement decision-making.

---

## 🛠️ Tools & Technologies

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **SQL**
* **SQLite**
* **Excel**
* **Power BI**
* **DAX**
* **Google Colab**

---

## 📁 Project Structure

```text
Inventory & Vendor Performance Analysis/
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
├── sql/
│   └── vendor_analysis.sql
│
├── powerbi/
│   └── vendor_performance.pbix
│
├── screenshots/
│   └── dashboard_overview.png
│
└── requirements.txt
```

---

## 🎯 Project Goal

The primary goal of this project is to develop an **end-to-end data analytics and business intelligence solution** for evaluating inventory, purchasing, sales, product, and vendor performance.

The project demonstrates the complete workflow from raw database data to actionable business insights.

### Project Workflow

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
Excel Data Preparation
        ↓
Power BI Dashboard
        ↓
Business Insights
```

The final analysis provides a data-driven framework for:

* Identifying supplier dependencies
* Evaluating vendor performance
* Analyzing product performance
* Understanding profitability
* Monitoring purchasing and sales activity
* Analyzing freight costs
* Supporting supplier diversification
* Improving inventory management
* Supporting procurement decisions

Overall, the project demonstrates how **SQL, Python, Excel, and Power BI** can be integrated to transform raw business data into meaningful insights and support **data-driven decision-making**.

