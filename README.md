# 🌍 World Bank Data Analysis

> Web scraping, cleaning, descriptive statistics, and visualization of GDP, Population, Literacy, and CO₂ data from the World Bank API.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/harshithabt/World-Bank-Data-Analysis/blob/main/WorldBank_DataAnalysis.ipynb)
![Language](https://img.shields.io/badge/Language-Python-blue?style=flat-square)
![Topic](https://img.shields.io/badge/Topic-Data%20Analysis-green?style=flat-square)
![Data](https://img.shields.io/badge/Data-World%20Bank%20API-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-purple?style=flat-square)

---

## Overview

This project fetches four World Bank indicators across all countries from 1960–2024, cleans and preprocesses the data, computes descriptive statistics and growth rates, and produces visualizations with inferences.

**Workflow:**
```
Web Scraping → Data Cleaning → Descriptive Statistics → Visualization → Inferences
```

---

## Datasets

| # | Indicator | Code | Description |
|---|-----------|------|-------------|
| 1 | GDP (current US$) | `NY.GDP.MKTP.CD` | Gross Domestic Product at current prices |
| 2 | Population, total | `SP.POP.TOTL` | Total population per country |
| 3 | Literacy rate (adult %) | `SE.ADT.LITR.ZS` | % of people aged 15+ who can read and write |
| 4 | CO₂ emissions (metric tons per capita) | `EN.ATM.CO2E.PC` | CO₂ emissions divided by midyear population |

**Source:** [World Bank Open Data](https://data.worldbank.org)

---

## Key Findings

| Indicator | Key Finding |
|-----------|-------------|
| **GDP** | Highly right-skewed; China surged sharply post-1990s; USA remains highest |
| **Population** | India and China are extreme outliers; India surpassed China around 2023 |
| **Literacy** | Global improvement trend; India grew from ~40% (1980) to ~75%+ (2020) |
| **CO₂/capita** | USA historically highest (~15–20 tons); India lowest (~2 tons); China rising fast post-2000 |

---

## Visualizations

Each indicator has three plots:

| Plot | Purpose |
|------|---------|
| Histogram | Distribution of values across all countries and years |
| Boxplot | Spread, median, and outliers |
| Line plot | Trend over time for India, China, and United States |

---

## Project Structure

```
World-Bank-Data-Analysis/
│
├── WorldBank_DataAnalysis.ipynb   # Main notebook (run on Colab)
├── requirements.txt               # Python dependencies
├── README.md                      # This file
├── LICENSE                        # MIT License
│
└── plots/                         # Generated visualization outputs
    ├── gdp_hist.png
    ├── gdp_box.png
    ├── gdp_line.png
    ├── population_hist.png
    ├── population_box.png
    ├── population_line.png
    ├── literacy_hist.png
    ├── literacy_box.png
    ├── literacy_line.png
    ├── CO2_hist.png
    ├── CO2_box.png
    └── CO2_line.png
```

---

## How to Run

### Option 1 — Through Google Colab (Recommended)
Click the **Open in Colab** badge above, then `Runtime → Run all`.

### Option 2 — or Local
```bash
git clone https://github.com/harshithabt/World-Bank-Data-Analysis.git
cd World-Bank-Data-Analysis
pip install -r requirements.txt
jupyter notebook WorldBank_DataAnalysis.ipynb
```

---

## Requirements

```
pandas
matplotlib
seaborn
numpy
requests
beautifulsoup4
```

---

## Data Fixes & Notes

- **CO₂ indicator:** Uses `EN.ATM.CO2E.PC` (per capita) — not total emissions. Values filtered to valid range 0–50 metric tons/capita.
- **Aggregate regions:** World Bank regional aggregates (e.g. `WLD`, `HIC`, `EAP`) are removed to keep only individual countries.
- **US literacy:** The World Bank does not consistently track US literacy (assumed ~99% through domestic surveys) — this is annotated in the plot.
- **Year column:** The `Unnamed: 69` column from raw World Bank CSVs is dropped during cleaning.

---

## Inferences

**GDP:** Distribution is highly right-skewed — most countries have small GDPs while USA and China dominate. China's sharp rise post-1990s reflects its economic reforms and export growth.

**Population:** India and China are extreme outliers. India surpassed China as the world's most populous country around 2023. US growth is slow and linear.

**Literacy:** Global literacy has improved dramatically since 1960. India grew from ~40% to 75%+, China from ~65% to ~97%. Outliers below 40% are concentrated in Sub-Saharan Africa.

**CO₂:** Most countries emit under 5 tons per capita. USA consistently high at 15–20 tons. China rising rapidly post-2000 (~8 tons). India remains low (~2 tons) — its per-capita footprint is far below developed nations despite being a large economy.

---

*Data sourced from [World Bank Open Data](https://data.worldbank.org) — free and open access.*

---
