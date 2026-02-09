# Time Series Analysis of Medical Appointments Using SQL
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

Tableau Dashboard Link: https://public.tableau.com/views/MedicalAppoinmentAnalysis/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link
