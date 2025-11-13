# Renewable-Energy-Permits-Analytics
**Interactive analytics & API for Renewable Energy Permits in Greece**

---

## Project Overview  
This repository provides a full-stack analytics solution for renewable energy permits in Greece.  
- We obtained raw permit data from the official portal of the Regulatory Authority for Energy (RAE) for small and large scale projects.  
- The data is cleaned, transformed and visualised via a web GUI built with Streamlit, and exposed as a RESTful API.  
- Purpose: to support policymakers, researchers, and energy-market stakeholders with **exploratory insights**, **regional summaries**, and **real time data access** via Docker-containerised deployment.

---

## Why it matters  
Greece’s energy transition relies on effective monitoring of renewable energy deployment. This project:  
- Enables transparent tracking of permits by region, technology, and time.  
- Helps identify bottlenecks or delays in the permitting pipeline.  
- Supports data-driven decision making via visual dashboards and easily accessible endpoints.

---

## Live Demo  
Explore the interactive app: [RAE Insights on Streamlit](https://rae-insights.streamlit.app/)  
*(Consider removing the lengthy fbclid parameter once stable.)*

Here are a couple of key views:  
<!-- Suggest adding screenshots: e.g. “permit_time_series.png”, “regional_heatmap.png” -->
![Time Series of Permits over Time](assets/time_series_permits.png)  
*Fig 1 – Cumulative number of permits by technology over time.*

![Greek Regional Map of Permits](assets/greece_regional_map.png)  
*Fig 2 – Heatmap by Regional Unit for number of permits approved.*

> You can place such screenshots in an `assets/` directory and reference them like above.

---

## Architecture & Components  
| Component        | Purpose                                                       | Location                        |
|------------------|---------------------------------------------------------------|---------------------------------|
| Data Pre-processing | Download raw CSVs, cleaning, mapping regional units & technologies | `preprocess_data.py`            |
| Data Loader/API   | Load cleaned data, expose endpoints for external use          | `api/` directory                |
| Web GUI (Streamlit) | Interactive dashboards & charts powered by cleaned data       | `app.py`, `visualizations.py`   |
| Docker Setup      | Containerisation for reproducible deployment                  | `docker-compose.yml`, `Dockerfile` |
| Mapping Module    | Greek regional-unit geometry & plotting                        | `greece_map.py`                 |

---

## Getting Started (Local)  
**Prerequisites:** Docker (or Python 3.8+ with dependencies).  
```bash
git clone https://github.com/SophiaVei/Renewable-Energy-Permits-Analytics.git  
cd Renewable-Energy-Permits-Analytics  


Note: the same plots created for Streamlit in this repo were later deployed on: [RES Market Monitor](https://trineflex.csd.auth.gr/energy-actors-observatory/res-monitor/data-analysis)
