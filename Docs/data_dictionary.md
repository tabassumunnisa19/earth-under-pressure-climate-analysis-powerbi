# 📘 Data Dictionary  
**Earth Under Pressure — Climate Systems & Human Impact Analysis**

This document describes the datasets, fields, and analytical purpose of each table used in the Power BI project.  
The data model integrates **multiple climate, environmental, and human activity datasets** to enable both **global and regional analysis** of climate pressure and its impacts.

---

## 🗂️ FACT_ENSO  
**ENSO (El Niño–Southern Oscillation) Indicators**

This table captures monthly ENSO conditions used to study the relationship between climate cycles, temperature variability, and extreme events.

| Column Name | Description |
|------------|------------|
| Year | Calendar year |
| Month | Month of observation |
| ENSO_Phase | ENSO classification (El Niño, La Niña, Neutral) |
| ENSO Phase (Month) | Derived categorical indicator combining phase and month |
| Niño3.4 | Sea surface temperature anomaly index (Niño 3.4 region) |
| ONI | Oceanic Niño Index used to quantify ENSO strength |

**Usage:**  
Used to analyze ENSO intensification and its alignment with temperature anomalies and disaster patterns.

---

## 🗂️ FACT_Master_Climate_CountryWise  
**Human Impact & Climate Driver Master Dataset**

This is a **region-based master fact table** created by merging multiple human-driven climate datasets.  
It enables country-level and temporal analysis of anthropogenic climate drivers.

| Column Name | Description |
|------------|------------|
| Country | Country name |
| Year | Year of observation |
| Annual CO₂ emissions (per capita) | Per-capita carbon dioxide emissions |
| Annual methane emissions in CO₂ equivalents | Methane emissions converted to CO₂ equivalents |
| Fossil fuels (TWh) | Fossil fuel energy consumption |
| Share of land covered by forest | Forest cover percentage |

**Usage:**  
Used to evaluate how human activities contribute to rising global temperatures and climate stress.

---

## 🗂️ FACT_Natural_Disasters_1900_2024  
**Historical Climate-Related Disaster Records**

This dataset contains detailed records of natural disasters spanning more than a century, supporting long-term trend analysis.

| Column Name | Description |
|------------|------------|
| Year | Year of disaster occurrence |
| Decade | Derived decade grouping |
| Country | Affected country |
| Continent | Continent classification |
| Region | Regional grouping |
| Disaster Group | High-level disaster category |
| Disaster Subgroup | Sub-classification of disaster |
| Disaster Type | Specific disaster type |
| Disaster Subtype | Detailed disaster classification |
| Dis Mag Scale | Disaster magnitude indicator |
| Start Year / Month / Day | Disaster start date |
| End Year / Month / Day | Disaster end date |
| Total Affected | Total number of people affected |
| Total Deaths | Number of fatalities |
| Total Damages (000 US$) | Estimated economic damage |
| CPI | Consumer Price Index (for normalization) |
| ISO | Country ISO code |
| Location | Specific location information |
| Seq | Event sequence identifier |

**Usage:**  
Used to study the increase in disaster frequency, severity, human impact, and economic loss over time.

---

## 🗂️ FACT_Temperature_Yearly  
**Global Temperature Anomalies (Annual)**

This table represents long-term global temperature deviation from baseline averages.

| Column Name | Description |
|------------|------------|
| Year | Calendar year |
| Decade | Derived decade grouping |
| Avg_Temperature_Anomaly | Average annual temperature anomaly |

**Usage:**  
Serves as the central climate signal for linking temperature rise with disasters, ENSO cycles, and heat stress.

---

## 🗂️ FACT_Temperature_Monthly  
**Monthly Temperature Data**

Provides higher temporal resolution temperature data for detailed climate pattern analysis.

| Column Name | Description |
|------------|------------|
| Year | Calendar year |
| Month | Month |
| Temperature | Monthly average temperature |

**Usage:**  
Used in heat stress and seasonal climate variability analysis.

---

## 🗂️ FACT_Urbanisation_1960_2024  
**Historical Urbanization Data**

Tracks urban population growth over time to analyze heat island effects and local-level climate stress.

| Column Name | Description |
|------------|------------|
| Country Name | Country |
| Year | Year of observation |
| Urban_Population_Percent | Percentage of population living in urban areas |

**Usage:**  
Used to study urban heat island effects and increased exposure to heat stress.

---

## 🗂️ FACT_Urbanisation_Estimated_Upto_2050  
**Projected Urbanization Trends**

Provides estimated future urban population trends.

| Column Name | Description |
|------------|------------|
| Country | Country |
| Year | Projection year |
| Urban_Population_Percent | Estimated urban population share |

**Usage:**  
Used for contextual insight into future urban heat risk (exploratory only).

---

## 🗂️ LOOKUP_Heat_Index  
**Heat Stress Risk Classification**

A lookup table mapping temperature and humidity combinations to heat risk categories.

| Column Name | Description |
|------------|------------|
| Temperature | Air temperature |
| Humidity | Relative humidity |
| Heat_Index | Derived heat index value |
| Heat Risk Category | Categorical risk level (Safe → Extreme Danger) |

**Usage:**  
Used to classify human heat stress risk based on combined temperature and humidity.

---

## 🗂️ Heat_Health_Risk  
**Human Heat Exposure Assessment**

Supports analysis of dangerous heat exposure at local and regional levels.

| Column Name | Description |
|------------|------------|
| Temperature | Observed temperature |
| Humidity | Observed humidity |
| Heat Index | Calculated perceived temperature |
| Risk Level | Health risk classification |

---

## 🔄 Data Transformation Notes

- All datasets were cleaned and transformed using **Power Query**
- Time alignment was performed using **Year** and **Decade**
- Human impact datasets were merged into a **single master fact table**
- Calculated fields and indicators were created using **DAX**

---

## ⚠️ Usage Notes

- This analysis is **descriptive and exploratory**, not predictive  
- Results depend on historical data availability and reporting practices  
- Insights should be interpreted within long-term climate context  

---

**Author:** Tabassum Unnisa  
**Project:** Earth Under Pressure — Climate Systems & Human Impact Analysis
