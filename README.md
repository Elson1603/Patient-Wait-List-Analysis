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

![Summary View](<img width="1378" height="767" alt="Screenshot 2026-07-10 035620" src="https://github.com/user-attachments/assets/5ab9604e-45e5-4a11-9976-34129bd82cf9" />
)

### Detailed View
Drill-down matrix for granular, specialty-level and time-band-level analysis.

![Detailed View](<img width="1360" height="757" alt="Screenshot 2026-07-10 035711" src="https://github.com/user-attachments/assets/bbd8f895-b511-4c8e-bbf0-5148bdb79b03" />
)

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

*(Add 2–3 of your own findings here once you've explored the final dashboard — e.g. which specialty had the highest wait list, how the overall trend moved year-over-year, etc. Concrete numbers here make this section stand out to recruiters.)*

---

## 🔮 Future Improvements

- Add forecasting for future wait-list trends using Power BI's built-in analytics.
- Automate data refresh via Power Query from a live source.
- Add a Power BI Service publish link for a live, browser-based demo.

---

## 👤 Author

**Elson Wilson Machado**
[LinkedIn](https://www.linkedin.com/in/elson-machado-601987322) · [GitHub](https://github.com/Elson1603)
