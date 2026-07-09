# 🏥 Patient Healthcare Wait List Dashboard

An interactive **Power BI** dashboard that analyzes multi-year patient wait-list data across hospital specialties, case types, and age groups — built to help identify wait-list trends and support data-driven healthcare planning.

> 📊 Data cleaned and structured in **Excel**, modeled and visualized in **Power BI** using **DAX**.

---

## 📌 Overview

Long patient wait lists are a major challenge in healthcare systems. This project transforms raw, multi-year wait-list records into a clear, interactive dashboard that lets stakeholders quickly answer questions like:

- How has the overall wait list changed compared to the previous year?
- Which specialties have the longest average/median wait times?
- How is the wait list distributed across age groups and time bands (0–3 months, 3–6 months, 18+ months, etc.)?
- How does the wait list break down by care type — Outpatient, Day Case, or Inpatient?

---

## ✨ Key Features

- **Dynamic KPI Cards** — Latest month vs. previous-year wait list totals, calculated with DAX time-intelligence measures.
- **Average / Median Toggle** — A calculation-method switch lets users instantly recalculate every KPI and visual using either the average or the median.
- **Case Type Breakdown** — Donut chart showing the split between Outpatient, Day Case, and Inpatient cases.
- **Age Profile × Time Band Analysis** — Stacked bar chart showing how wait times are distributed across age groups (0–15, 16–64, 65+) and time bands.
- **Specialty Ranking** — Ranked list of specialties (e.g., Paediatric ENT, Paediatric Orthopaedic, Paediatric Dermatology) by average/median wait list.
- **Trend Analysis** — Line charts tracking Day Case/Inpatient and Outpatient volumes over time (2018–2021).
- **Detailed Drill-Down View** — A matrix table that expands from Archive Date → Specialty → Age Profile → Time Band, showing Day Case, Inpatient, Outpatient, and Total counts at every level.
- **Interactive Filters** — Archive date range slider, Case Type, Specialty Name, Age Profile, and Time Bands slicers, all cross-filtering the entire report.

---

## 🖼️ Dashboard Preview

### Summary View
KPI overview, case type split, age/time-band distribution, and specialty rankings.

<img width="1378" height="767" alt="Summary View - Patient Wait List Dashboard" src="https://github.com/user-attachments/assets/5ab9604e-45e5-4a11-9976-34129bd82cf9" />

### Detailed View
Drill-down matrix for granular, specialty-level and time-band-level analysis.

<img width="1360" height="757" alt="Detailed View - Patient Wait List Dashboard" src="https://github.com/user-attachments/assets/bbd8f895-b511-4c8e-bbf0-5148bdb79b03" />

---

## 🗂️ Data Model

The report is built around one main fact table and two supporting tables:

**`All_Data`** (fact table)
| Field | Description |
|---|---|
| `Archive_Date` | Date the wait-list snapshot was recorded |
| `Case_Type` | Outpatient / Day Case / Inpatient |
| `Age_Profile` | Age band of the patient (0–15, 16–64, 65+) |
| `Adult_Child` | Adult or child classification |
| `Time_Bands` | Length of time on the wait list (0–3 Months, 3–6 Months, … 18+ Months) |
| `Specialty_Name` / `Specialty_HIPE` | Medical specialty |
| `Total` | Number of patients |
| `Average Wait List` / `Median Wait List` | Calculated wait-list measures |
| `Latest Month Wait List` / `PY Latest Month Wait List` | Current vs. prior-year comparison measures |
| `Dynamic Title` | DAX measure used to drive dynamic visual titles |

**`Calculation_Method`** — a disconnected parameter table powering the Average/Median toggle.

**`Mapping_Specialty`** — maps individual specialties to broader specialty groups for roll-up reporting.

---

## 🛠️ Tools & Techniques

- **Microsoft Excel** — Data cleaning, structuring, and preparation of raw multi-year wait-list records.
- **Power BI Desktop** — Data modeling, relationships, and report/dashboard design.
- **DAX** — Time-intelligence and conditional measures, including:
  - Dynamic Average/Median switching via a disconnected parameter table
  - Year-over-year (latest month vs. PY latest month) comparisons
  - Dynamic titles that update based on active filter selections

---

## 🚀 How to Use

1. Clone this repository:
   ```bash
   git clone https://github.com/Elson1603/Patient-Wait-List-Analysis.git
   ```
2. Open the `.pbix` file in **Power BI Desktop**.
3. If prompted, update the data source path to point to the included dataset.
4. Use the slicers (Archive Date, Case Type, Specialty, Age Profile, Time Bands) to explore the data.
5. Click the **Average/Median** toggle to switch calculation methods across all visuals.

---

## 📁 Repository Structure

```
Patient-Wait-List-Analysis/
├── screenshots/
│   ├── summary-view.png
│   └── detailed-view.png
├── data/
│   └── [raw/cleaned dataset]
├── Patient_Wait_List_Dashboard.pbix
└── README.md
```

---

## 📈 Key Insights

- **Wait list grew year-over-year.** The latest month's total wait list (709K) is roughly **11% higher** than the same month the previous year (640K), suggesting growing rather than easing pressure on services.
- **Outpatient care dominates the wait list.** Outpatient cases make up the largest share of the average wait list (~72%), well ahead of Day Case (~17%) and Inpatient (~11%) — making outpatient scheduling the biggest lever for reducing overall wait times.
- **Paediatric specialties are the top bottleneck.** Paediatric ENT (272), Paediatric Orthopaedic (264), and Paediatric Dermatology (233) have the highest average/median wait lists among individual specialties.
- **Growth is concentrated in Outpatient.** From 2018 to 2021, Outpatient volumes climbed from ~0.5M to over 0.6M, while combined Day Case and Inpatient volumes stayed roughly flat around 50K — most of the year-over-year increase in the wait list is coming from the outpatient side, not inpatient or day-case capacity.

---

