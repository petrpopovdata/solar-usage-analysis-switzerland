# ☀️ Swiss Solar Adoption: Are We Fully Tapping Municipal Potential?

## 📌 Project Background

Switzerland is investing heavily in solar energy to meet its climate goals — but are all municipalities utilizing their solar potential equally?

This analysis uses municipality-level energy data from **Energie Reporter** to explore:
- Solar capacity and actual usage
- Regional disparities across Switzerland
- Untapped opportunities for investment or policy focus

This project delivers insights relevant to:
- **Federal and cantonal energy agencies**
- **Local governments and infrastructure planners**
- **Environmental policymakers and NGOs**

Data spans over 3 years across 2,000+ municipalities. The focus is to identify where solar investments are underperforming — and why.

---

## 🗂️ Data Overview

**Source:** [Energie Reporter Switzerland](https://opendata.swiss/en/dataset/energie-reporter)  
**License:** Creative Commons BY 4.0  
**Time Period:** March 2021 – March 2024  
**Granularity:** Monthly, by Municipality

The analysis uses the **historicized municipality dataset** with these key columns:

| Column                      | Description                                                |
|-----------------------------|------------------------------------------------------------|
| `municipality`              | Municipality name                                          |
| `canton`                    | Canton code                                                |
| `energyreporter_date`       | Reporting date (monthly)                                   |
| `solar_power_installed_kwp` | Installed solar capacity (kilowatt‑peak)                   |
| `solar_potential_usage`     | Percentage of total solar potential currently utilized     |

All other columns (e.g., EV, heating) were excluded from this solar‑focused analysis.

> Data was cleaned and pre-processed in Python. Final dataset and visualizations were developed in Tableau.

---

## 🧠 Executive Summary

As of **March 2024**:

- 🌤️ **National average solar usage is 7% (as of March 2024)**, rising from 4.3% in 2021.
- 🏘️ **289 out of 2184 municipalities (13.2%) use less than 5% of their solar potential**, even with installed infrastructure.
- 🏅 **Top-performing municipalities** exceed 40% usage, often clustered within certain cantons like Ticino (TI), and Vaud (VD).
- 🔍 Despite having the highest levels of installed solar capacity, major Swiss cities like Zürich, Bern, and Lausanne are utilizing less than 5% of their solar potential.
- 📈 If current trends hold, national usage is projected to reach **~10% by mid-2025**.

---

## 📊 Insights Deep Dive

### 1. 🔝 Adoption Leaders and Laggards
- Histogram reveals a **long tail**: most municipalities are underperforming.
- Leading municipalities like Onnens (VD) and Clarmont (VD) have solar potential usage rates over 6× the national average.
- The national average stands at 6.7%, while the top municipality exceeds 40% — highlighting significant geographic disparities.
- Most others are still far below the national average — signaling room for growth and replication of best practices.
- If more municipalities matched even the mid-tier performers, national solar usage could grow substantially.
- Municipalities in similar cantons (e.g., VD and FR) show variable performance, indicating that policy, not geography, may be the key driver.
- Outperformers often share regional or infrastructure characteristics.

> Visuals:
- *Histogram of Solar Usage (Mar 2024)*
- *Top 10 Municipalities by Usage*

---

### 2. ⚖️ Installed Capacity ≠ Usage
- There's no strong linear correlation between installed capacity (kWp) and actual usage (%).
- Some municipalities with very high capacity (>10,000 kWp) still have very low usage (<10%), indicating underutilization.
- There’s a dense cluster of municipalities with moderate capacity and low usage (bottom-right quadrant).This suggests structural inefficiencies or policy/implementation issues.
- High-capacity, low-usage municipalities may have invested in infrastructure without ensuring uptake, integration, or behavior change.
- Municipalities with low installed capacity but high usage (Curio, Astano) are potentially model cases of efficiency. These municipalities make the most out of limited resources — ideal for best practice case studies.
- As installed capacity increases beyond a threshold (e.g., 15k–20k kWp), usage stagnates or drops. This may imply scale-related inefficiencies, lack of grid integration, or oversizing without uptake.
- Darker shades (pink/purple) indicate extreme inefficiency — useful to pinpoint which municipalities to audit or support.
- Color distribution also shows inefficiency is widespread across cantons, not just isolated.
- Cantons BE and AG appear to have a disproportionately high number of municipalities with underutilized solar capacity — indicating regional opportunity for better solar adoption initiatives or more efficient usage.
- Municipalities with low installed capacity but high usage (Curio, Astano, Rovray, Clarmont) are potentially model cases of efficiency. These municipalities make the most out of limited resources — ideal for best practice case studies.
- Upper-right quadrant (high capacity & high usage) is nearly empty, suggesting very few municipalities are both scaling and utilizing effectively.
- Lower-left quadrant is densely populated — showing a long tail of low-capacity, low-usage municipalities, which may represent areas with either limited funding or weak policy engagement.
- Opportunity zone: Mid-capacity + mid-usage municipalities might be the most scalable targets — they have infrastructure and moderate performance, suggesting room for improvement.
- High Capacity + Low Usage = "Underperformers": Zürich, Bern, Lausanne, Basel, Bellinzona
- Low Capacity + High Usage = "Efficiency Champions": Curio, Astano, Rovray, Clarmont
- High Capacity + High Usage = "Model Scalers": No
- Low Capacity + Low Usage = "Neglected Zone": Auboranges, Andermatt, Saxeten.
- At very high installed capacity (>25kW or >40kW), solar usage plateaus or drops. This is critical for national investment planning: don’t just install more; ensure it's used well.

> Visuals:
- *Installed Capacity vs Usage Scatterplot*
- *Filter: Canton / High Unused Potential*

---

### 3. 📈 Growth Trends Over Time
- Steady upward trend from 2021 to 2024.
- Growth has **slowed slightly** in recent quarters.
- Forecast suggests **~25% usage by Q2 2025** if unchanged.

> Visuals:
- *Line Chart: Average Usage Over Time (with Forecast)*
- *Monthly Growth Rate Line*

---

### 4. 🎯 Target Municipalities for Action
- Identified municipalities with:
  - High installed capacity
  - Low usage %
  - High unused potential
- These are prime candidates for incentives, policy, or technical support.

> Visuals:
- *Filterable List/Table: High-Potential Municipalities*
- *(Optional)* *Map View: Solar Opportunity Hotspots*

---

### 5. 🗺️ Regional Disparities
- **Canton averages vary widely** (10–30% usage).
- Some rural areas outperform urban ones.
- Opportunity to examine **policy/zoning influences**.

> Visuals:
- *Average Usage by Canton*
- *(Add)* *Choropleth Map by Municipality*

---

## 📌 Recommendations

1. **Target Underperforming Municipalities**  
   Focus incentives or education programs where capacity is high, but usage is low.

2. **Replicate Best Practices**  
   Study top-performing municipalities to replicate success in similar regions.

3. **Monitor Usage, Not Just Capacity**  
   Set performance goals based on actual utilization, not just installations.

4. **Enable Self-Service Benchmarking**  
   Build dashboards for municipalities to compare performance and track progress.

---

## ⚠️ Caveats & Assumptions

- `solar_potential_usage` is calculated as a basic ratio — does not account for weather, shading, or roof orientation.
- Forecasts are based on historical exponential smoothing, **not ML**.
- **No demographic or economic data** included in this version.
- Some solar capacity installation timestamps may lag actual project completion.
- **Data Cutoff**: Values after March 2024 were excluded as projections. Our analysis focuses on actual data through March 2023.
- **Outliers**: One record (Chapelle (Glâne)) reported >100% usage; this was capped at 100% for visualization.
- **Projected Data**: Entries beyond last update (Mar 2024) likely represent forecasts or estimates—not measured values.
- **Temporal Gaps**: Use of rolling averages causes minor delays in trend lines immediately after cutoffs.
- **Municipality Aggregation**: National trends sum municipalities assuming no overlaps.
- **No External Validation**: Data taken at face value without cross‑referencing federal statistics.

---

## 🔗 Deliverables

- 📈 [Interactive Tableau Dashboard](#) *(hosted on Tableau Public)*  
- 🐍 [Python EDA + Data Cleaning Notebook](#) *(GitHub repo)*  
- 📁 [Cleaned CSV File](#) *(optional link)*  

---

## ✅ Skills Demonstrated

- 📊 Data storytelling & dashboarding (Tableau)
- 🐍 Data wrangling & feature creation (Python)
- 📈 Trend & forecast analysis
- 💬 Executive-level insights & recommendations
- 🧠 Stakeholder framing

---

## ✍️ Interview Summary

> “This project simulates a real-world analysis for federal and local policymakers. I identified underused solar resources in Switzerland using a mix of trend analysis, benchmarking, and forecast modeling. I approached it as if I were on a cross-functional energy planning team, delivering insights and action points, not just charts.”

---
