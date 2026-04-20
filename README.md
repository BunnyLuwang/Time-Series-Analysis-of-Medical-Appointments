# Time Series Analysis of Medical Appointments
This repository contains a data analytics project that performs time series analysis of medical appointment data using SQL queries. The analysis focuses on clean data preparation, visualizing trends in appointment counts over time, and extracting actionable insights from a real-world healthcare dataset using standard SQL techniques.

## Project Overview
Healthcare systems generate large volumes of appointment data. Analyzing this data with a time-series perspective can help answer important operational questions like:

 > When do most appointments occur?

 > How do weekly and monthly patterns differ?

 > Are there trends around scheduling delays or no-shows?

This project implements a structured workflow to explore such patterns using SQL on a cleaned dataset, making it perfect for those learning SQL analytics, time series analysis, and healthcare data exploration.

## Tasks done in the project:
1. Data Preparation

> Load and inspect the medical appointment dataset

> Clean and format dates for use in SQL time-series analysis

> Identify missing or inconsistent data (cleaning steps)

2. Time Series SQL Analysis

> SQL queries included in the Jupyter Notebook focus on:

> Daily, weekly, and monthly counts of appointments

> Trend detection and peak volume periods

> Calculating averages and identifying significant patterns in appointment scheduling

> Comparing time intervals between scheduled and actual appointment dates

Each query demonstrates core SQL functions such as GROUP BY, DATE_TRUNC, COUNT(), and window functions for time-series aggregation.

## Tools & Technologies
Technology	Purpose
SQL	Main tool for querying and analyzing time-series data
Python / Jupyter Notebook	Hosting SQL execution environment and visualization
Matplotlib / Seaborn	(optional) plotting trends and time series patterns
CSV / SQL Database	Dataset storage

This SQL-centric workflow encourages analysts to leverage SQL’s strengths for temporal data insights.

Tableau Dashboard Link: https://public.tableau.com/views/MedicalAppointmentNo-ShowAnalysis/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

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
