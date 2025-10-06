# 🏠 Housing Market Analysis Dashboard

### **Dashboard Link:** [View on Power BI Service](https://app.powerbi.com/)  
 
---

## 🧩 Problem Statement

The **Housing Market Dashboard** provides an analytical overview of property sales across regions, sales types, and housing categories.  
It helps real estate analysts, investors, and policymakers understand:  

- Regional performance of housing sales  
- Year-over-year (YoY) growth patterns  
- Relationships between offer and purchase prices  
- Price per square meter (SQM) by region and house type  
- Impact of inflation, yield, and interest on housing trends  

By using this dashboard, stakeholders can **identify regions with higher price appreciation, sales decline, or market saturation**, and adjust investment strategies accordingly.

---

## 🧠 Tools & Technologies Used

- **SQL Server** → Data extraction, cleaning, and aggregation  
- **Power BI Desktop** → Data modeling, visualization, and DAX analysis  
- **Excel** → Used for preliminary data checks  
- **DAX (Data Analysis Expressions)** → Used to create calculated measures and KPIs  

---

## ⚙️ Steps Followed

### **Step 1: Data Preparation**
- Loaded multiple housing datasets into Power BI Desktop.  
- Created a **measure table** to centralize all DAX calculations.  
- Cleaned data using **Power Query**:
  - Checked for nulls, duplicates, and inconsistencies.  
  - Verified column data types (e.g., numeric for price fields, categorical for region/type).  

### **Step 2: Data Modeling**
- Established relationships between tables:
  - `housing` (main fact table) linked with `date` and `measure table`.  
- Ensured proper **one-to-many** relationships for accurate filtering.  

### **Step 3: DAX Measures Created**
Some of the main DAX measures used include:

```DAX
Median Sales Price Change = MEDIANX(housing, housing[%_change_between_quarters])
TotalYTD Sales = TOTALYTD(SUM(housing[purchase_price]), 'date'[date])
Offer to SQM Ratio = DIVIDE(SUM(housing[offer Price]), SUM(housing[sqm]))
YOY Sales Growth = CALCULATE(SUM(housing[purchase_price]), SAMEPERIODLASTYEAR('date'[date]))
Units Sold in Last 12 Months = CALCULATE(COUNT(housing[house_id]), DATESINPERIOD('date'[date], MAX('date'[date]), -12, MONTH))
```

---

## 📊 Dashboard Pages Overview

### **1️⃣ House Market Overview**
- Shows **Median Sales Price Change by Region**
- **Offer vs Purchase Price** scatter plot highlights pricing correlations  
- **Key Metrics Cards:**
  - Units Sold (Latest Year & Quarter)
  - 12-Month Total Sales Value (≈13bn)
- **YOY Sales Growth by Sales Type** visual identifies declining or growing trends

 
---

### **2️⃣ Sales Performance**
- **Sales by Region** funnel chart ranks regional sales volumes  
- **Key Influencers Visual** explains factors influencing total purchase price (e.g., age effect)  
- **Offer to SQM Ratio by Sales Type** highlights which sale types deliver better returns  
- **Average Price per SQM by Region (Pie Chart)** shows regional distribution of housing cost per area  

 
---

### **3️⃣ House Type Analysis**
- Page allows interactive filtering by:
  - **Region**, **City**, **Sales Type**, and **Area**
- **Average Offer vs Purchase Price by House Type**
- **Inflation / Interest / Yield Comparison**
- **Average SQM & SQM Price by House Type**

📈 *This helps investors compare house types (Apartment, Villa, Farm, etc.) on profitability and growth.*

 
---

## 💡 Key Insights

### 🔹 Market Overview
- Total units sold (latest year): **77**
- Total 12-month sales value: **13 bn**
- Offer and purchase prices are closely correlated, indicating a stable market.

### 🔹 Regional Trends
- **Jutland** shows the highest median price change among regions.  
- **Bornholm** experienced a slight negative change, indicating slower growth.  

### 🔹 Sales Type Trends
- YoY Sales Growth:
  - **Auction:** +0.29  
  - **Regular Sale:** −0.21  
  - **Other Sale:** −0.21  
  - **Family Sale:** −0.75  
  ⮕ *Regular and family sales show declining growth.*

### 🔹 Price Analysis
- **Zealand** region leads with the highest average SQM price (≈ 20.8K).  
- **Bornholm** and **Fyn & Islands** have lower price points, suggesting more affordability.  

---

## 🚀 Insights Summary

| Category | Key Takeaway |
|-----------|---------------|
| Top-Performing Region | **Zealand** |
| Weakest-Performing Region | **Bornholm** |
| Best-Performing Sales Type | **Auction** |
| Overall Market Trend | Moderate growth with declining YoY in family/regular sales |
| Recommendation | Focus on boosting regular and family sales through pricing strategy and improved affordability. |

---

## 📤 Publishing
- The final report was **published to Power BI Service** for online access and sharing.  
- Interactive slicers allow region-wise and type-wise drill-down for deeper insights.  

---

## 🧾 Report Snapshots

| Page | Description |
|------|--------------|
| House Market Overview | Regional trends, key metrics, and YoY growth |
| Sales Performance | Sales by region, influencer analysis, and SQM price |
| House Type Analysis | Detailed breakdown by property category |

---

## 📚 Learnings
- Built a measure table for better DAX organization.  
- Applied various Power BI visuals including Funnel Chart, Pie Chart, and Scatter Plot.  
- Used **Key Influencers Visual** to understand data relationships.  
- Created **interactive filters** (region, city, sales type, area).  

---

## 🧑‍💻  
**Siddharth Sharma**  
📍 Final Year Engineering Student | Aspiring Data Analyst  
📧 siddharth23321@gmail.com


