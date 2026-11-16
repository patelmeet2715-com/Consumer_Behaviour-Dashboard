# 🛍️ Consumer Behavior & E-Commerce Analytics Dashboard | Power BI

**Author:** Meet Patel  
**Dashboard File:** [`consumer_behavior_analytics_PM.pbix`](./consumer_behavior_analytics_PM.pbix)  
**Tools Used:** Power BI Desktop, DAX, Power BI Semantic Modeling, Dimensional Data Modeling, Interactive Data Visualization, AI Decomposition Tree

---

## 📌 Project Overview

**Consumer Behavior & E-Commerce Analytics** is an interactive Power BI analytics project built to explore multi-channel consumer spending patterns, digital adoption drivers, geographic distributions, and logistics/return dynamics.

The report analyzes **11,789 consumers** and a **Combined Monthly Spend of $1,771M** (split across **$879M Online Spend** and **$892M Store Spend**), utilizing a robust dimensional data model. Core KPI measures provide a consistent view of consumer behavior across a **4-page executive report**. The dashboard includes synchronized slicers, cross-filtering, hierarchy drill-downs, AI decomposition trees, and page-navigation buttons.

The report is designed to answer practical business questions such as:

- How is consumer spend distributed between brick-and-mortar stores, online platforms, and hybrid channels?
- What are the spending habits and basket sizes across different income brackets and age cohorts?
- How do psychographic factors like tech-savvy tiers and tactile touch/feel needs drive digital adoption?
- How do delivery SLAs and return policies impact return-to-order ratios across regional logistics zones?

---

## 📊 Report Pages & Key Insights

1. **Page 1 — Executive & Wallet Share**
   - KPI cards summarize **Total Consumers (11,789)**, **Combined Monthly Spend ($1,771M)**, **Total Online Spend ($879M)**, **Total Store Spend ($892M)**, and **Digital Adoption Rate (0.13)**.
   - Consumer distribution by shopping preference is led by **Store (86.89%)**, followed by **Online (9.98%)**, and **Hybrid (3.13%)**.
   - Compares online vs. store spend and wallet share percentage across primary buying archetypes.
   - Breakdown of channel preference shares across City Tiers (Tier 1, Tier 2, and Tier 3) via a hierarchy drill-down.

2. **Page 2 — Spend & Order Velocity**
   - Tracks average online and store spend per consumer categorized by channel preference and age cohort (**Gen Z, Millennials, Gen X, Boomers+**).
   - Displays implied online basket size (AOV) rankings across income brackets (**Low, Middle, High**).
   - Monthly transaction velocity scorecards covering online orders (~291K monthly) and store visits (~112K monthly).
   - Gender segment and income bracket unit economics drill-down matrix.

3. **Page 3 — Behavioral & Tech Drivers**
   - Highlights the **Digital Readiness Index (5.52)**, **Physical Friction Index (5.47)**, and **Net Digital Momentum (0.05)**.
   - Visualizes how tech-savvy tiers drive online adoption (showing a **2.53x lift** for high-tech users).
   - Examines how tactile touch/feel needs lock shoppers into physical stores.
   - Quadrant analysis mapping digital readiness versus physical friction by buyer archetype (Digital Hesitant, Digital Vanguard, Mainstream Connected).

4. **Page 4 — Logistics SLA & Returns**
   - Tracks **Average Delivery SLA (4.00 Days)**, **Average Return Frequency (4.47)**, and **Return-to-Order Ratio (18%)**.
   - Analyzes online order volume and return rates across delivery days (1 to 7 days).
   - Features an interactive **AI Decomposition Tree** for multi-level drill-through on Return-to-Order ratios.
   - Fulfillment SLA and return policy sensitivity matrix breaking down consumer tolerance across return-focus tiers.

---

## 🗂️ Data Model Architecture

The Power BI semantic model is organized around a central consumer transactional fact table, descriptive geographic/psychographic dimensions, and a dedicated measure table.

| Table Name | Table Type | Role in the Model | Fields / Attributes Used in the Report |
| :--- | :--- | :--- | :--- |
| **`Dim_Geography`** | Dimension | Provides regional and city tier context | `City_Tier`, `Regional_Logistics_Zone` |
| **`Dim_Consumer_Profile`** | Dimension | Holds demographic and psychographic attributes | `Age_Group`, `Gender`, `Income_Bracket`, `Tech_Savvy_Tier`, `Digital_Maturity_Segment` |
| **`Dim_Channel_SLA`** | Dimension | Defines shopping preferences and logistics parameters | `Shopping_Preference`, `Delivery_SLA_Days`, `Return_Policy_Tier` |
| **`Fact_Consumer_Transactions`** | Fact | Central fact table capturing spend, orders, visits, and returns | `Online_Spend`, `Store_Spend`, `Monthly_Orders`, `Store_Visits`, `Return_Frequency` |
| **`Meet Measure`** | Measure Table | Central location for reusable business measures | Core business metrics listed below |

> The report file contains the semantic model and report definition. Source source files are contained within the unified dashboard architecture.

---

## 📐 Core DAX Measures

The report utilizes standardized measures consistently across its KPI cards, charts, matrices, and decomposition trees.

| Measure Name | Business Logic | Description |
| :--- | :--- | :--- |
| **`Total Consumers`** | Distinct count of consumer IDs | Total unique customer base in current filter context |
| **`Combined Monthly Spend`** | Sum of online and store spend | Total monthly monetary volume across channels |
| **`Digital Adoption Rate`** | Ratio of online-preferred users to total | Proportion of customers favoring digital-first shopping |
| **`Implied Online AOV`** | `Total Online Spend ÷ Monthly Online Orders` | Average transaction basket value for digital purchases |
| **`Return-to-Order Ratio`** | `Total Returns ÷ Total Orders` | Percentage of delivered orders resulting in returns |

The measures dynamically adjust to slicer and cross-filter contexts across all report pages.

---

## 🛠️ Modeling & Dashboard Features

1. **Dimensional Model:** Consumer metrics are structured using a core fact table linked to comprehensive geographic, demographic, and behavioral dimensions.
2. **Centralized Measures:** Key financial, operational, and behavioral KPIs are grouped in the `Meet Measure` table for consistent reuse.
3. **AI Decomposition Tree:** Integrated on Page 4 to automatically analyze drivers behind the Return-to-Order ratio.
4. **Interactive Slicers:** Global filters for City Tier, Shopping Channel, Age Cohort, Income Bracket, Gender, and Tech-Savvy Tier.
5. **Cross-Filtering:** Dynamic visual interactions where selecting chart segments updates related scorecards and matrices.
6. **Page Navigation:** Direct button-based access across all four functional report pages with active state indicators.
7. **Consistent Visual Design:** Built with a modern executive dashboard aesthetic featuring custom card layouts, high-contrast palette accents, and a 16:9 widescreen canvas.
