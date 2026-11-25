# Online Retail Sales Analysis (2009–2010)

## Executive Summary
An end-to-end exploratory and descriptive sales analysis of an online retail dataset (~518,600 cleaned transaction records), built using **Excel** and **Power Query**. The objective of this project was to transform raw transactional data into a clean analytical model, isolate core product revenue from administrative noise, and evaluate performance across **geography**, **products**, and **customer segments**.

---

## Business Problem & Objectives
Raw retail transaction logs often contain returns, manual accounting entries, shipping charges, and incomplete customer records that distort KPIs. This analysis addresses three core business questions:
1. **Geographic Concentration:** How heavily does revenue rely on the domestic market, and which international markets offer the strongest expansion potential?
2. **Product Performance:** Which physical products truly drive top-line revenue once non-product charges are excluded?
3. **Customer Dynamics:** How concentrated is revenue among top accounts, and what share of sales comes from unlinked/guest transactions?

---

## Methodology & Data Preparation
* **ETL & Data Cleaning (Power Query):** Imported and standardized ~518.6k records, resolving date parsing formatting errors and filtering the dataset specifically to completed **Sales** movements (`Movement_Type = Sales`) for gross revenue analysis.
* **Noise & Non-Product Filtering:** Identified high-value non-merchandise entries (e.g., `M` / Manual adjustments at **$175.7k**, `DOT` / Dotcom Postage at **$105.4k**, and `Amazon Fee`) and isolated them from product-level rankings using multi-filter Pivot Table configurations (`Allow multiple filters per field`).
* **Analytical Modeling & Visualization:** Built dynamic Pivot Tables tracking both absolute revenue (`Sum of Total_Amount`) and relative contribution (`% of Grand Total`), paired with Bar Charts and a non-UK Treemap to highlight secondary market structure.

---

## Key Findings & Business Insights

### 1. Geographic Distribution (`Total Sales per Country`)
* **Heavy Domestic Reliance:** The **United Kingdom** generates **$7.94M** (**85.87%** of total sales), exposing the business to high single-market concentration risk[cite: 4].
* **Primary International Markets:** Outside the UK, **EIRE** (**$352.8k**), the **Netherlands** (**$251.9k**), **Germany** (**$171.4k**), and **France** (**$126.8k**) lead international revenue[cite: 5].
* **Data Hygiene Gap:** **$5,959.69** in sales is logged under `Unspecified` country records, indicating minor gaps in order capture validation[cite: 4].

### 2. Product Performance (`Total Sales per Product`)
* **Impact of Non-Product Entries:** Before filtering, `Manual` (`M`) and `Dotcom Postage` (`DOT`) ranked 1st and 4th overall—demonstrating why separating operational fees from inventory SKUs is critical before making merchandising decisions[cite: 6].
* **Core Revenue Drivers:** Excluding administrative codes, top-performing physical SKUs such as **`22423`** (*Regency Cakestand 3 Tier*, **$169.9k**) and **`85123A`** (*White Hanging Heart T-Light Holder*, **$159.8k**) anchor product revenue[cite: 2, 6].

### 3. Customer Segmentation (`Total Sales per Customer`)
* **High Share of Anonymous Transactions:** Unidentified/guest transactions (`(blank)` `CustomerID`) account for **$1.23M** (**49.98%** of the top-segment view), limiting visibility into repeat purchase rates and Customer Lifetime Value (CLV)[cite: 7].
* **Wholesale / B2B Account Concentration:** Among registered customers, top accounts—led by ID **`18102`** (**$242.2k**), **`14646`** (**$233.9k**), and **`14156`** (**$185.5k**)—contribute disproportionately high order volumes, reflecting wholesale or corporate purchasing behavior[cite: 7].

---

## Strategic Recommendations
1. **Improve Customer ID Capture:** Introduce checkout incentives (loyalty points, order tracking, or streamlined account creation) to convert anonymous (`blank`) buyers into trackable customer profiles[cite: 7].
2. **Diversify European Growth:** Allocate targeted marketing and logistics optimization toward **EIRE, the Netherlands, Germany, and France** to gradually reduce over-reliance on the UK market[cite: 5].
3. **Protect Core Inventory & Key Accounts:** Prioritize stock availability for top-10 physical SKUs and establish dedicated account management for high-volume wholesale customers (`18102`, `14646`, `14156`)[cite: 6, 7].

---

## Tools & Skills Demonstrated
* **Excel & Power Query:** Data ingestion, type handling, filtering, multi-sheet workbook architecture
* **Pivot Tables & Charts:** Multi-filter ranking, `% of Grand Total` share calculations, Treemap & Column/Bar visualizations
* **Business Analytics:** KPI definition, data anomaly isolation, executive storytelling
