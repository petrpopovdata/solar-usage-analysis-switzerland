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

| Column                         | Description                                               |
|-------------------------------|-----------------------------------------------------------|
| `municipality`                | Name of the municipality                                  |
| `canton`                      | Canton the municipality belongs to                        |
| `energyreporter_date`         | Reporting date (monthly)                                  |
| `solar_power_installed_kwp`   | Installed solar capacity (kilowatt-peak)                  |
| `solar_potential_usage`       | % of total solar potential currently being utilized       |

---

## 📈 Executive Summary

Between March 2021 and March 2023, **average solar potential usage** across Swiss municipalities increased by **X percentage points** _(placeholder)_, reflecting steady progress in solar adoption.

Key highlights:

- **Top-performing municipalities** reached over **YY%** solar utilization.
- Over **40%** of municipalities still use **less than 25%** of their solar potential.
- **Installed solar capacity** grew by **ZZ%** nationally during this period.

These findings suggest strong momentum overall but signal a need for **targeted interventions** in underperforming regions.

---

## 🔍 Insights Deep Dive

### 1. 📈 Growth Over Time

- National average `solar_potential_usage` rose from **A%** (Mar 2021) to **B%** (Mar 2023).
- Growth was steady, with a noticeable acceleration during mid-2022 — potentially driven by policy changes or rising energy prices.

---

### 2. 🏆 Top vs. Bottom Performers _(as of Mar 2023)_

**Top 5 Municipalities by Solar Usage**

| Municipality | Usage % |
|--------------|---------|
| Muni 1       | 78.2%   |
| Muni 2       | 74.5%   |
| Muni 3       | ...     |

**Bottom 5 Municipalities by Solar Usage**

| Municipality | Usage % |
|--------------|---------|
| Muni A       | 6.1%    |
| Muni B       | 5.3%    |
| Muni C       | ...     |

---

### 3. 🧭 Underutilized High-Potential Areas

Some municipalities show **high installed capacity** but relatively **low usage rates**, suggesting that **untapped solar potential remains substantial**.

- **Urban municipalities** tend to show higher utilization
- **Rural areas** display greater variability and potential for improvement

---

## 💡 Recommendations

### 🎯 Targeted Incentives in Low-Usage Municipalities
Municipalities with usage below 20% and moderate-to-high installed capacity may benefit from **local outreach**, **funding programs**, or **grid upgrades**.

### 📈 Policy Support for Medium Performers
Municipalities in the 30–50% range show clear momentum — continued incentives could help them reach full potential.

### 🔁 Benchmarking for Underperformers
Encourage **knowledge sharing** from top-performing municipalities on:
- Streamlined permitting
- Awareness campaigns
- Community engagement strategies

---

## ⚠️ Caveats & Assumptions

- `solar_potential_usage` assumes accurate estimates of technical solar potential. Actual conditions (e.g. weather, building renovations) may vary.
- Very small municipalities may skew % changes due to low absolute values.
- Some reporting periods may be **missing or delayed**, especially in early 2023.
- Installed capacity (`kwp`) does **not represent actual energy generation** — this analysis focuses on **capacity potential**.

---
