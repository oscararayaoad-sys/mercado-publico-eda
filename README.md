# Public Spending Analysis in Chile's Mercado Público

**How and where does the Chilean State spend through Mercado Público, and where are the best opportunities for a supplier?**

Exploratory Data Analysis (EDA) of ~1.1 million public purchase orders from the first quarter of 2026, focused on a concrete business question: identifying spending patterns, geographic concentration, and accessible market niches for a supplier looking to enter public procurement.

> 🛠️ **Stack:** Python · pandas · NumPy · Matplotlib · Seaborn · Jupyter  
> 📊 **Type:** Exploratory Data Analysis (EDA) with a business focus  
> 🗂️ **Source:** Mercado Público Open Data (ChileCompra)

---

## 🎯 The Question

The State of Chile buys goods and services worth trillions of pesos annually through Mercado Público. For a supplier wanting to sell to the State, the key question is: **where is it worth entering?** This project breaks that question down into three dimensions:

1. **How does the State spend?** — concentrated or distributed?
2. **Where does it spend?** — distribution by region, sector, and category.
3. **What opportunities exist?** — niches with high spending and low competition.

---

## 💡 Key Findings

**1. Spending is concentrated at the head and distributed in the tail.**  
The two largest agencies (JUNAEB and CENABAST) account for about **30%** of total spending, and the top 10 reach **~42%**. The vast majority of orders are small; a small group of large orders accumulates the bulk of the money.

**2. The Metropolitan Region dominates geographically.**  
The RM concentrates **~62%** of spending. The top 5 regions reach **~81%**. Geographic concentration is much stronger than concentration by category.

**3. Spending by sector is distributed, not concentrated.**  
The top 10 sectors barely reach **~74%** of spending — the 80% threshold is only reached near the top 14. This indicates a broad market with multiple opportunities rather than a single dominant sector.

**4. "Few suppliers" does NOT mean opportunity.**  
The most counterintuitive finding: high-spending niches with few suppliers turned out to be **captive markets** (nuclear equipment, radiotherapy, radioisotopes), with a leading supplier capturing over **90%** of spending — high barriers to entry, not opportunities. Real opportunities lie in high-spending markets with medium competition and a weak leader (<50%): medical diagnostics, advertising, forestry machinery.

---

## 🔍 Key Technical Decisions

Beyond the results, the project documents the reasoning process. Some decisions showcasing the applied criteria:

- **Data Granularity.** Each row represents an item, not an order. Line-level amounts (`totalLineaNeto`) were distinguished from total order amounts (`MontoTotalOC`, which repeats on every line) to avoid inflating totals via double counting.
- **Monetary Column Reconciliation.** The ~2x gap between both columns was investigated and found to be **VAT** (order = gross, line = net), not a data error. Validated by inspecting individual orders.
- **Real Data Cleaning.** `Latin-1` encoding, `;` separator, Chilean decimal comma (`1.234,56`), and currency verification (99.4% CLP) prior to aggregation.
- **Entity Normalization.** Regions arrived with **32 different labels for 16 real regions** (invisible spaces, glyph variants, short vs. long names). These were consolidated using Unicode normalization and keyword matching.
- **Concentration Metric.** An indicator (`pct_lider`: % of spending captured by the leading supplier) was built to distinguish open markets from captive ones — the key to answering the opportunity question.
- **Data Quality.** Unclassified records (10.6%) were investigated by proportion, not count: the pattern turned out to be a capture failure in local public education services (100% unclassified) and partial opacity in a security agency (Gendarmería, 61%), rather than general confidentiality.
- **Working Discipline.** *"Diagnose before fixing"*: every anomaly was verified with raw data before applying a correction, avoiding fixing ghosts.
- **Classification Hierarchy.** `RubroN1` is the parent category and `Categoria` is its subdivision (one sector groups several categories). Therefore, spending is more concentrated when grouping by sector than by category: the same money is spread across more buckets at a lower level. Both dimensions are analyzed separately to avoid confusing the aggregation level.

---

## 📈 Visualizations

### Interactive Dashboard (Power BI)

![Public spending dashboard in Power BI](assets/dashboard_powerbi.png)  
*Interactive dashboard built in Power BI: total spending, top 10 agencies, regional distribution on a map, and sector filter. When selecting a sector, all visuals recalculate in real time.*

**Spending by Agency — Head Concentration**  
![Spending concentration by agency](assets/concentración_de_gasto_por_organismo.png)  
*JUNAEB and CENABAST lead spending, together concentrating about 30%. The curve flattens quickly: few agencies account for a disproportionate share, with a long tail of hundreds of smaller buyers.*

**Spending by Category — Distributed**  
![Spending concentration by category](assets/concentración_de_gasto_por_categoría.png)  
*No single category dominates. The cumulative 80% is not even reached within the top 15, signaling a broad market with multiple fronts of opportunity.*

**Spending by Region — Strong Geographic Concentration**  
![Spending concentration by region](assets/concentración_de_gasto_por_región.png)  
*The Metropolitan Region concentrates ~62% of spending. The cumulative 80% is reached only in the top 5: public spending is geographically concentrated, unlike its sectoral distribution.*

**Spending by Sector — Distributed**  
![Spending concentration by sector](assets/concentración_de_gasto_por_rubro.png)  
*Spending by sector is spread across many industries; the cumulative 80% is only reached near the top 14, confirming an open market.*

---

## 💡 Key Findings

**1. Spending is heavily concentrated at the top.**  
The **Top 10 agencies** account for **84.1%** of total spending, led individually by **CONAF** (19.5%). While transactions are massively fragmented at the operational level (median value of $919.16K CLP), total spending is driven by high-value mega-transactions.

**2. Extreme centralization in the Metropolitan Region.**  
The **Metropolitan Region** absorbs **96.7%** of recorded spending ($66.82 Quadrillion CLP), heavily influenced by corporate headquarters and ministerial billing biases, leaving only 3.3% distributed across the remaining 15 regions.

**3. Sectoral spending is led by IT and Transportation.**  
**Information Technology (IT)** leads spending by industry with **42.8%**, while **Transportation & Logistics** is the top single category by volume at **19.2%** ($13.17 Quadrillion CLP). The top 5 sectors concentrate 93.7% of the overall budget.

**4. High spend with few suppliers often signals a closed market.**  
High-spending sectors with very few suppliers usually represent **captive markets or oligopolies** (e.g., Financial Services, Mining Machinery) with extreme entry barriers. Real opportunities lie in **open/dynamic niches** with high transaction flow and distributed liquidity, such as *Transportation & Storage* ($140.09T/supplier) and *IT & Telecommunications*.

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

> Data is not included due to size; it is publicly downloadable from the Mercado Público (ChileCompra) open data portal.

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
Data Analyst · Santiago, Chile 🇨🇱

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/oscar-araya-diaz-7a418a170)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/oscararayaoad-sys)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:oscar.araya.oad@gmail.com)

**Certifications:**
- Google Advanced Data Analytics
- Google Data Analytics
- Data Analysis — AIEP *(in progress, 08-2026)*
