

# 👥 HR Attrition Analysis Dashboard

> **An end-to-end HR analytics project diagnosing employee turnover across a 10,000-employee workforce — using SQL for data extraction and cleaning, Excel for exploratory validation, and Power BI for a 3-page interactive executive dashboard.**

---

## ⚡ Key Numbers Upfront

| Metric | Value |
|--------|-------|
| Total Employees | **10,000** |
| Active Employees | **7,753** |
| Attrition Employees | **2,247** |
| Overall Attrition Rate | **22.47%** |
| Average Employee Age | **40 years** |
| Distance Attrition Gap | **29.93% (>40km) vs 8.58% (<10km)** |
| Highest Role Attrition | **Consultant — 208 employees** |
| Overtime Attrition (Yes) | **34.78% of attrition cases** |
| Fresher Attrition Rate | **24.17% — nearly 1 in 4 new hires** |

---

## 📌 Project Overview

Unmanaged attrition quietly erodes organizational value through recruitment costs, lost productivity, knowledge drain, and disrupted team performance. Most HR teams react to attrition after it happens — because they lack a consolidated, filterable view of who is leaving and why.

This project builds an **interactive, executive-ready HR Attrition Dashboard** that consolidates all attrition drivers into a single reporting system — enabling HR leadership to identify high-risk segments, quantify the problem, and act on data-backed retention recommendations.

The analysis answers one central question: **"Who is leaving the company, and why?"**

---

## ❓ Business Problem — 6 Analytical Questions

| # | Question | Dimension Analyzed |
|---|----------|--------------------|
| 1 | Which departments and job roles have the highest attrition? | Department, Job Role |
| 2 | Does commute distance drive employees to leave? | Distance From Home (KM bands) |
| 3 | Does stalled promotion history correlate with attrition? | Years Since Last Promotion |
| 4 | Which seniority level is most at risk? | Fresher / Junior / Senior / Most Senior |
| 5 | Do overtime, travel demands, and education level predict turnover? | OverTime, Business Travel, Education |
| 6 | Are work-life balance and job satisfaction measurable attrition predictors? | WLB Rating 1–5, Job Satisfaction 1–5 |

---

## 🗃️ About the Data

**Dataset: 10,000 employee records** — structured like enterprise HRIS exports, cleaned and validated before modeling.

| Category | Fields Included |
|----------|----------------|
| **Demographics** | Age, Gender, Education Level |
| **Job Details** | Department, Job Role, Seniority Level, Years Since Last Promotion |
| **Work Conditions** | OverTime (Yes/No), Business Travel, Work-Life Balance (1–5), Job Satisfaction (1–5) |
| **Personal Factors** | Distance From Home to Office (KM) |
| **Target Variable** | Attrition (Yes / No) |

---

## 🛠️ Tools & Workflow

**Pipeline:** `Raw HR Data → SQL (Extract & Clean) → Excel (EDA & Validate) → Power BI (Dashboard)`

| Tool | Role in Project |
|------|----------------|
| **SQL** | Extracted raw HR data, performed cleaning and de-duplication, built aggregations for attrition rate, department counts, seniority breakdowns, and distance band groupings. Validated data before loading. |
| **Excel** | Conducted exploratory data analysis using pivot tables, cross-verified KPI calculations (attrition %, average age, department totals), and performed pre-modeling checks before dashboard build. |
| **Power BI** | Built fully interactive 3-page dashboard with DAX measures for all KPIs. Designed drill-down navigation across pages. Added Gender and Department slicers and embedded narrative insight boxes. |

---

## 📊 Dashboard Structure — 3 Pages

### Page 1 — Overview & KPI Summary
**The executive summary screen.**

- KPI cards: Total Employees (10,000), Active (7,753), Attrition (2,247), Rate (22.47%), Avg Age (40)
- Gender slicer (Female / Male) — filters all visuals simultaneously
- **Attrition by Home Distance** — bar chart across 5 distance bands
- **Attrition by OverTime** — donut chart (Yes: 34.78% / No: 65.2%)
- **Attrition due to Promotion Years** — bar chart by years since last promotion
- **Work Life Balance Rating** — distribution across scores 1–5
- **Job Satisfaction Rating** — distribution across scores 1–5
- **Attrition by Seniority** — horizontal bar (Senior 769, Most Senior 607, Junior 491, Fresher 380)
- Narrative insight box summarizing key drivers

### Page 2 — Distance & Commute Analysis
**Deep-dive into geographic attrition drivers.**

- Same KPI header maintained for context
- **Distance From Home Line Chart** — individual employee distance plotted across 0–50 range, showing commute volatility
- **Attrition by OverTime** donut (maintained for cross-filter reference)
- **Attrition by Seniority** bar (maintained for cross-filter context)
- Narrative insight: "Living Distance from Office causes the Highest number of Attrition, also due to Less Promotions over the Years"

### Page 3 — Role & Department Analysis
**Granular attrition by organizational structure.**

- **Attrition by Job Role & Department** — bar chart across 9 roles (Consultant 208, Director 199, QA Analyst 199, IT 198, Software Engineer 186, Business Analyst 184, Developer 181, Help Desk 181, HR 181)
- **Department slicer** — filter all visuals by department
- **Attrition Due to Travel** — horizontal bar (Travel Rarely: 1,182 | Travel Frequently: 690 | No Travel: 375)
- **Attrition by Education** — donut chart (Graduation 35.12%, Degree 28.43%, Master's 20.4%, PhD 8.36%, Below College 7.69%)
- Narrative insight boxes on travel behavior and education attrition patterns

---

## 💡 Key Insights — All Numbers Verified from Dashboard

### Insight 1 — Distance From Home is the Strongest Attrition Predictor

| Distance Band | Attrition Rate |
|--------------|----------------|
| Above 40 KM | **29.93%** |
| Under 40 KM | 25.20% |
| Under 20 KM | 24.54% |
| Under 30 KM | 24.22% |
| Under 10 KM | **8.58%** |

Employees living beyond 40 KM attrite at **3.5x the rate** of those living under 10 KM. Commute burden is the clearest geographic retention signal in the dataset.

**Action:** Remote/hybrid work policy and commute support programs directly target the highest-risk attrition segment.

---

### Insight 2 — Seniority: Freshers Have the Highest Rate, Seniors Have the Highest Count

| Seniority Level | Attrition Count |
|-----------------|----------------|
| Senior | **769** |
| Most Senior | 607 |
| Junior | 491 |
| Fresher | 380 |

Senior employees have the **highest absolute attrition volume** (769). But Freshers show a **24.17% attrition rate** — nearly 1 in 4 new hires leaves. Seniors attrite at the lowest rate (17.83%), indicating stronger organizational commitment at higher levels.

**Action:** Strengthen onboarding, early-career development programs, and 90-day check-ins to improve Fresher retention — it is cheaper to retain a new hire than recruit a replacement.

---

### Insight 3 — Promotion Stagnation Drives Attrition

| Years Since Promotion | Attrition Count |
|----------------------|----------------|
| 6 years | **305** (highest) |
| 2 years | 293 |
| 7 years | 291 |
| 8 years | 290 |
| 4 years | 284 |
| 3 years | 280 |
| 5 years | 278 |
| 1 year | 150 |
| 0 years | 76 |

Attrition peaks at **6 years without promotion**. Employees who received a promotion recently (0–1 years) show dramatically lower attrition. The data signals a clear career stagnation threshold around the 5–7 year mark.

**Action:** Introduce structured promotion review cycles with defined timelines. Employees approaching the 4-year mark without advancement should be flagged for career planning conversations.

---

### Insight 4 — Overtime is a Material Attrition Driver

| OverTime Status | Count | % of Attrition |
|----------------|-------|---------------|
| Yes | 104 | **34.78%** |
| No | 195 | 65.22% |

Employees required to work overtime represent a disproportionate share of attrition cases — signaling workload and burnout as retention risk factors.

---

### Insight 5 — Travel Rarely = Highest Attrition Volume (Counter-Intuitive)

| Travel Frequency | Attrition Count |
|-----------------|----------------|
| Travel Rarely | **1,182** |
| Travel Frequently | 690 |
| No Travel | 375 |

Employees who travel rarely — not frequently — account for the largest attrition group. The dashboard narrative explains this: employees dislike being required to travel when it disrupts their routine, even infrequently.

**Action:** Clarify travel expectations at time of hiring. Employees with travel in their role who are not aligned to it are a hidden attrition risk.

---

### Insight 6 — Education: Mid-Level Education Drives Most Attrition

| Education Level | % of Attrition |
|----------------|---------------|
| Graduation | **35.12%** |
| Degree | 28.43% |
| Master's | 20.40% |
| PhD | 8.36% |
| Below College | 7.69% |

Employees with high and low education levels show less attrition. The mid-range (Graduation and Degree) accounts for over 63% of all attrition — suggesting this group has the most mobility in the job market and the highest alternative employment options.

---

### Insight 7 — Satisfaction Ratings Skew Low Among Attrition Cases

**Work-Life Balance Rating distribution (attrition employees):**

| Rating | Count |
|--------|-------|
| 2 (Low) | **628** (highest) |
| 1 (Lowest) | 604 |
| 3 | 375 |
| 4 | 320 |
| 5 | 320 |

**Job Satisfaction Rating distribution:**

| Rating | Count |
|--------|-------|
| 1 (Lowest) | **545** (highest) |
| 2 | 541 |
| 3 | 402 |
| 4 | 397 |
| 5 | 362 |

Both distributions are **inverted** — the lowest satisfaction scores dominate attrition cases. Employees rating WLB at 1–2 and Job Satisfaction at 1–2 represent the highest-risk retention segment.

---

## 🎯 Business Impact & Recommendations

| Finding | Recommendation | Priority |
|---------|---------------|----------|
| 29.93% attrition above 40 KM | Launch remote/hybrid policy for long-distance commuters | 🔴 High |
| 24.17% Fresher attrition rate | Strengthen onboarding + 90-day check-in program | 🔴 High |
| Attrition peaks at 6 years without promotion | Structured promotion review every 3–4 years | 🔴 High |
| Sales has highest attrition rate (20.52%) | Department-specific retention programs in Sales | 🟡 Medium |
| R&D has highest absolute attrition (961) | Role-specific exit interviews to identify drivers | 🟡 Medium |
| WLB scores 1–2 dominate attrition | Flexible scheduling and wellbeing investment | 🟡 Medium |
| Overtime correlates with attrition | Workload review — overtime as lagging indicator | 🟢 Monitor |

**Cost framing:** At an industry-standard replacement cost of 50–200% of annual salary per employee, reducing the 22.47% attrition rate by even 3–5 percentage points on a 10,000-employee workforce represents significant avoided cost — making retention programs a measurable ROI investment, not a soft initiative.

---

## 🗂️ Repository Structure

```
hr-attrition-analysis-dashboard/
│
├── data/
│   └── hr_attrition_dataset.csv          # Raw 10,000-employee dataset
│
├── sql/
│   └── hr_attrition_queries.sql          # Data extraction, cleaning, aggregation queries
│
├── excel/
│   └── hr_attrition_eda.xlsx             # EDA pivot tables and KPI validation workbook
│
├── powerbi/
│   └── HR_Attrition_Dashboard.pbix       # Power BI dashboard file (3 pages)
│
├── assets/
│   ├── page1_overview.png                # Dashboard Page 1 screenshot
│   ├── page2_distance_analysis.png       # Dashboard Page 2 screenshot
│   └── page3_role_department.png         # Dashboard Page 3 screenshot
│
└── README.md
```

---

## ▶️ How to Use

**1. Clone the repository**
```bash
git clone https://github.com/SandipMandal-52/hr-attrition-analysis-dashboard.git
```

**2. Run SQL queries** (optional — if exploring data first)
```sql
-- Open sql/hr_attrition_queries.sql in SSMS or any SQL client
-- Execute sections in order: cleaning → aggregation → KPI validation
```

**3. Open Excel workbook** (optional — EDA and pivot validation)
```
Open excel/hr_attrition_eda.xlsx
Review pivot tables for pre-dashboard KPI cross-checks
```

**4. Open Power BI dashboard**
```
Open powerbi/HR_Attrition_Dashboard.pbix in Power BI Desktop
Refresh data source if prompted (point to your local data/ folder)
```

**5. Interact with the dashboard**
```
Use Gender slicer (top right) to filter by Female / Male
Use Department slicer (Page 3) to drill into specific departments
Navigate pages using the left sidebar icons:
  → Page 1: Overview KPIs and primary attrition drivers
  → Page 2: Distance and commute deep-dive
  → Page 3: Role, department, travel, and education analysis
```

---

## 🔮 Next Steps

- **Predictive Attrition Modeling** — Python logistic regression or Random Forest on the same dataset to score each employee's churn probability
- **Automated SQL Refresh Pipeline** — Scheduled data refresh via SQL Agent Jobs or Power BI Service gateway
- **Post-Intervention KPI Tracking** — Baseline current attrition rates by segment; re-measure after retention program implementation (90-day, 6-month, 12-month)
- **Cohort Analysis by Hire Year** — Track whether attrition rates differ across hiring cohorts to identify structural vs cyclical patterns
- **Compensation Analysis Integration** — Add salary band data to test whether pay is a confounding variable in the distance and promotion findings

---

## 🛠️ Tools & Environment

![SQL Server](https://img.shields.io/badge/Microsoft_SQL_Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)
![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

| Tool | Version/Environment |
|------|-------------------|
| SQL | Microsoft SQL Server / T-SQL |
| Excel | Microsoft Excel (Pivot Tables, EDA) |
| Power BI | Power BI Desktop (DAX, 3-page dashboard) |
| Dataset | 10,000 HR employee records |

---

## 👤 Author

**Sandip Mandal** — EDP Analyst | Aspiring Data Analyst
📍 Nagpur, Maharashtra, India
🔗 [LinkedIn](https://linkedin.com/in/sandipmandal52) | [GitHub](https://github.com/SandipMandal-52) | 📧 sandipmandalcv@gmail.com

---

*Data doesn't just tell you who left — it tells you exactly where to intervene before the next one does.*

---

