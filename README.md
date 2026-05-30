# 🏙️ Current Urban Planning Challenges in Bucharest

> **Bachelor's Thesis** — Bucharest University of Economic Studies (ASE)  
> Faculty of Cybernetics, Statistics and Economic Informatics  
> Author: **Constantin Teodor-Vasile** | Supervisor: Prof. dr. Constanța Mihăescu | Bucharest, 2025

---

## 📌 Description

This thesis analyzes how Bucharest can be transformed from a car-dominated city into a functional, equitable, and sustainable European capital. Through a multidisciplinary approach combining econometrics, spatial analysis, and urban sociology, it identifies the structural dysfunctions of the Romanian capital and proposes concrete reform directions, drawing on successful models such as Paris.

---

## 🎯 Research Hypotheses & Objectives

| | Description |
|---|---|
| **H1** | Residents' general opinion reflects significant dissatisfaction with the current urban organization |
| **H2** | Compared to other cities worldwide, Bucharest shows a gap across key urbanistic indicators |
| **H3** | Based on current indicators, the city's evolution can be projected as a pessimistic scenario |
| **H4** | The "15-minute city" model is only partially applicable in Bucharest due to major structural barriers |

---

## 🗂️ Project Structure

```
📁 bachelors-thesis-bucharest-urbanism/
├── 📄 Examen_Licenta.pdf          # Full thesis document
├── 📜 codLicenta.R                # R scripts used in the analysis
├── 📊 BD_MARE.xlsx                # Main database (Smart City, UN-Habitat, Eurostat)
├── 📄 graficeLicenta.docx         # Exported charts and visualizations
├── 📄 pozeVelo.docx               # Velo Masterplan images
└── 📄 README.md
```

> Additional resources available on GitHub:
> - [R Code](https://github.com/TeoSW/CodRLicenta/blob/main/codLicenta.txt)
> - [Database](https://github.com/TeoSW/CodRLicenta/blob/main/BD%20MARE.xlsx)
> - [![Thesis Presentation](https://img.shields.io/badge/Presentation-PowerPoint-B7472A?logo=microsoft-powerpoint)](https://view.officeapps.live.com/op/view.aspx?src=https://github.com/TeoSW/Bachelors-Project/raw/main/licenta_prezentare.pptx)

---

## 🧮 Methodology

The research combines quantitative and qualitative methods across three main chapters:

### Ch. 1 — Theoretical Foundations & Urban Context
Historical overview of Bucharest's urban evolution, from interwar architectural styles to the communist era's impact and post-1989 transformations. Key concepts analyzed: the **"15-minute city"** model (Carlos Moreno / Anne Hidalgo), periurban sprawl problems, and the lack of alternative transport infrastructure.

### Ch. 2 — Empirical Analysis

**Demographic evolution**
- INS TEMPO-Online data (1992–2024): resident and domicile-registered population
- Age pyramids for Bucharest: 2012, 2018, 2024

**Opinion survey** (Dec. 2024, n = 162 respondents)
- Distribution by district, gender, age, education level
- Traffic, parking, cycling infrastructure, quality of life in neighborhoods
- Tools: Google Forms, SPSS

**International comparison** (UN-Habitat 2019–2020, Eurostat NUTS 2)
- Road mortality rate, public transport access, PM2.5, motorization rate
- Spatial analysis in **GeoDa**: vehicle distribution and population density across Europe
- Multiple regression with robust standard errors (White estimator), Breusch-Pagan and Durbin-Watson tests

**Smart City IMD 2024 predictive model**
- **Random Forest** (700 trees, accuracy 83.1%) for ranking position prediction
- **Bidirectional Stepwise Regression** for identifying relevant predictors (R² = 0.867)
- Improvement scenarios for Bucharest by adjusting `Structure2024` and `Technology2024`

**The "15-minute city" model**
- Spatial analysis using **OpenStreetMap** data: average distances from residences to essential facilities
- Distribution mapping: residential buildings, schools, universities, workplaces

### Ch. 3 — Policy & Strategic Directions
- Paris' sustainable transport revolution: Vélib', Plan Vélo I & II (2015–2026)
- Comparison with Romania's A0 motorway and Bucharest's Velo Masterplan
- Impact analysis of Parisian interventions on traffic flow (NFD method)
- Concrete proposals for reconfiguring urban space in Bucharest

---

## 📊 Key Results

| Indicator | Value |
|---|---|
| Share of passenger cars in total vehicles — Bucharest-Ilfov | **94.6%** (2020) |
| Normalized motorization rate — Bucharest | **0.00534** (among the lowest in Europe) |
| Road mortality rate — Bucharest | **8.54 / 100,000 pop.** (vs. Berlin 4.00, Oslo 1.76) |
| Actual Smart City IMD 2024 rank | **#100** |
| Random Forest estimated rank | **#77.8** (class B) |
| Optimistic scenario (Structure BB + Technology B) | **~#72.7** |
| Average distance to public transport | **230 m** ✅ |
| Average distance to universities | **2,206 m** ⚠️ |
| Average distance to cultural centers | **1,720 m** ⚠️ |
| Respondents willing to cycle with adequate infrastructure | **60%** |

---

## ⚙️ Running the R Code

### Required packages

```r
install.packages(c(
  "tidyverse", "ggplot2", "sf", "osmdata", "spdep",
  "randomForest", "lmtest", "sandwich", "car", "MASS"
))
```

### Required data
- `BD_MARE.xlsx` — main database (Smart City IMD, UN-Habitat, Eurostat NUTS 2)
- Demographic data: [INS TEMPO-Online](http://statistici.insse.ro:8077/tempo-online/)
- Geospatial data: OpenStreetMap via the `osmdata` package

### Run
```bash
Rscript codLicenta.R
```

---

## 🛠️ Tools & Technologies

![R](https://img.shields.io/badge/R-4.x-276DC3?logo=r)
![SPSS](https://img.shields.io/badge/SPSS-Statistics-052FAD)
![GeoDa](https://img.shields.io/badge/GeoDa-Spatial_Analysis-green)

| Tool | Usage |
|---|---|
| **R / RStudio** | Multiple regression, Random Forest, Stepwise, OSM spatial analysis |
| **SPSS** | Survey data processing, descriptive charts |
| **GeoDa** | NUTS 2 spatial analysis — motorization and population density |
| **OpenStreetMap** | Geospatial data for the "15-minute city" evaluation |
| **Excel** | INS demographic data processing, Smart City IMD |

---

## 📚 Main Data Sources

- [INS TEMPO-Online](http://statistici.insse.ro:8077/tempo-online/) — Bucharest demographics
- [UN-Habitat](https://data.unhabitat.org/pages/datasets) — global urban indicators (2019–2020)
- [Eurostat NUTS 2](https://ec.europa.eu/eurostat/databrowser/) — vehicles and population density
- [IMD Smart City Index 2024](https://www.coit.es/sites/default/files/imd_-smartcityindex-2024-full-report.pdf)
- [OpenStreetMap Wiki Features](https://wiki.openstreetmap.org/wiki/Map_features)
- [Velo Masterplan Bucharest](https://pmb.ro/interes-public/arhiva/get-public-interest-announcements/2024/283)

---

## 🏁 Conclusions

Bucharest has **significant urban potential** (urban HDI = 0.926, identical to Warsaw — ranked #38), yet sits at **#100 in the Smart City Index 2024** due to structural deficiencies in infrastructure and digitalization, not a lack of human development.

The "15-minute city" model works partially **only in the central core** of the capital. Peripheral and periurban neighborhoods remain **poorly connected residential enclaves**, car-dependent and lacking essential facilities.

Key reforms identified: expanding public transport, implementing the Velo Masterplan, restricting car access in the city center, and reconfiguring public space in favor of pedestrians and cyclists.

---

*Bachelor's Thesis | Bucharest University of Economic Studies, 2025*
