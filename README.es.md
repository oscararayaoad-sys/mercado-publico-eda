# Public Spending Analysis in Chile's Mercado Público

**How and where does the Chilean State spend through Mercado Público, and where are the best opportunities for a supplier?**

Exploratory Data Analysis (EDA) of ~1.1 million public purchase orders from Mercado Público (ChileCompra), structured around a concrete business question: identifying spending patterns, geographic/sectoral concentration, and accessible market niches for new suppliers.

> 🛠️ **Stack:** Python · pandas · NumPy · Matplotlib · Seaborn · Jupyter · Power BI  
> 📊 **Type:** Exploratory Data Analysis (EDA) with a business focus & data pedagogy approach  
> 🗂️ **Source:** Mercado Público Open Data (ChileCompra)

---

## 🎯 Business Question Framework

To determine where it is worth competing, the core objective is broken down into three fundamental analytical dimensions:

### 1. How does the State spend?
* **1.1 Concentration:** Is spending concentrated among a few agencies or evenly distributed?
* **1.2 Transactional Structure:** Is spending fragmented (mass low-value POs) or consolidated (large contracts)?
* **1.3 Competition:** Do de facto monopolies/oligopolies exist, or is the market open to competition?

### 2. Where does the State spend?
* **2.1 By Sector (`rubro`):** Budget distribution across macro industry sectors.
* **2.2 By Category (`categoria`):** Granular breakdown by product/service subdivisions.
* **2.3 By Region (`region_de_compra`):** Geographic spending centralization.

### 3. What opportunities exist for suppliers?
* **3.1 Agency Entry Barriers:** Public entities with low supplier diversity.
* **3.2 False Niche Filtering:** Identifying high-spend categories heavily concentrated among few suppliers (captive markets).
* **3.3 Dynamic Niches:** Detecting un-saturated sectors with high transactional flow and distributed liquidity.

---

## 💡 Key Findings

1. **Heavy Head Concentration (Extreme Pareto Rule):**
   * The **Top 10 agencies** account for **84.1%** of total spending.
   * The **Top 5 agencies** capture **64.6%** of the budget.
   * **CONAF** leads individually with **19.5%** of recorded expenditure.
   * Massive operational volume in low-value transactions (median of $919.16K CLP; 75% of POs < $3.07M CLP), but total budget is driven by mega-transactions.

2. **Extreme Regional Centralization in Metropolitan Region:**
   * The **Metropolitan Region** absorbs **96.7%** of recorded spending ($66.82 Quadrillion CLP), heavily influenced by corporate headquarters and ministerial billing biases.

3. **Sectoral Dominance in IT and Transportation:**
   * **IT & Telecommunications** leads sector spending with **42.8%**.
   * **Passenger Transport & Logistics** is the top single category by volume at **19.2%** ($13.17 Quadrillion CLP).
   * The top 5 sectors concentrate **93.7%** of the overall budget.

4. **Opportunity Matrix: Distinguishing Real Niches from Captive Markets:**
   * **False Niches:** Sectors like *Financial Services* and *Mining Machinery* feature astronomical spending per supplier ($630.98T CLP and $37.12T CLP respectively), but have only 6 to 8 active suppliers. These are closed oligopolies.
   * **Real Niches:** *Transportation, Storage & Courier* ($140.09T CLP/supplier across 94 suppliers) and *IT subsectors* display high liquidity with open competition.

---

## 🔍 Technical Criteria & Data Engineering Decisions

* **Line vs. Order Granularity:** Each record represents an item line (`total_linea_neto`). This value was isolated from `MontoTotalOC` to prevent double-counting upon aggregation.
* **Currency & VAT Reconciliation:** Verified currency consistency (99.4% CLP) and reconciled gaps between net and gross order values.
* **Geographic Entity Normalization:** Consolidated 32 inconsistent regional labels into the 16 official Chilean regions via Unicode normalization and keyword string matching.
* **Automated Pareto Curves:** Implemented cumulative spending analysis (80/20) to evaluate concentration across agencies, sectors, categories, and regions.
* **Diagnose Before Fixing:** Verified raw data anomalies before applying fixes, uncovering unclassified data patterns in local public education services and security agencies.

---

## 📈 Visualizations & Pareto Analysis

* **Pareto Chart by Agency:** Illustrates how the Top 10 entities absorb 84.1% of the total budget.
* **Sector & Category Breakdown:** Highlights IT and Logistics dominance.
* **Interactive Power BI Dashboard:** Real-time dynamic dashboard for recalculating spending, maps, and supplier distributions.

---

## 📊 Market Opportunity Matrix

| Category / Sector | Market Type | Suppliers | PO Volume | Spend / Supplier | Diagnosis |
| :--- | :--- | :---: | :---: | :---: | :--- |
| **Transportation, Storage & Courier** | Open / Dynamic | 94 | 2,101 | **$140.09T CLP** | 🟢 **Niche #1:** High transaction flow and high return per supplier. |
| **IT & Telecom (Subsector 1782)** | Open / Dynamic | 364 | 2,565 | **$26.33T CLP** | 🟢 **Niche #2:** Highest transactional turnover. |
| **IT & Telecom (Subsector 1802)** | Competitive / Moderate | 429 | 2,024 | **$28.69T CLP** | 🟢 **Niche #3:** High accumulated liquidity. |
| **Financial Services / Banking** | Closed / Concentrated | 6 | 11 | **$630.98T CLP** | 🔴 **False Niche:** Institutional banking oligopoly. |
| **Mining Machinery** | Closed / Concentrated | 8 | 10 | **$37.12T CLP** | 🔴 **False Niche:** Extreme technical exclusivity. |

---

## 📂 Repository Structure

```
.
├── notebooks/
│   ├── 01_cleaning_mercado_publico_eda.ipynb        # Data loading, cleaning & normalization
│   └── 02_analyze_mercado_publico_eda.ipynb         # Exploratory data & Pareto analysis
├── assets/                      # Exported charts and GIFs
├── data/                        # Excluded: Processed Parquet dataset
├── dashboard/                   # Power BI dashboard file (.pbix)
├── reports/
│   ├── executive_summary.es.md
│   └── executive_summary.md
├── README.es.md
└── README.md
```

---

## 🧰 Tools

| Category | Tools |
|---|---|
| Language | Python 3.13 |
| Data Manipulation | pandas, NumPy |
| Visualization | Matplotlib, Seaborn, **Power BI** |
| Environment | Jupyter Notebook, VS Code, Git |

---

## 👤 Autor

**Oscar Araya Díaz**  
Data Analyst · Santiago, Chile 🇨🇱

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/oscar-araya-diaz-7a418a170)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/oscararayaoad-sys)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:oscar.araya.oad@gmail.com)