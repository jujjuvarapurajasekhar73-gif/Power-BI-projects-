# 🚚 Supply Chain & Inventory Optimization Executive Dashboard (Power BI)

![Supply Chain Dashboard Preview](Screenshot%202026-11-29%20004111.png)

## 📌 Project Overview
An end-to-end **Power BI Business Intelligence solution** built using the enterprise **Power BI Project (`.pbip`)** format to analyze supply chain logistics, carrier SLA compliance, warehouse bottlenecks, and multi-date revenue performance across regions.

---

## 🔗 Data Modeling & Active/Inactive Relationships (`USERELATIONSHIP`)
Designed a normalized **1-to-Many Star Schema** connecting the central `Fact_Shipments` table with 4 dimension tables (`Dim_Date`, `Dim_Products`, `Dim_Carriers`, `Dim_Warehouse`) and a dedicated `Key_Measures` table:

* **Active Relationship (Solid Line):** `Dim_Date[Date]` ➔ `Fact_Shipments[Order_Date]` (Drives default Order Date reporting and Time Intelligence).
* **Inactive Relationship #1 (Dotted Line):** `Dim_Date[Date]` ➔ `Fact_Shipments[Ship_Date]` (Activated dynamically via `USERELATIONSHIP` to analyze warehouse dispatch volume).
* **Inactive Relationship #2 (Dotted Line):** `Dim_Date[Date]` ➔ `Fact_Shipments[Delivery_Date]` (Activated dynamically via `USERELATIONSHIP` to track completed deliveries by delivery date).

```dax
// Activating Inactive Relationships in DAX
Revenue by Ship Date = 
CALCULATE([Total Revenue], USERELATIONSHIP('Dim Date'[Date], Fact_Shipments[Ship_Date]))

Revenue by Delivery Date = 
CALCULATE([Total Revenue], USERELATIONSHIP('Dim Date'[Date], Fact_Shipments[Delivery_Date]))
```

---

## 🧮 Advanced DAX Measures (20+ Enterprise KPIs)
* **Role-Playing Date Measures (`USERELATIONSHIP`):** `Revenue by Ship Date`, `Revenue by Delivery Date`, `Shipments by Delivery Date`
* **Financial & Profitability:** `Total Revenue` (`SUMX`), `Total Cost`, `Net Profit`, `Net Profit Margin %`, `Average Order Value (AOV)`, `Shipping Cost %`
* **Time Intelligence:** `YTD Revenue` (`TOTALYTD`), `Previous Year Revenue (PY)` (`SAMEPERIODLASTYEAR`), `YoY Revenue Growth %`
* **Supply Chain & SLA Compliance:** `Total Shipments`, `Total Units Shipped`, `Avg Delivery Lead Time (Days)`, `On-Time Delivery %` (`DATEDIFF` + `RELATED`), `Delayed Shipments`, `Storage Capacity Utilization %`
* **Dynamic Ranking & Leaders:** `% Revenue Contribution by Products` (`ALL`), `Product Revenue Rank` (`RANKX`), `Top Performing Carrier` (`TOPN` + `CONCATENATEX`)

---

## ⚡ Power BI Visual Calculations
Implemented native in-visual calculations inside the Monthly Executive Performance table to eliminate complex model overhead:
* **Running Total Revenue:** `RUNNINGSUM([Total Revenue])`
* **Month-over-Month (MoM) Change:** `[Total Revenue] - PREVIOUS([Total Revenue])`
* **3-Month Moving Average (True Trend):** `MOVINGAVERAGE([Total Revenue], 3)`

---

## 📊 Key Business Insights & AI Storytelling
* **Financial Performance:** Generated **₹212.74M** in Total Revenue and **₹76.10M** in Net Profit, led by *Industrial Machinery* (₹107M revenue, ₹41M profit) and *Electronics* (₹59M revenue, ₹20M profit).
* **Carrier SLA Bottlenecks:** While *Maersk Coastal* outperformed its 10-day SLA target (5.4 days average lead time), expedited carriers like *BlueDart Express* (10.5 days vs 2-day SLA) and *DHL Priority Air* (6.8 days vs 1-day SLA) drove the majority of delayed shipments.
* **Warehouse Load Balancing:** Identified *Bengaluru Tech Park WH* and *Mumbai West Logistics* as top contributors to delayed shipments, highlighting an immediate opportunity for regional stock rebalancing.
