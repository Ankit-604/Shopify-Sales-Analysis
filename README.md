# Shopify Sales & Customer Intelligence Dashboard 🛒📊

**Author:** Ankit Kumar Sharma  
**Institution:** Presidency University  
**Tech Stack:** Power BI, Power Query (M), DAX, Relational Data Modeling

---

## 📑 Project Overview
This Business Intelligence project transforms over 7,400 raw Shopify transactional records into a dynamic, interactive dashboard. Designed for e-commerce executives, marketing directors, and inventory planners, the tool provides high-level visibility into transaction performance, geographic market concentration, and long-term customer retention.

## 🎯 Business Objectives
The dashboard was engineered to answer critical business questions and drive operational strategy:
* **Transaction Performance:** Which specific product categories and timeframes drive the most revenue?
* **Customer Behavior:** What is the geographic concentration of the market, and what payment gateways reduce checkout friction?
* **Retention & Value:** How loyal is the customer base, and what is their long-term financial viability?

## 🏗️ Technical Methodology & Architecture

### 1. Data Engineering (ETL)
* **Extraction:** Ingested raw `.xlsx` transactional ledgers into **Power Query**.
* **Transformation:** Enforced strict financial data types, standardized regional text strings, filtered null product identifiers, and engineered time-intelligence helper columns (e.g., isolating transaction hours from timestamps).

### 2. Relational Data Modeling
* Built a highly optimized **Star Schema** architecture.
* Engineered a continuous `Dim_Date` calendar table using DAX to support advanced time-intelligence functions and linked it to the primary sales fact table via a 1-to-Many relationship.

### 3. Logic Layer (DAX)
Created a dedicated measure table for dynamic, cross-filtering calculations, including:
* `Total Revenue = SUM('shopify_sales'[Total Price Usd])`
* `Average Order Value (AOV) = DIVIDE([Total Revenue], [Total Orders], 0)`
* `Repeat Purchase Rate = DIVIDE([Repeat Customers], [Total Customers], 0)`
* `Customer Lifetime Value (CLV) = [AOV] * [Purchase Frequency]`

### 4. UI/UX Design
* Implemented a modern dark-theme aesthetic (`#0D1926`) to reduce eye strain.
* Utilized an **F-Pattern visual hierarchy**, placing critical financial KPIs at the top left and exploratory trend charts across the center and right.
* Configured dynamic field parameters and synchronized slicers for seamless drill-down capabilities.

---

## 📈 Key Insights & Business Impact

* **Revenue Generation:** Generated **$4.18 Million** in Net Sales with a highly profitable Net Average Order Value of **$562.60**.
* **Product Dominance:** The portfolio is heavily skewed, with *Running Shoes* ($1.5M) and *Tennis Shoes* ($0.9M) acting as the primary revenue drivers.
* **Purchasing Velocity:** Discovered a massive, sustained spike in daily purchasing volume occurring strictly between **10:00 AM and 2:00 PM**.
* **Brand Loyalty:** The store boasts a highly engaged customer base with a **46% Repeat Purchase Rate** and an estimated Customer Lifetime Value (CLV) of **$943.60**.

---

## 💡 Strategic Recommendations
Based on the data modeled within this dashboard, the following actions are recommended to executive leadership:
1. **Optimize Marketing Timing:** Shift digital ad spend and schedule promotional email campaigns to deploy at precisely **10:30 AM** to capture the mid-day purchasing surge.
2. **Reallocate Inventory Capital:** Shift procurement budgets to heavily favor top-performing categories (Running/Tennis shoes) to prevent stock-outs, while aggressively reducing capital tied up in slow-moving inventory (e.g., water shoes).
3. **Launch a VIP Loyalty Program:** Institute a formalized VIP tier offering early access or exclusive shipping rates to returning customers to maximize the $943 CLV and prevent churn.

---

## 📂 Repository Contents
* `Shopify Analysis.pbix` - The complete Power BI project file containing the data model, DAX measures, and interactive frontend.
* `Dataset/` - Anonymized Shopify sales raw data used for the analysis.
* `Dashboard_Screenshots/` - High-resolution captures of the Main Overview and Details Ledger sheets.

## 🚀 How to Run
1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
2. Clone this repository to your local machine.
3. Open `Shopify Analysis.pbix` to interact with the dashboard and view the underlying data model.
