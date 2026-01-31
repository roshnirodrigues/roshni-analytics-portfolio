# 📊 Data Jobs Market Analysis — Power BI Project

<p align="center">
<img src="Images/Jobs Dashboard - Overview.png" width="500" alt="Jobs Dashboard Overview">

## 🚀 Project Overview

In this project, I analysed data-related job postings from 2024 to understand trends in the data job market. While the original dataset is global, the analysis focuses specifically on India to make the insights more meaningful from a local job-seeker perspective.

This is a **Power BI–focused project**, with emphasis on data cleaning, modelling, and building an interactive dashboard rather than predictive modelling.

---

## 🎯 Business Problem

The data job market is large and constantly changing, which makes it difficult for job seekers to clearly understand:

- Which data roles are in demand  
- What skills employers are looking for  
- How salaries differ across roles and locations  
- How common remote roles and degree requirements are  

The objective of this project was to organise and analyse job posting data to answer these questions clearly and present the insights through an interactive Power BI dashboard.

---

## 🗂️ Data

**Source:** Luke Barousse – Data Jobs Dataset  
**Year:** 2024  
**Collection Method:** Scraped from Google job postings across multiple sources  

The dataset is global in nature. For this project, it was filtered to focus on **India-specific job postings**.

The data follows a **star schema** with the following key tables:

- `job_postings_fact`  
- `job_schedule_dim`  
- `skills_dim`  
- `skill_job_dim`  
- `company_dim`

---

## 🧹 Data Cleaning & Preparation

Data cleaning was performed using **Power Query in Power BI**.

One of the main challenges was that multiple skills, job schedules were stored in a single row for each job posting in the job_postings_fact table. 
To handle this:

- I extracted individual skills from job postings where multiple skills were listed together.

- Created a separate skills dimension table containing skill id, skill and skill type by extracting distinct skills.

- Split the skills into individual rows and linked them back to job postings using a bridge table (skill_job_dim), enabling a one-to-many relationship.

- Similarly, I cleaned the job type information by splitting multiple job types into separate rows for each job ID.

- Removed duplicate job postings.

- Handled inconsistencies in job titles, locations, and skill names.

- Standardised salary fields where possible.

To reduce the impact of outliers:
- **Median salary** was used for yearly and hourly salary comparisons  

Relationships were then created between fact and dimension tables based on the star schema.

<p align="center">
<img src="Images/star schema_jobs.png" width="500" alt="Star Schema Jobs">
---

## 🔍 Analysis Approach

The analysis is descriptive and exploratory, not predictive.

Using Power BI:

- Created measures for job counts, median salaries, and skill frequency  
- Used parameters for dynamic role-based exploration  
- Analysed job demand by role, skill, location, and job type  
- Compared median yearly vs hourly salaries  
- Used slicers and drill-throughs for deeper role-level analysis  

---

## 📈 Dashboard Pages

### Page 1 — Job Market Overview

<p align="center">
<img src="Images/Jobs Dashboard - Overview.png" width="600" alt="Jobs Dashboard Overview">

Provides a high-level view of the Indian data job market.

Includes:

- Total job postings KPI  
- Median salary KPI  
- Job distribution by role  
- Most in-demand skills  
- Median yearly vs hourly salary comparison  
- City-wise job distribution  

Designed for quick market understanding.

---

### Page 2 — Role Deep Dive

<p align="center">
<img src="Images/Jobs Dashboard - Role Beakdown.png" width="600" alt="Jobs Dashboard Role Breakdown">

Allows drill-down into specific roles.

Includes:

- Role-specific job counts  
- Top skills by role  
- Salary trends  
- Job type and remote/work-from-home distribution  

Useful for role comparison and targeted exploration.

---

## 💡 Key Insights

- Data Engineer and Data Analyst roles have the highest posting volume  
- Median yearly salary across data roles is ~₹9.6L  
- Python and SQL are the most consistently required skills  
- Cloud and big data tools appear more in engineering roles  
- Many postings do not explicitly require a degree  
- Remote roles exist but are less common than on-site  
- Bengaluru and Hyderabad lead in job volume  
- LinkedIn is the most common job posting platform  

---

## 🎯 Actions & Use Cases

This dashboard can help:

- Identify high-demand data roles in India  
- Prioritise skills for role preparation  
- Set realistic salary expectations  
- Compare opportunities by city and job type  
- Explore remote vs on-site patterns  

Supports **career exploration and informed decision-making**.

---

## 🛠️ Tools Used

**Power BI**
- Power Query for data cleaning  
- Star schema data modelling  
- Measures and parameters  
- Interactive visuals  
- Slicers and drill-throughs  

---

## ⚠️ Notes & Limitations

- Dataset is based on scraped job postings and may not represent the full market  
- Salary values are median-based estimates  
- Seniority is inferred from posting text only  

---

