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
