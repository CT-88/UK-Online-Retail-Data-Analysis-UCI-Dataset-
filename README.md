# Online Retail Data Analysis (E-Commerce Analytics Project)

## 📌 Project Overview
This project analyzes transactional data from a **UK-based online retail company** specializing in unique, all-occasion gifts. The objective is to extract **business insights**, understand **customer behavior**, and provide **data-driven recommendations** using Python-based data analysis techniques.

The project is designed as a **portfolio piece** to demonstrate applied skills in:
- Data cleaning and feature engineering
- Exploratory data analysis (EDA)
- Customer segmentation (RFM analysis)
- Business-oriented insight generation and reporting

---

## 🏢 Business Context
- **Company Type:** Non-store online retail (E-commerce)
- **Product Range:** Unique gifts for various occasions
- **Customer Base:** Mix of individual retail customers and wholesalers
- **Operations:** UK-registered business serving international customers

The analysis supports strategic decision-making related to **revenue growth, customer retention, product optimization, and geographic expansion**.

---

## 📊 Dataset Description
- **Total Records:** 541,909 transactions  
- **Time Period:** December 1, 2010 – December 9, 2011  
- **Currency:** GBP (£)

### Raw Dataset Features
| Feature | Description |
|------|------------|
| InvoiceNo | Unique transaction identifier (prefix `C` indicates cancellation) |
| StockCode | Product identifier |
| Description | Product description |
| Quantity | Units purchased (negative values indicate returns) |
| InvoiceDate | Date and time of transaction |
| UnitPrice | Price per unit (£) |
| CustomerID | Unique customer identifier |
| Country | Customer’s country |

---

## ⚙️ Feature Engineering
The project extends the raw data with **business-relevant engineered features**.

### Transaction-Level
- `TotalPrice` = Quantity × UnitPrice  
- `Cancelled` (binary indicator)  
- `Returned` (binary indicator)

### Invoice-Level
- `ItemsPerInvoice`
- `TotalQuantityPerInvoice`
- `InvoiceValue`
- `AvgUnitPricePerInvoice`

### Product-Level
- `ProductSalesCount`
- `TotalProductRevenue`
- `AvgProductQuantityPerOrder`
- `ReturnRate`

### Customer-Level
- `CustomerTenure` (customer lifetime in days)

### Temporal
- `YearMonth` (for time-series analysis)

---

## 🧠 Key Analyses Performed
- **Revenue & Order Trends Analysis**
- **Average Order Value (AOV) Analysis**
- **Product Performance & Return Risk Analysis**
- **Customer Segmentation using RFM (Recency, Frequency, Monetary)**
- **Geographic Revenue Distribution**
- **Business KPI Evaluation**

All findings are summarized in a structured business report (`findings.md`).

---

## 🧩 Customer Segmentation (RFM)
Customers were segmented using RFM analysis, revealing strong revenue concentration:

- **High Value Customers:** 28.9% of customers → 76.7% of revenue  
- **Loyal Customers:** 23.6% → 13.4% of revenue  
- **Potential Loyal Customers:** 27.2% → 7.7% of revenue  
- **At Risk & Lost Customers:** 20.3% → 2.3% of revenue  

This highlights a clear **Pareto effect** and informs targeted retention strategies.

---

## 📈 Key Business Insights
- Revenue shows **consistent monthly growth** (avg. 2.82%) with strong seasonality.
- A small customer segment generates the majority of revenue.
- Overall return rate is low (2.2%), but specific products pose **return-related revenue risk**.
- The UK dominates revenue, while several European markets show growth potential.

➡️ Detailed insights and recommendations are available in **`reports/findings.md`**.

---

## 📁 Project Structure
├── data
│ ├── raw_data.csv # Original dataset
│ ├── clean_data.csv # Cleaned dataset
│ ├── expanded_data.csv # Dataset with engineered features
│ └── rfm_data.csv # Customer-level RFM dataset
│
├── notebook
│ ├── initial_data_processing.ipynb
│ └── exploratory_data_analysis.ipynb
│
├── reports
│ ├── figures
│ │ ├── basic_business_health
│ │ ├── returns_cancellations_and_risk
│ │ └── rfm_segmentation
│ └── findings.md # Business findings & recommendations
│
├── pyproject.toml
├── uv.lock
└── README.md