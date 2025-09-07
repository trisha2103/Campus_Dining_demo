# Campus Dining — Sales & Discount Optimization (Personal Project)

**Personal, end-to-end data engineering project** exploring how a campus dining team could use external signals (weather, events, calendar) to **recommend student discounts that increase expected margin** on low-demand days.

> **Note:** This repository is for learning/portfolio purposes only. **No real or private data is included.** All figures in screenshots and the PBIX are **simulated/expected**, not actual sales.

---

## Quick look


<p align="center">
  <img src="./Overview%20page.png" width="900" alt="Overview"/>
</p>
<p align="center">
  <img src="./Daily%20planner%20page.png" width="900" alt="Daily Planner"/>
</p>
<p align="center">
  <img src="./Curve%20Explorer%20page.png" width="900" alt="Curve Explorer"/>
</p>

---

## What this project demonstrates

- **Medallion architecture** on Microsoft Fabric Lakehouse (Delta): **Bronze → Silver → Gold**
- **Feature engineering** from public signals (weather, athletics ICS, academic calendar)
- **Scenario modeling** (0–30% discount) to compute **Expected Covers / Revenue / Margin**
- **Policy guardrails** (recommend only on low-demand days, respect closures/weekends, minimum lift)
- **Power BI** report with KPIs, “why/why not” breakdown, planner matrix, and margin curve

---

## Stack

- **Microsoft Fabric** (Lakehouse, Notebooks, Delta)
- **Python** (pandas, numpy)
- **Power BI** (PBIX; semantic model over gold exports)

---

## Repository contents

- notebooks/
- Campus_dining.ipynb # Bronze → Silver → Gold + recommendations (simulated)
- powerbi/
- Campus Dining_Sales & Discount_Report.pbix
- assets/screens/
- Overview page.png
- Daily planner page.png
- Curve Explorer page.png
- Semantic_model.png
- Workspace.png

  
> The PBIX and screenshots are included to show the end result; raw datasets are **not** checked in.

---

## Data & assumptions

- **No real POS data.** Demand/covers are **simulated** (Poisson) using engineered features and conservative priors.
- External inputs referenced (not included):
  - **Weather:** Open-Meteo ERA5 (daily max/min temp, precipitation)
  - **Athletics calendars:** public ICS downloads per sport
  - **Academic calendar:** Registrar PDF dates
- Ops inputs (dining hours, class blocks) are **assumed** for modeling only.

---

## How to view

- Open `powerbi/Campus Dining_Sales & Discount_Report.pbix` in **Power BI Desktop** to explore the model/report structure.
- Use the screenshots in `assets/screens/` for a quick tour if you’re not on Power BI Desktop.


---

## License

MIT — see `LICENSE`.
