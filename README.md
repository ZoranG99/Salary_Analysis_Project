# Data Skills vs Salary: An Excel-Powered Job Market Analysis Project

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

    <img width="240" height="296" alt="data_jobs_all applied steps" src="https://github.com/user-attachments/assets/ddf49cc6-2316-49ac-b6a7-602b47829729" />

- 🛠️ `data_job_skills`

    <img width="240" height="296" alt="data_job_skills applied steps" src="https://github.com/user-attachments/assets/85bcf897-8e5c-4a40-b757-7930448577c1" />

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

  <img width="771" height="500" alt="Do more skills get you better pay image" src="https://github.com/user-attachments/assets/3a741bc7-d1fe-428b-85a8-0f5f22581a58" />

#### 🗝️ Why It Matters

This trend highlights the advantage of developing a broader skill set — particularly for professionals targeting higher-paying roles in data.

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈 Pivot Table

- 🔢 Built a PivotTable using the Data Model created with Power Pivot.  
- 📊 Placed `job_title_short` in the Rows area and `salary_year_avg` in the Values area.  
- 🧮 Added a new measure to calculate the **median salary** for jobs in the United States:

    ```DAX
    =CALCULATE(
        MEDIAN(data_jobs_salary[salary_year_avg]),
        data_jobs_salary[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median annual salary across all roles, the following DAX measure was used:

    ```DAX
    Median Salary := MEDIAN(data_jobs_salary[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Roles such as Senior Data Engineer and Data Scientist offer higher median salaries both in the U.S. and internationally — a sign of consistent global demand for advanced data roles.
- 💰 There's a noticeable salary gap between U.S. and non-U.S. positions, especially in tech-centric roles, potentially reflecting the influence of the U.S. tech industry's size and demand.

    <img width="884" height="298" alt="median salaries table" src="https://github.com/user-attachments/assets/9d709d0c-4d0a-4508-bcef-9633fc018c49" />

#### 🗝️ Why It Matters

These findings can guide salary benchmarking and job search strategies by accounting for regional pay differences — crucial for both professionals and employers navigating a global talent market.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 Built a data model by integrating the `data_jobs_salary` and `data_jobs_skills` tables.  
- 🧹 Since the data had already been cleaned in Power Query, Power Pivot was able to automatically establish a relationship between the two tables.

#### 🔗 Data Model

- A relationship was created between the tables using the `job_id` column.

    <img width="698" height="564" alt="data model power pivot" src="https://github.com/user-attachments/assets/008a2f6a-f243-4ae7-be49-d08f680a661e" />


#### 📃 Power Pivot Menu

- The Power Pivot interface was used to refine the model and simplify the creation of new measures.

    <img width="1918" height="651" alt="power pivot menu" src="https://github.com/user-attachments/assets/aadc74b6-0d05-4959-a76f-21d1f89dba8a" />

---

### 📊 Analysis

#### 💡 Insights

- 💻 **SQL** and **Python** are by far the most commonly mentioned skills in data-related job postings, each appearing in over 50% of listings — highlighting their fundamental role in data work.
- 📊 Visualization and statistical tools like **Tableau** and **R** follow closely, reflecting their continued relevance in analytics.

  <img width="659" height="436" alt="what are the top skills of data nerds" src="https://github.com/user-attachments/assets/59cdbca8-54f3-46a9-b037-09590ea463c6" />

#### 🗝️ Why It Matters

Recognizing in-demand skills like SQL and Python helps professionals stay competitive and guides training efforts toward the most valuable technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (PivotChart)

#### 📈 PivotChart

- Created a combo PivotChart to visualize **median salary** and **skill likelihood (%)** based on PivotTable data.
    - 🪙 **Primary Axis:** Median Salary (Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (Line with Markers)
- Customizations included:
    - Adding axis titles and chart title  
    - Removing lines for skill likelihood  
    - Changing markers to diamonds for better visual clarity

### 📊 Analysis

#### 💡 Insights

- 💰 Top-paying skills like Spark, AWS, and Java offer median salaries over $130K, showing strong value in tech roles.
- 📈 Python, Azure, and SQL also rank high in both pay and demand, making them smart career investments.
- 📉 Excel and SAS trail in salary and demand, reflecting broader, less-specialized use.

  <img width="738" height="438" alt="what is the pay of the top 10 skills" src="https://github.com/user-attachments/assets/8f94a502-4726-45c6-b71a-30bb3fcba679" />

#### 🗝️ Why It Matters

This chart shows the value of learning high-impact skills like Python and SQL, which are closely tied to higher salaries. For anyone aiming to grow in tech or increase earnings, focusing on in-demand tools is a smart move.

## 🧾 Conclusion

As a data enthusiast and former job seeker, I developed this Excel-based project to explore meaningful trends in the data science job market. Using real-world job posting data, I analyzed roles, salaries, locations, and in-demand skills.

By leveraging Excel tools like **Power Query**, **PivotTables**, **DAX**, and **PivotCharts**, I uncovered clear correlations — especially between the number of skills listed and higher salaries. Skills such as **Python**, **SQL**, and cloud platforms stood out as key drivers of compensation.

I hope this project offers practical insights for aspiring and current data professionals, and serves as a useful reference for identifying the most valuable skills in today’s tech-driven job market.

