# Public Spending Analysis in Chile's Mercado Público

**How and where does the Chilean State spend through Mercado Público, and where are the best opportunities for a supplier?**

Exploratory Data Analysis (EDA) of ~1.1 million public purchase orders from Mercado Público, focused on a concrete business question: identifying spending patterns, geographic concentration, and accessible market niches for a supplier looking to enter public procurement[cite: 1, 2].

> 🛠️ **Stack:** Python · pandas · NumPy · Matplotlib · Seaborn · Jupyter  
> 📊 **Type:** Exploratory Data Analysis (EDA) with a business focus  
> 🗂️ **Source:** Mercado Público Open Data (ChileCompra)

---

## 🎯 The Question

The State of Chile buys goods and services worth trillions of pesos annually through Mercado Público. For a supplier wanting to sell to the State, the key question is: **where is it worth entering?**[cite: 1, 2] This project breaks that question down into three dimensions:

1. **How does the State spend?** — concentrated or distributed?[cite: 1, 2]
2. **Where does it spend?** — distribution by region, sector, and category[cite: 1, 2].
3. **What opportunities exist?** — niches with high spending and accessible competition[cite: 1, 2].

---

## 💡 Key Findings

**1. Spending is heavily concentrated at the top.**  
The **Top 10 agencies** account for **84.1%** of total spending, led individually by **CONAF** (19.5%)[cite: 1, 2]. While transactions are massively fragmented at the operational level (median value of $919.16K CLP, with 75% of POs under $3.07M CLP), total budget is driven by high-value mega-transactions[cite: 1, 2].

**2. Extreme centralization in the Metropolitan Region.**  
The **Metropolitan Region** absorbs **96.7%** of recorded spending ($66.82 Quadrillion CLP), heavily influenced by corporate headquarters and ministerial billing biases, leaving only 3.3% distributed across the remaining 15 regions[cite: 1, 2].

**3. Sectoral spending is led by IT and Transportation.**  
**Information Technology (IT)** leads spending by industry with **42.8%**, while **Transportation & Logistics** is the top single category by volume at **19.2%** ($13.17 Quadrillion CLP)[cite: 1, 2]. The top 5 sectors concentrate 93.7% of the overall budget[cite: 1, 2].

**4. High spend with few suppliers signals a closed market, not an opportunity.**  
High-spending sectors with very few suppliers usually represent **captive markets or oligopolies** (e.g., Financial Services, Mining Machinery) with extreme entry barriers[cite: 1, 2]. Real opportunities lie in **open/dynamic niches** with high transaction flow and distributed liquidity, such as *Transportation & Storage* ($140.09T CLP/supplier) and *IT & Telecommunications*[cite: 1, 2].

---

## 🔍 Key Technical Decisions

Beyond the results, the project documents the reasoning process. Some decisions showcasing the applied criteria:

- **Data Granularity.** Each row represents an item, not an order. Line-level amounts (`totalLineaNeto`) were distinguished from total order amounts (`MontoTotalOC`, which repeats on every line) to avoid inflating totals via double counting[cite: 2].
- **Monetary Column Reconciliation.** The ~2x gap between both columns was investigated and found to be **VAT** (order = gross, line = net), not a data error. Validated by inspecting individual orders[cite: 2].
- **Real Data Cleaning.** `Latin-1` encoding, `;` separator, Chilean decimal comma (`1.234,56`), and currency verification (99.4% CLP) prior to aggregation[cite: 2].
- **Entity Normalization.** Regions arrived with **32 different labels for 16 real regions** (invisible spaces, glyph variants, short vs. long names). These were consolidated using Unicode normalization and keyword matching[cite: 2].
- **Concentration Metric.** Evaluated through volume and supplier count ratios to distinguish open, high-turnover markets from captive oligopolies[cite: 1, 2].
- **Data Quality.** Unclassified records (10.6%) were investigated by proportion, not count: the pattern turned out to be a capture failure in local public education services (100% unclassified) and partial opacity in a security agency (Gendarmería, 61%), rather than general confidentiality[cite: 2].
- **Working Discipline.** *"Diagnose before fixing"*: every anomaly was verified with raw data before applying a correction, avoiding fixing ghosts[cite: 2].
- **Classification Hierarchy.** `RubroN1` is the parent category and `Categoria` is its subdivision (one sector groups several categories)[cite: 2]. Both dimensions are analyzed separately to avoid confusing the aggregation level[cite: 2].

---

## 📈 Visualizations

### Interactive Dashboard (Power BI)

![Public spending dashboard in Power BI](assets/dashboard_demo_mercado_publico_eda.gif)[cite: 2]  
*Interactive dashboard built in Power BI: total spending, top 10 agencies, regional distribution on a map, and sector filter. When selecting a sector, all visuals recalculate in real time.*[cite: 2]

**Spending by Agency — Head Concentration**  
![Spending concentration by agency](assets/concentración_de_gasto_por_organismo.png)[cite: 1, 2]  
*Top 10 agencies account for 84.1% of spending, led by CONAF (19.5%). Nearly two-thirds (64.6%) are executed by just 5 entities.*[cite: 1]

**Spending by Category — Core Priorities**  
![Spending concentration by category](assets/concentración_de_gasto_por_categoría.png)[cite: 1, 2]  
*Top 5 categories represent 74.7% of spend, led by Air Passenger Transport (19.2%) and core IT infrastructure/services.*[cite: 1]

**Spending by Region — Extreme Centralization**  
![Spending concentration by region](assets/concentración_de_gasto_por_región.png)[cite: 1, 2]  
*The Metropolitan Region concentrates 96.7% of total registered spending, reflecting a heavy corporate invoicing bias.*[cite: 1]

**Spending by Sector — IT Dominance**  
![Spending concentration by sector](assets/concentración_de_gasto_por_rubro.png)[cite: 1, 2]  
*IT & Telecommunications captures 42.8% of spending alone. The top 5 sectors cover 93.7% of the total budget.*[cite: 1]

---

## 📊 Market Opportunity Matrix

| Category / Sector | Market Type | Suppliers | PO Volume | Spend / Supplier | Diagnosis |
| :--- | :--- | :---: | :---: | :---: | :--- |
| **Transportation, Storage & Courier** | Open / Dynamic | 94 | 2,101 | **$140.09T CLP** | 🟢 **Niche #1:** High transaction flow and high return[cite: 1]. |
| **IT & Telecom (Subsector 1782)** | Open / Dynamic | 364 | 2,565 | **$26.33T CLP** | 🟢 **Niche #2:** Highest transactional turnover[cite: 1]. |
| **IT & Telecom (Subsector 1802)** | Competitive / Moderate | 429 | 2,024 | **$28.69T CLP** | 🟢 **Niche #3:** High accumulated liquidity[cite: 1]. |
| **Financial Services / Banking** | Closed / Concentrated | 6 | 11 | **$630.98T CLP** | 🔴 **False Niche:** Institutional banking oligopoly[cite: 1]. |
| **Mining Machinery** | Closed / Concentrated | 8 | 10 | **$37.12T CLP** | 🔴 **False Niche:** Extreme technical exclusivity[cite: 1]. |

---

## 📂 Repository Structure

```
.
├── notebooks/
│   ├── 01_cleaning_mercado_publico_eda.ipynb        # Loading and cleaning
│   └── 02_analyze_mercado_publico_eda.ipynb         # Complete analysis
├── assets/                      # Exported charts
├── data/                        # (excluded: public Mercado Público data)
├── dashboard/                   # Power BI dashboard
├── reports/
│   ├── executive_summary.es.md
│   └── executive_summary.md
├── README.es.md
└── README.md
```

> Data is not included due to size; it is publicly downloadable from the Mercado Público (ChileCompra) open data portal[cite: 2].

---

## 🧰 Tools

| Category | Tools |
|---|---|
| Language | Python 3.13 |
| Data Manipulation | pandas, NumPy |
| Visualization | Matplotlib, Seaborn, **Power BI** |
| Dashboard | **Power BI Desktop** |
| Environment | Jupyter Notebook, VS Code, Git |

---

## 👤 Author

**Oscar Araya Díaz**  
Data Analyst · Santiago, Chile 🇨🇱[cite: 2]

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/oscar-araya-diaz-7a418a170)[cite: 2]
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/oscararayaoad-sys)[cite: 2]
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:oscar.araya.oad@gmail.com)[cite: 2]

**Certifications:**
- Google Advanced Data Analytics[cite: 2]
- Google Data Analytics[cite: 2]
- Data Analysis — AIEP *(in progress, 08-2026)*[cite: 2]