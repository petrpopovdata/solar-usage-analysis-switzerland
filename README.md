# 🌞 Solar Potential Utilization in Swiss Municipalities  
*An Analytical Look at Solar Power Usage Across Switzerland (2021–2023)*

---

## 📘 Background & Overview

Switzerland has made strong commitments toward sustainable energy, with **solar power positioned as a key pillar** of the national energy transition. Each municipality has a defined solar potential based on:

- Rooftop availability  
- Building orientation  
- Local climate conditions  

Yet, **actual utilization varies widely**.

This project analyzes the extent to which municipalities are utilizing their available solar capacity between **March 2021 and March 2023**. We examine:

- Growth trends over time  
- Leading and lagging municipalities  
- Recommendations to unlock unused capacity  

📊 The data is sourced from [Energie Reporter](https://opendata.swiss/en/dataset/energie-reporter) and reflects **monthly progress in solar power installation and potential usage** at the municipality level.

---

## 🧱 Data Structure Overview

The analysis is based on the **historicized municipality dataset**, which includes:

The analysis uses the **historicized municipality dataset** with these key columns:

| Column                      | Description                                                |
|-----------------------------|------------------------------------------------------------|
| `municipality`              | Municipality name                                          |
| `canton`                    | Canton code                                                |
| `energyreporter_date`       | Reporting date (monthly)                                   |
| `solar_power_installed_kwp` | Installed solar capacity (kilowatt‑peak)                   |
| `solar_potential_usage`     | Percentage of total solar potential currently utilized     |

All other columns (e.g., EV, heating) were excluded from this solar‑focused analysis.

---

## 📈 Executive Summary
- **Average utilization** rose from **4.3% in March 2021** to **7.0% in March 2023** — a **2.7 percentage point** increase.
- **Top performers** like Onnens (VD) reached nearly **60%** utilization, demonstrating best‑in‑class local adoption.
- **Over 40%** of municipalities use **less than 7%** of their solar potential, indicating substantial untapped capacity.

While national momentum is positive, many regions lag behind, highlighting the need for targeted incentives and policy support.

---

## 🔍 Insights Deep Dive

### 1. Growth Over Time
- National average usage increased steadily from **4.3% → 7.0%**.
- Seasonal dips (winter months) and reporting lags cause short-term fluctuations.
- Trajectory suggests sustained but moderate growth (~21% relative increase over two years).

### 2. Top vs. Bottom Performers (as of Mar 2023)

**Top 5 Municipalities by Solar Usage**

| Municipality      | Usage %  |
|-------------------|---------:|
| Onnens (VD)       | 58.7%    |
| Clarmont (VD)     | 34.2%    |
| Cressier (NE)     | 32.8%    |
| Sévaz (FR)        | 31.5%    |
| Essert‑FR         | 30.1%    |

**Bottom 5 Municipalities by Solar Usage**

| Municipality      | Usage %  |
|-------------------|---------:|
| Zwischbergen (VS) | 0.0%     |
| Bedretto (TI)     | 0.0%     |
| Simplon (VS)      | 0.0%     |
| Rovio (TI)        | 0.05%    |
| Silvaplana (GR)   | 0.08%    |

Top municipalities illustrate best practices and supportive local policies. Bottom performers—often remote alpine regions—face infrastructure and climatic barriers.

### 3. Underutilized High‑Potential Areas
- **Large urban centers** (e.g., Zürich, Bern, Geneva) have **>10 MW installed** but utilization below **5%**.
- These municipalities represent significant opportunities: increasing usage by just 1% could unlock **100 kWp+** of additional capacity nationally.

---

## 💡 Recommendations
1. **Targeted Incentives for Low‑Usage Areas**
   - Offer subsidies or financing programs in municipalities with <7% usage and moderate‑to‑high installed capacity.
2. **Policy Support for Medium Performers**
   - Municipalities in the 20–40% usage range could benefit from streamlined permitting and awareness campaigns to push toward full potential.
3. **Benchmarking & Knowledge Sharing**
   - Share case studies from top performers (e.g., Onnens) on community engagement and installation best practices.

---

## ⚠️ Caveats & Assumptions
- **Data Cutoff**: Values after March 2024 were excluded as projections. Our analysis focuses on actual data through March 2023.
- **Outliers**: One record (Chapelle (Glâne)) reported >100% usage; this was capped at 100% for visualization.
- **Projected Data**: Entries beyond last update (Mar 2024) likely represent forecasts or estimates—not measured values.
- **Temporal Gaps**: Use of rolling averages causes minor delays in trend lines immediately after cutoffs.
- **Municipality Aggregation**: National trends sum municipalities assuming no overlaps.
- **No External Validation**: Data taken at face value without cross‑referencing federal statistics.

---

## 📂 Getting Started
1. **Run** `solar_usage_analysis.py` to generate `data/solar_municipality_unified.csv`.
2. **Open** the CSV in Tableau.
3. **Use** boolean flags (`is_top10_as_of_mar2024`, `is_bottom10_as_of_mar2024`, `is_high_capacity_low_usage`) to filter and highlight.
4. **Recreate** or extend the charts provided.

For questions or further collaboration, see the notebook or contact the author.
