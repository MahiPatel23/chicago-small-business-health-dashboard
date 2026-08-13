# Chicago Small Business Health Dashboard (2025)

An interactive Power BI dashboard analyzing small business closures across Chicago wards in 2025, built to answer: **which neighborhoods are losing businesses, and why?**

![Dashboard screenshot](dashboard-screenshot.png)

## Key Finding

Debt collection and select retail categories show the highest closure rates in 2025. Food safety violations show no meaningful link to closure — closed businesses actually had a slightly *lower* failed-inspection rate (13.2%) than active ones (17.7%), suggesting closures are driven more by business category and location than food safety issues.

## Data Sources

All data pulled live from the Chicago Open Data Portal:
- [Business Licenses](https://data.cityofchicago.org/resource/r5kz-chrr.json)
- [Food Inspections](https://data.cityofchicago.org/resource/4ijn-s7e5.json)
- [Ward Boundaries](https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Wards-2023-/p293-wvbd)

Scope: all 2025 license and inspection records (~35,000 businesses).

## Methodology

**Defining a "closure"** was the core analytical decision in this project, since Chicago doesn't publish a dedicated closures dataset. A business is flagged as closed when:
- Its license status changes to **Cancelled (AAC)** or **Revoked (REV)**, **and**
- That status change is not tied to a **Change of Location (C_LOC)** application — since a business relocating isn't a closure.

This stricter definition avoids overcounting businesses that simply moved addresses.

## Dashboard Components

1. **Ward-level closure rate map** — geographic view of where closures are concentrated
2. **KPI cards** — total businesses, total closures, overall closure rate
3. **Monthly closure trend** — closures by month across 2025
4. **Closure rate by business category** — which types of businesses are closing most
5. **Food inspection comparison** — failed inspection rate, active vs. closed businesses

## Tools

Power BI Desktop (Power Query for ETL, DAX for measures, Shape Map for geographic visualization)

## File

`business-health-dashboard.pbix` — open in Power BI Desktop to explore interactively.
