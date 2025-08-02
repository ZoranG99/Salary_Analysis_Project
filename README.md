# Skills & Salary Analysis Project

## Introduction

Navigating the data science job market can be challenging, especially when trying to identify which skills truly drive better opportunities and higher pay. This project explores real-world job data to uncover trends in salaries, regional differences, and in-demand skills for data professionals.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**  
2. **What’s the salary for data jobs in different regions?**  
3. **What are the top skills of data professionals?**  
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel tools and techniques were used in this analysis:

- **📊 Pivot Tables**  
- **📈 Pivot Charts**  
- **🧮 DAX (Data Analysis Expressions)**  
- **🔍 Power Query**  
- **💪 Power Pivot**

### Dataset Overview

This project utilizes a dataset containing real job listings and salary information from data-related roles in 2023. It includes key insights into:

- **👨‍💼 Job titles**  
- **💰 Salaries**  
- **📍 Locations**  
- **🛠️ Skills**

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

I began by using Power Query to extract the original data (`data_jobs_salary_all.xlsx`) and create two queries:

- 🗃️ One containing all job listing details.
- 🔧 Another mapping each job ID to its listed skills.

#### 🔄 Transform

Each query was cleaned and transformed by:

- Changing column data types  
- Removing unnecessary columns  
- Standardizing and cleaning text  
- Trimming excess whitespace

- 📊 `data_jobs_salary`

    <img width="320" height="395" alt="data_jobs_all applied steps" src="https://github.com/user-attachments/assets/ddf49cc6-2316-49ac-b6a7-602b47829729" />


- 🛠️ `data_job_skills`

    <img width="322" height="420" alt="data_job_skills applied steps" src="https://github.com/user-attachments/assets/85bcf897-8e5c-4a40-b757-7930448577c1" />


#### 🔗 Load

Both transformed queries were loaded into the workbook to support the analysis:

- 📊 `data_jobs_salary`

    <img width="1918" height="801" alt="power_query_both_queries" src="https://github.com/user-attachments/assets/350eb9df-59c2-41a5-8a15-5248c3582d87" />

- 🛠️ `data_job_skills`

    <img width="1918" height="860" alt="data_jobs_skills_power_query" src="https://github.com/user-attachments/assets/17c9b720-350a-4788-b4bd-ff72202203a5" />

---

### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills listed in job postings and the median salary — especially for roles like **Senior Data Engineer** and **Data Scientist**.
- 💼 Positions requiring fewer skills, such as **Business Analyst**, tend to offer lower salaries, indicating that specialized skill sets are often rewarded with higher compensation.

  <img width="957" height="622" alt="Do more skills get you better pay image" src="https://github.com/user-attachments/assets/3a741bc7-d1fe-428b-85a8-0f5f22581a58" />

#### 🤔 So What

This trend highlights the advantage of developing a broader skill set — particularly for professionals targeting higher-paying roles in data.


