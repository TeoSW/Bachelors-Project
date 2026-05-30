# 🏙️ Provocările actuale ale urbanismului în capitală

> **Lucrare de licență** — Academia de Studii Economice din București  
> Facultatea de Cibernetică, Statistică și Informatică Economică  
> Absolvent: **Constantin Teodor-Vasile** | Conducător științific: Prof. univ. dr. Constanța Mihăescu | București, 2025

---

## 📌 Descriere

Lucrarea analizează modalitățile prin care Bucureștiul poate fi transformat dintr-un oraș dominat de automobile într-o capitală europeană funcțională, echitabilă și sustenabilă. Printr-o abordare multidisciplinară care combină econometrie, analiză spațială și sociologie urbană, sunt identificate disfuncționalitățile structurale ale Capitalei și propuse direcții concrete de reformă, inspirate din modele de succes precum Parisul.

---

## 🎯 Obiective și Ipoteze de cercetare

| | Descriere |
|---|---|
| **I1** | Opinia generală a locuitorilor reflectă nemulțumire față de organizarea urbană actuală |
| **I2** | Față de alte orașe din lume, Bucureștiul înregistrează un decalaj la principalii factori urbanistici |
| **I3** | Pe baza indicatorilor actuali, evoluția orașului poate fi proiectată sub forma unui scenariu pesimist |
| **I4** | Modelul „orașului de 15 minute" este aplicabil parțial în București, cu bariere structurale majore |

---

## 🗂️ Structura Proiectului

```
📁 licenta-urbanism-bucuresti/
├── 📄 Examen_Licenta.pdf          # Lucrarea completă de licență
├── 📜 codLicenta.R                # Coduri R utilizate în analiză
├── 📊 BD_MARE.xlsx                # Baza de date principală (Smart City, UN-Habitat, Eurostat)
├── 📄 graficeLicenta.docx         # Vizualizări grafice exportate
├── 📄 pozeVelo.docx               # Imagini MasterPlan Velo București
└── 📄 README.md
```

> Resurse auxiliare disponibile și pe GitHub:
> - [Cod R](https://github.com/TeoSW/CodRLicenta/blob/main/codLicenta.txt)
> - [Baza de date](https://github.com/TeoSW/CodRLicenta/blob/main/BD%20MARE.xlsx)
> - [![Prezentare licență](https://img.shields.io/badge/Prezentare-PowerPoint-B7472A?logo=microsoft-powerpoint)](https://view.officeapps.live.com/op/view.aspx?src=https://github.com/TeoSW/Bachelors-Project/raw/main/licenta_prezentare.pptx)

---

## 🧮 Metodologie

Cercetarea combină metode cantitative și calitative, structurate în trei direcții principale:

### Cap. 1 — Fundamente teoretice și context urbanistic
Context istoric al evoluției urbane a Bucureștiului, de la stilurile interbelice până la impactul comunismului și transformările post-1989. Sunt analizate concepte cheie: modelul **„orașului de 15 minute"** (Carlos Moreno / Anne Hidalgo), problemele zonelor periurbane și deficitul de transport alternativ.

### Cap. 2 — Analiză empirică

**Evoluție demografică**
- Date INS TEMPO-Online (1992–2024): populație după domiciliu și rezidentă
- Piramidele vârstelor în București: 2012, 2018, 2024

**Anchetă de opinie** (dec. 2024, n = 162 respondenți)
- Distribuție pe sectoare, gen, vârstă, nivel educațional
- Trafic, parcare, infrastructură ciclism, calitatea vieții în cartiere
- Instrumente: Google Forms, SPSS

**Comparație internațională** (date UN-Habitat 2019–2020, Eurostat NUTS 2)
- Rata mortalității rutiere, acces transport public, PM2.5, grad de motorizare
- Analiză spațială în **GeoDa**: distribuția vehiculelor și densității populației la nivel european
- Regresie multiplă cu erori standard robuste (White estimator), teste Breusch-Pagan și Durbin-Watson

**Model predictiv Smart City IMD 2024**
- **Random Forest** (700 arbori, acuratețe 83.1%) pentru predicția poziției în clasament
- **Regresie Stepwise bidirecțională** pentru identificarea predictorilor relevanți (R² = 0.867)
- Scenarii de îmbunătățire a scorului București prin varierea `Structure2024` și `Technology2024`

**Modelul „orașului de 15 minute"**
- Analiză spațială cu date **OpenStreetMap**: distanțe medii de la locuințe la facilități esențiale
- Cartografiere distribuție: clădiri rezidențiale, școli, universități, locuri de muncă

### Cap. 3 — Politici și direcții strategice
- Revoluția transportului sustenabil parizian: Vélib', Plan Vélo I & II (2015–2026)
- Comparație cu autostrada A0 și MasterPlanul Velo București
- Analiza impactului intervențiilor pariziene asupra fluxului de trafic (metoda NFD)
- Propuneri concrete pentru reconfigurarea spațiului urban în București

---

## 📊 Rezultate cheie

| Indicator | Valoare |
|---|---|
| Ponderea autoturismelor în total vehicule — București-Ilfov | **94.6%** (2020) |
| Rata motorizării normalizată — București | **0.00534** (printre cele mai mici din Europa) |
| Rata mortalității rutiere — București | **8.54 / 100.000 loc.** (vs. Berlin 4.00, Oslo 1.76) |
| Poziție reală Smart City IMD 2024 | **locul 100** |
| Poziție estimată de modelul Random Forest | **locul 77.8** (clasa B) |
| Scenariu optimist (Structure BB + Technology B) | **locul ~72.7** |
| Distanța medie la transport public | **230 m** ✅ |
| Distanța medie la universități | **2.206 m** ⚠️ |
| Distanța medie la centre culturale | **1.720 m** ⚠️ |
| Respondenți care ar folosi bicicleta cu infrastructură adecvată | **60%** |

---

## ⚙️ Rulare cod R

### Pachete necesare

```r
install.packages(c(
  "tidyverse", "ggplot2", "sf", "osmdata", "spdep",
  "randomForest", "lmtest", "sandwich", "car", "MASS"
))
```

### Date necesare
- `BD_MARE.xlsx` — baza de date principală (Smart City IMD, UN-Habitat, Eurostat NUTS 2)
- Date demografice: [INS TEMPO-Online](http://statistici.insse.ro:8077/tempo-online/)
- Date geospațiale: OpenStreetMap via pachetul `osmdata`

### Rulare
```bash
Rscript codLicenta.R
```

---

## 🛠️ Tehnologii utilizate

![R](https://img.shields.io/badge/R-4.x-276DC3?logo=r)
![SPSS](https://img.shields.io/badge/SPSS-Statistics-052FAD)
![GeoDa](https://img.shields.io/badge/GeoDa-Spatial_Analysis-green)

| Instrument | Utilizare |
|---|---|
| **R / RStudio** | Regresie multiplă, Random Forest, Stepwise, analiză spațială OSM |
| **SPSS** | Prelucrarea datelor din ancheta de opinie, grafice descriptive |
| **GeoDa** | Analiză spațială NUTS 2 — motorizare și densitate populației |
| **OpenStreetMap** | Date geospațiale pentru evaluarea modelului „15 minute" |
| **Excel** | Prelucrare date demografice INS, Smart City IMD |

---

## 📚 Surse principale de date

- [INS TEMPO-Online](http://statistici.insse.ro:8077/tempo-online/) — demografie București
- [UN-Habitat](https://data.unhabitat.org/pages/datasets) — indicatori urbani globali (2019–2020)
- [Eurostat NUTS 2](https://ec.europa.eu/eurostat/databrowser/) — vehicule și densitate populației
- [IMD Smart City Index 2024](https://www.coit.es/sites/default/files/imd_-smartcityindex-2024-full-report.pdf)
- [OpenStreetMap Wiki Features](https://wiki.openstreetmap.org/wiki/Map_features)
- [MasterPlan Velo București](https://pmb.ro/interes-public/arhiva/get-public-interest-announcements/2024/283)

---

## 🏁 Concluzii

Bucureștiul dispune de un **potențial urban semnificativ** (HDI urban = 0.926, identic cu Varșovia — locul 38), însă ocupă locul **100 în Smart City Index 2024** din cauza deficiențelor structurale în infrastructură și digitalizare, nu a unui deficit de dezvoltare umană.

Modelul „orașului de 15 minute" funcționează parțial **doar în nucleul central** al Capitalei. Cartierele periferice și periurbane rămân **enclave rezidențiale slab conectate**, dependente de automobil și lipsite de facilități esențiale.

Reformele prioritare identificate: extinderea transportului public, implementarea MasterPlanului Velo, limitarea accesului auto în centru și reconfigurarea spațiului public în favoarea pietonilor și bicicliștilor.

---

*Lucrare de licență | ASE București, 2025*
