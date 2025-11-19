# Data Professionals Survey – Power BI Dashboard

This project analyzes a survey of **630+ data professionals** and visualizes key insights about
salary, skills, demographics, and job satisfaction using **Power BI**.

The goal is to practice an end-to-end BI workflow: importing raw survey data, cleaning and
transforming it in Power Query, building a simple data model with DAX measures, and designing
an interactive, insight-driven dashboard.

---

## 📁 Dataset

- **Source:** Online survey of data professionals (630+ respondents)
- **Fields include:**
  - Country of origin
  - Job title (Data Analyst, Data Scientist, Data Engineer, etc.)
  - Age
  - Annual salary (USD)
  - Favourite programming language
  - Rating of:
    - Happiness with work–life balance
    - Happiness with salary
    - Difficulty breaking into data

> Note: The raw survey file is provided for learning purposes only. All personal identifiers, if any,
have been removed.

---

## 🎯 Objectives

1. Clean and standardize survey data so it can be analyzed reliably.
2. Explore how salary and satisfaction vary across different data roles.
3. Identify trends in favourite programming languages among data professionals.
4. Understand how hard people feel it is to break into data.
5. Build an intuitive Power BI dashboard that could be used by hiring managers, educators, or aspiring data professionals.

---

## 🧹 Data Cleaning & Preparation (Power Query)

All data preparation was done in **Power Query** inside Power BI:

- Removed empty rows and obvious test/invalid responses.
- Standardized **country names**  
  - e.g., “US”, “U.S.A.” → `United States`
- Grouped similar **job titles** into broader categories  
  - e.g., “Business Data Analyst”, “Reporting Analyst” → `Data Analyst`
- Converted:
  - Salary columns to numeric (annual salary in USD)
  - Rating columns to numeric scales (1–10)
- Handled missing values:
  - Dropped rows with critical fields completely missing (e.g., salary & job title)
  - Left some missing ratings as blanks to avoid bias
- Created additional columns where needed (e.g., cleaned job title / country fields).

---

## 🧠 Data Model & DAX

A simple **single-table model** was used for this project, with a few calculated measures:

Example measures (names may vary in the `.pbix`):

- `Total Participants = COUNTROWS(Survey)`
- `Average Age = AVERAGE(Survey[Age])`
- `Average Salary = AVERAGE(Survey[SalaryUSD])`
- `Avg WorkLife Balance = AVERAGE(Survey[WorkLifeRating])`
- `Avg Salary Happiness = AVERAGE(Survey[SalaryHappinessRating])`

These measures are used across cards, bar charts, and gauges so that they dynamically
recalculate when t
