# 🏥 Healthcare Analytics Power BI Dashboard

An end-to-end, interactive Power BI healthcare dashboard designed to analyze patient demographics, encounter trends, procedure details, and overall healthcare claim costs.

---

## 🚀 Project Overview & Objectives
* **Objective:** Design and construct a comprehensive analytics solution to evaluate healthcare service utilization, regional patient density, and financial distributions.
* **Key Focus Areas:** Data cleaning, Star Schema relationship modeling, DAX measure creation, bidirectional cross-filtering, geographic mapping, and executive visual styling.

---

## 🛠️ Phases & Technical Implementation

### Phase 1: Data Preparation & Preprocessing (Excel & Power Query)
* **Data Extraction:** Imported core dataset tables (`Patients`, `Encounters`, `Procedures`) into Microsoft Excel and Power Query.
* **Data Cleaning:**
  * Cleaned missing, null, and blank entries across critical category fields (e.g., `Gender`, `ZIP`, `Class`).
  * Converted raw timestamps into standard `Date` formats to enable time-intelligence capabilities.
  * Resolved missing/null values with appropriate data imputation methods.

### Phase 2: Data Modeling & Architecture (Star Schema)
* **Schema Design:** Structured the relational model into a **Star Schema**:
  * **Dimension Tables:** `Patients` (Demographics, Gender, Location) and `Procedures` (Medical Procedures, Descriptions).
  * **Fact Table:** `Encounters` (Visits, Costs, Dates, Payers).
* **Relationship Configuration:**
  * Established `1:N` (One-to-Many) relationships (`Patients[Id]` $\rightarrow$ `Encounters[PATIENT]` and `Patients[Id]` $\rightarrow$ `Procedures[PATIENT]`).
  * Established relationships between `Encounters[Id]` and `Procedures[ENCOUNTER]`.
* **Cross-Filtering Adjustment:**
  * Configured bidirectional cross-filtering ("Both") between `Patients` and `Encounters` to ensure seamless dynamic updates across connected tables when filtered by patient attributes like `Gender`.

### Phase 3: DAX Formulas & KPI Measures
Key executive metrics were authored using Data Analysis Expressions (DAX):
* **Total Patients**
* **Total Encounters**
* **Total Claim Cost**
* **Total Procedures Count**

### Phase 4: Visualization & Dashboard Development
* **Executive KPI Cards (Top Banner):** High-level summary metrics (`Total Patients`, `Total Encounters`, and `Total Claim Cost`).
* **Yearly & Monthly Trend Analysis (Line Chart):** Temporal trends using `START` date hierarchy with drill-down/drill-up capabilities.
* **Procedure Analysis (Clustered Bar Chart):** Ranked high-frequency healthcare services by procedure descriptions.
* **Geographic Distribution (Map Visual):** Integrated `Latitude` and `Longitude` coordinates with `Total Patients` bound to bubble sizes for regional density analysis.
* **Insurance & Demographic Breakdown:** Visual breakdowns including `Payer Name` vs. `Total Claim Cost` and `Encounter Class` splits (Inpatient, Outpatient, Emergency).
* **Interactive Slicers:** `Gender` and `Encounter Class` slicers with visual-level filtering to omit `(Blank)` categories.

### Phase 5: Visual Styling & Quality Assurance
* Applied a cohesive medical/corporate color theme.
* Enhanced visual framing using rounded borders, drop shadows, and a customized high-transparency healthcare background image.
* Verified end-to-end cross-filtering interactivity across all visuals.

---

## 💻 Tech Stack & Tools
* **Microsoft Excel & Power Query** (Data Extraction & Transformation)
* **Power BI Desktop** (Data Modeling & Visualization)
* **DAX (Data Analysis Expressions)** (Calculated Measures)
