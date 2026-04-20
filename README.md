# Time Series Analysis of Medical Appointments

> An SQL-driven analytics project uncovering scheduling patterns, 
> no-show trends, and peak demand periods in a 110,000+ record 
> healthcare dataset — with an interactive Tableau dashboard for 
> stakeholder communication.

---

## Business Problem

Healthcare systems struggle with appointment no-shows, uneven demand 
distribution, and scheduling inefficiencies - leading to wasted 
clinical capacity and longer patient wait times. This project analyzes 
appointment data from a time-series perspective to answer:

- When do peak appointment volumes occur (daily / weekly / monthly)?
- What is the no-show rate and which patient segments are most affected?
- How large are scheduling delays between booking and appointment date?
- Are there actionable patterns that could reduce no-shows?

---

## Dataset

- **Records:** 110,000+ medical appointments
- **Source:** Brazilian public health system dataset (Kaggle)
- **Key fields:** ScheduledDay, AppointmentDay, No-show status, 
  patient demographics, health conditions, SMS reminder flag

---

## Methodology

**1. Data Preparation (Python)**
- Loaded and inspected the dataset for nulls, duplicates, 
  and data type issues
- Parsed and formatted datetime columns for SQL time-series analysis
- Cleaned inconsistent date entries and removed invalid records

**2. Time Series SQL Analysis**
Core SQL techniques applied:

| Technique | Purpose |
|---|---|
| `GROUP BY` + `DATE_TRUNC` | Daily, weekly, monthly appointment counts |
| `COUNT()` + `AVG()` | Volume aggregation and averages |
| Window functions | Rolling trends and period-over-period comparison |
| `DATEDIFF` / date arithmetic | Scheduling delay distribution |
| Subqueries & CTEs | No-show rate by patient segment |

**3. Visualization & Dashboard (Tableau)**
- Built an interactive Tableau Public dashboard
- Visualized appointment trends, no-show rates, and peak periods
- Enabled filtering by time period, patient demographics, 
  and health conditions

---

## Tech Stack

`SQL` `Python` `Pandas` `Matplotlib` `Seaborn` `Tableau Public` 
`Jupyter Notebook`

---

## Tableau Dashboard Link: 
https://public.tableau.com/views/MedicalAppointmentNo-ShowAnalysis/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

<img width="1644" height="760" alt="Screenshot 2026-04-20 184843" src="https://github.com/user-attachments/assets/ef0b48d7-8494-40ca-a7be-c23b000d5f39" />


## Key Insights from SQL + Python Analysis

### Appointment Volume
- **106,988 valid appointments** analyzed after removing outliers 
  (negative scheduling delays and invalid age records)
- Average of **~3,963 appointments per day** across the dataset period
- **Busiest single day: June 6, 2016** with 4,529 appointments
- **Wednesday and Tuesday** are peak weekdays (25,090 and 24,831 
  appointments respectively)
- **Saturday has only 39 appointments** - high no-show rate on 
  Saturdays (23.1%) is based on a very small sample and should 
  be interpreted with caution

### Gender Distribution
- **Female patients dominate: 70,119 (65.5%)** vs Male: 36,869 (34.5%)
- No-show rates are similar across genders - gender alone is not 
  a strong predictor of absence

### Scheduling Patterns
- Average of **10.17 days between booking and appointment**
- Same-day appointments (lead time = 0) have significantly lower 
  no-show rates - urgency reduces absence
- Longer scheduling delays correlate with higher no-show likelihood

### No-Show Risk Factors
- **Overall no-show rate: 20.2%** - persistent across all months, 
  indicating a structural not seasonal problem
- **Alcoholism patients: ~42% no-show rate** - highest risk group, 
  more than double the average
- **Age group 18-35** shows the highest no-show rate among 
  demographic segments
- **SMS paradox:** Patients who received SMS showed higher no-show 
  rates (27.6%) than those who didn't (16.7%) - because SMS was 
  targeted at already high-risk patients, not because SMS is 
  ineffective

## Business Recommendation
Redesign the SMS targeting strategy to focus on age 18-35 patients 
and those with alcoholism diagnoses. Supplement with direct phone 
call reminders for the highest-risk segments. Given the stable ~20% 
no-show rate across all months, a systemic intervention - not a 
seasonal campaign - is required.
