# 📊 E-Commerce Sales & Profitability Analytics Dashboard (Power BI)

![Dashboard Preview](Screenshot%202026-11-21%20212110.png)


## 📌 Project Overview
An end-to-end Business Intelligence solution designed to analyze e-commerce sales performance, profit margins, regional demand, and product rankings across multi-year transactions (2024–2026).

## 🛠️ Tech Stack & Key Features
- **ETL & Data Cleaning (Power Query & M-Code):** Built custom M-code logic to parse inconsistent date formats, standardized text casing, handled null regions, and removed duplicate transactions.
- **Data Modeling:** Architected a **Star Schema** connecting `Fact_Sales` with `Dim_Products`, `Dim_Customers`, `Dim_Region`, and a dynamic DAX `Dim_Date` table (`CALENDARAUTO`).
- **Advanced DAX Measures (14 KPIs):** Implemented `SUMX` iterators, Time Intelligence (`TOTALYTD`, `SAMEPERIODLASTYEAR`, `YoY % Growth`), `AOV`, dynamic product ranking (`RANKX`, `TOPN`), and `% Sales Contribution` (`ALL`).
- **AI & Interactive Storytelling:** Integrated Power BI's **Smart Narrative** visual for automated executive insights.

## 📈 Key Business Insights
- **Total Revenue:** ₹149.06M | **Overall Profit:** ₹48.77M (**32.72% Profit Margin**)
- **YoY Growth:** +41.75% growth in peak periods driven by high-margin categories.
- **Top Performing States:** Andhra Pradesh, Maharashtra, West Bengal, Tamil Nadu, and Telangana lead overall order volume.
