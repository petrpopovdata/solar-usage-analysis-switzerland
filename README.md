tgleich# ☀️ Swiss Solar Adoption: Are We Fully Tapping Municipal Potential?

## 📌 Project Background

Switzerland is ramping up its solar investments to meet national energy and climate goals — but **are all municipalities equally effective in utilizing their solar potential**?

This project uses granular data from the [**Energie Reporter**](https://opendata.swiss/en/dataset/energie-reporter) to assess:
- 📈 How much solar capacity is installed vs. actually used  
- 🗺️ Regional disparities in adoption across municipalities and cantons  
- 🚧 Where inefficiencies and untapped opportunities exist  

The insights are designed to support:
- **Federal and cantonal energy agencies**  
- **Local governments and infrastructure planners**  
- **Environmental policymakers and NGOs**

The core objective is to pinpoint **underperforming areas** and explain *why* solar usage lags — despite available infrastructure — across Switzerland’s 2,000+ municipalities over a 3-year period.

---

## 🗂️ Data Overview

### 📥 Primary Dataset

- **Source:** [Energie Reporter Switzerland](https://opendata.swiss/en/dataset/energie-reporter)  
- **License:** Creative Commons BY 4.0  
- **Period Covered:** March 2021 – March 2024  
- **Granularity:** Monthly, by Municipality  

From the original dataset — which included EV adoption, heating data, and electricity consumption — we focused on solar energy indicators. After filtering and cleaning, we retained:

| Column                    | Description                                                  |
|---------------------------|--------------------------------------------------------------|
| `energyreporter_date`     | Monthly reporting date                                        |
| `municipality`            | Municipality name                                             |
| `canton`                  | Canton code                                                  |
| `solar_potential_usage`   | Share of total solar potential currently utilized (%)         |
| `solar_power_installed_kwp` | Installed solar capacity in kilowatt-peak (kWp)             |

### 🧮 Engineered Fields (Python)

To support deeper analysis, we generated additional indicators:

| Field                         | Description                                                |
|-------------------------------|------------------------------------------------------------|
| `unused_solar_potential`      | Remaining untapped solar potential                         |
| `is_top10_as_of_mar2024`      | Flag for top 10 municipalities by solar usage (Mar 2024)   |
| `is_bottom10_as_of_mar2024`   | Flag for bottom 10 municipalities by solar usage (Mar 2024)|
| `is_high_capacity_low_usage` | Flag for high capacity, low usage municipalities           |

> ⚙️ All data preprocessing and transformation were done in **Python** using `pandas` and `geopandas`.

---

### 🌍 Supplementary Geospatial Data

To enable **map visualizations** at the canton level, we included additional spatial data:

- **Source:** [SwissBOUNDARIES3D – swisstopo](https://www.swisstopo.admin.ch/de/landschaftsmodell-swissboundaries3d)  
- **Tooling:** `GeoPandas` for extracting and computing geographic centroids  
- **Usage:** Supports canton-level bubble maps and choropleths in Tableau

---

## 🧠 Executive Summary

Switzerland is scaling up solar energy — but **not all municipalities are keeping pace**.

This data-driven portfolio project explores how 2,000+ municipalities utilize their solar potential using data from **Energie Reporter (2021–2024)**. Despite rising installed capacity, many regions show **underutilization**, **regional disparities**, and **missed efficiency opportunities**.

### 🔍 Key Findings

- ⚖️ **Installed capacity ≠ effective usage**: Many high-capacity municipalities (e.g., Bern, Lausanne) use <10% of their solar potential.
- 🏆 **Top performers punch above their weight**: Smaller municipalities like Clarmont and Curio achieve >30% usage — despite limited infrastructure.
- 📉 **Growth is real but volatile**: Solar usage is growing nationally (~2–3% monthly), though seasonal and systemic dips exist.
- 🗺️ **Regional disparities are stark**: Rural cantons like AI and AR lead usage, while urban-heavy cantons (ZH, GE, TI) lag — suggesting **policy and implementation**, not geography, drive success.
- 🎯 **Actionable targets identified**: Underperforming municipalities with high capacity and low usage are ideal candidates for focused investment, audits, or incentives.

---

## 📊 Insights Deep Dive

### 1. 🔝 Adoption Leaders and Laggards

- A long-tailed distribution reveals that the **majority of municipalities are using less than 10%** of their solar potential.
- **Over 280 municipalities** fall below the 5% usage mark, despite having installed capacity.
- **Top performers** like Onnens (VD) and Clarmont (VD) utilize over **6× the national average** (6.7%).
- The **top municipality reaches nearly 60%**, while most remain under 10%, exposing deep disparities.
- This variation occurs **within the same cantons** (e.g., VD, FR), indicating policy or implementation differences, not just geographic or solar resource limitations.
- If underperforming municipalities matched the efficiency of mid-to-top performers, **national solar usage would dramatically increase**.

**Visuals**:
- Histogram of Solar Usage (March 2024)
- Top/Bottom 10 Municipalities by Usage (Actual & Projected)

---

### 2. ⚖️ Installed Capacity ≠ Usage

- The scatterplot shows **no clear correlation** between installed solar capacity and actual usage.
- Municipalities with **very high capacity (>10,000 kWp)** often use **<10%** of it — a major sign of underutilization.
- Conversely, places like **Curio** and **Astano** achieve **40–50%+ usage** with relatively small installed capacity — highlighting operational efficiency and behavioral/policy success.
- The **upper-right quadrant (high capacity, high usage)** is sparsely populated — very few municipalities manage to **scale AND use efficiently**.
- Large cities like **Zürich, Bern, Lausanne, and Geneva** sit in the **“High Capacity, Low Usage” zone**, representing untapped opportunity.
- **Darker colors** in the scatterplot signal extreme inefficiency, visible across many cantons, notably **BE and AG**.
- Usage seems to **plateau or decline** at very high capacity levels (>25kWp), suggesting scaling challenges, poor integration, or behavioral barriers.

**Quadrant Summary**:
- **High Capacity + Low Usage = Underperformers**: Zürich, Lausanne, Bern, Geneva  
- **Low Capacity + High Usage = Efficiency Champions**: Curio, Astano, Rovray, Clarmont  
- **Low Capacity + Low Usage = Neglected Zone**: Auboranges, Andermatt, Saxeten  
- **High Capacity + High Usage = Rare (Model Scalers)**

**Visuals**:
- Installed Capacity vs Usage Scatterplot (Actual & Projected)
- Top Inefficient Cities Highlight

---

### 3. 📈 Growth Trends Over Time

- **Solar usage in Switzerland has grown steadily**, nearly **doubling over 3 years** from ~4.5% to 10.8% nationally.
- Despite **short-term volatility**, the **long-term trend is positive** — confirmed by a dotted trend line.
- **Sharp dips** (e.g., -12.8% in April 2023) are not due to data reporting gaps — verified via Python — but likely reflect **seasonal patterns, grid delays, or policy cycles**.
- Growth often rebounds quickly after dips, underscoring **resilience and continued expansion**.
- The average **monthly growth rate sits between 2–3%**, modest but consistent.
- Growth shows **no signs of saturation** — with plenty of headroom left in terms of national potential.

**Visuals**:
- Solar Potential Usage Over Time (Line)
- Monthly Growth Rate (Colored by Rate, With Trend Line)
- Reporting Count Validation (Python)

---

### 4. 🎯 Target Municipalities for Action

- Identified municipalities that combine:
  - **High Installed Capacity**
  - **Low Solar Potential Usage**
  - **Large Unused Potential**
- These areas represent **"low-hanging fruit"** for intervention: incentive redesign, behavioral nudges, or integration efforts.
- Major cities are prominent in this group, reinforcing the need for **urban strategy reform**.

**Visuals**:
- Table/List of High-Potential Municipalities
- Highlighted Map View (Bubble Color = Usage, Size = Capacity)

---

### 5. 🗺️ Regional Disparities

- **Clear usage gaps** exist between top and bottom cantons, both in actual and projected data.
- Leading cantons like **LU, AI, AR, SG, TG** consistently outperform — hitting **10–17% usage**.
- Lagging cantons — **UR, VS, GE, GR** — remain under **6%**, even in projections.
- Surprisingly, **rural cantons outperform urban ones** — showing that **urbanization does not guarantee efficiency**.
- **BE and GE**, despite large installed capacity, continue to underutilize — aligning with inefficiency seen in scatterplots.
- In projected usage, the **gap between leaders and laggards widens**, reinforcing the need for targeted interventions.
- **Regional disparities are persistent** and require **canton-level planning adjustments** — especially in **infrastructure integration and behavior programs**.

**Visuals**:
- Average Usage by Canton (Actual & Projected)
- Choropleth & Bubble Map (Color = Usage, Size = Capacity)

---

## 📌 Recommendations

While this project does not propose direct policy actions, the following data-driven insights offer **guidance to stakeholders** — including municipal planners, energy agencies, and sustainability teams — who are in a position to take action.

### 1. 🎯 Prioritize High-Capacity, Low-Usage Municipalities
- **Target municipalities** with significant installed capacity but under 10% solar usage.
- These locations represent **quick wins** — the infrastructure exists, but optimization or behavioral nudges are missing.
- Major cities like **Zürich, Geneva, Lausanne, and Bern** fall into this group and may benefit from operational audits or public engagement.

### 2. 📍 Leverage Efficiency Models from Top Performers
- **Study municipalities** such as **Curio, Onnens (VD), and Astano**, which achieve 40–60%+ usage.
- Extract operational, regulatory, or cultural patterns that could be **replicated in low-performing areas**.
- Peer comparisons within cantons (e.g., FR, VD) are particularly useful due to shared geography and solar potential.

### 3. 🧭 Focus on Cantonal Strategy Alignment
- Cantonal governments can benefit from dashboards showing **intra-canton variance**.
- This variance suggests opportunities to **standardize processes, incentives, or data flows** across municipalities within the same canton.
- Cantons like **VS, UR, GE, and GR** show consistently low usage and may require **capacity-building at the local level**.

### 4. ⚖️ Match Capacity Investment with Operational Readiness
- Avoid installing more solar capacity without ensuring **capacity is being used**.
- Use scatterplots from this analysis to guide **smarter infrastructure planning** — focusing not just on quantity but **realistic utilization**.

### 5. 📈 Monitor Volatility, but Focus on the Trend
- The monthly growth rate shows **volatility**, but long-term national usage is **steadily increasing**.
- Stakeholders should **not overreact to short-term dips**, but maintain **consistent support** aligned with the growth trend.
- Data systems should flag **structural drops** (e.g., >10% monthly declines) for diagnostic follow-up.

### 6. 🔎 Use Data-Driven Dashboards for Ongoing Monitoring
- This portfolio demonstrates how **geospatial, time-series, and categorical data** can be combined to:
  - Detect inefficiencies
  - Compare regional performance
  - Forecast solar usage potential
- Stakeholders can extend this approach by integrating **real-time data** and **energy consumption overlays** for deeper impact.

---

> These recommendations are derived purely from exploratory data analysis and visualization. Final action should be informed by additional context, domain expertise, and stakeholder collaboration.
---

## ⚠️ Caveats & Assumptions

### 📊 Data-Related Caveats

- **Historicization of Data**:  
  The dataset is a **"historicized" version** of municipality-level indicators from Energie Reporter. Each month's data reflects the status as of that reporting date — this assumes accuracy and continuity in the source.

- **Limited Scope of Variables**:  
  We focused exclusively on solar-relevant variables:
  - `solar_power_installed_kwp`
  - `solar_potential_usage`
  
  Other potentially important columns (e.g., electric car share, heating, wind energy) were excluded for scope clarity — this **limits holistic energy analysis**.

- **One Outlier Removed**:  
  One municipality — **Chapelle (Glâne)** — reported **solar potential usage above 100%**, which is likely due to reporting or calculation error. It was **excluded** from the final analysis.

- **Projection Assumptions**:  
  We distinguish between:
  - Actual data (up to March 2024)
  - Forward projections (post-March 2024)

  All projections assume **continuity of existing trends** and **no external disruptions** (e.g., policy shifts, climate anomalies, grid infrastructure changes).

### 📉 Analytical Assumptions

- **Solar Potential Usage (%) as a Proxy for Efficiency**:  
  We're interpreting `solar_potential_usage` as a measure of how efficiently each municipality uses its capacity. This **does not account for local constraints**, such as:
  - grid saturation
  - shading from mountains
  - building orientation

- **"Low Usage" Defined Arbitrarily**:  
  Thresholds for categories (e.g., "Very Low" <5%) are based on **visual clustering** and are not standardized by national benchmarks.

- **No Weather or Irradiance Control**:  
  This analysis does not account for **solar irradiance differences** across Switzerland (e.g., alpine vs. plateau regions). Solar usage % is interpreted without correcting for expected yield variation.

- **Temporal Trends Assume Constant Reporting**:  
  Missing months, lags, or changes in Energie Reporter’s methodology are not adjusted for — **monthly growth rates** may reflect reporting artifacts.

## 🔗 Deliverables

- 📈 [Interactive Tableau Dashboard](https://public.tableau.com/views/SolarUsageAnalysisSwitzerland/SwissSolarPotentialDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link) *(hosted on Tableau Public)*  
- 🐍 [Python EDA + Data Cleaning Notebook](swiss-solar-final.ipynb) *(GitHub repo)*  
- 📁 [Cleaned CSV File](solar_municipality_unified1.csv) *(optional link)*  

---

## ✅ Skills Demonstrated

- 📊 Data storytelling & dashboarding (Tableau)
- 🐍 Data wrangling & feature creation (Python)
- 📈 Trend & forecast analysis
- 💬 Executive-level insights & recommendations
- 🧠 Stakeholder framing

---
