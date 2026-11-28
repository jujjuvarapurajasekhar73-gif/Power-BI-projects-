# 🚚 Supply Chain & Inventory Optimization Executive Dashboard (Power BI)

![Supply Chain Dashboard Preview](Screenshot%202026-11-29%20004111.png)


## 📌 Project Overview
An end-to-end **Power BI Business Intelligence solution** designed to analyze supply chain operations, carrier SLA performance, warehouse bottlenecks, and financial profitability across multiple regions. Built using the modern **Power BI Project (`.pbip`)** format for enterprise version control and CI/CD readiness.

---

## 🛠️ Technical Architecture & Skills Demonstrated
* **Data Modeling (Star Schema):** Built a normalized 1-to-Many Star Schema connecting `Fact_Shipments` with `Dim_Date`, `Dim_Products`, `Dim_Carriers`, and `Dim_Warehouse`, alongside a dedicated `Key_Measures` table for clean model organization.
* **Advanced DAX (20+ Measures):** Implemented `SUMX`, `DIVIDE`, Time Intelligence (`TOTALYTD`, `SAMEPERIODLASTYEAR`, `YoY Revenue Growth %`), Dynamic Ranking (`RANKX`), Dynamic Text Extraction (`TOPN` + `CONCATENATEX`), and SLA compliance logic (`DATEDIFF` + `RELATED`).
* **Power BI Visual Calculations:** Created high-performance in-visual calculations for **Running Total Revenue** (`RUNNINGSUM`), **Month-over-Month Change** (`PREVIOUS`), and **3-Month Moving Average** (`MOVINGAVERAGE`) to uncover true revenue trends.
* **AI & Executive Storytelling:** Integrated **AI Smart Narrative** with alternating two-tone KPI cards, custom formatting, and dynamic slicers (`Year`, `Region`).

---

## 🧮 Key DAX Measures Implemented
* **Financials:** `Total Revenue`, `Total Cost`, `Net Profit`, `Net Profit Margin %`, `Average Order Value (AOV)`, `Shipping Cost %`
* **Time Intelligence:** `YTD Revenue`, `Previous Year Revenue (PY)`, `YoY Revenue Growth %`
* **Supply Chain & SLA:** `Total Shipments`, `Total Units Shipped`, `Avg Delivery Lead Time (Days)`, `On-Time Delivery %`, `Delayed Shipments`, `Storage Capacity Utilization %`
* **Dynamic Ranking & Leaders:** `% Revenue Contribution by Products`, `Product Revenue Rank`, `Top Performing Carrier`

---

## 📊 Key Business Insights
* **Financial Performance:** Achieved **₹212.74M** in Total Revenue and **₹76.10M** in Net Profit, driven primarily by *Industrial Machinery* (₹107M revenue, ₹41M profit) and *Electronics* (₹59M revenue, ₹20M profit).
* **Carrier SLA Bottlenecks:** While *Maersk Coastal* outperformed its 10-day SLA target (5.4 days average lead time), expedited carriers like *BlueDart Express* (10.5 days vs 2-day SLA) and *DHL Priority Air* (6.8 days vs 1-day SLA) were the primary drivers of delayed shipments.
* **Warehouse Operations:** Identified *Bengaluru Tech Park WH* and *Mumbai West Logistics* as top contributors to delayed shipments, highlighting an immediate opportunity for warehouse load balancing and capacity optimization.
