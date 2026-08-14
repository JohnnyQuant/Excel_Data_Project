# Excel Salary Analysis

## 🌎 Introduction

I have looked for jobs in data industry, but I found that little information about the best jobs and skills. Hence, I would like to understand what skills top employers request and how to get more pay.

### 🎯 Question to Analyze

To get more information about data job market, I asked these key questions:

* **What-if more skills lead to better pay?**

* **How much salary for data jobs in different countries?**

* **What are the top required skills for data occupation?**

* **How much do the top required skills pay?**

### 🖥️ Excel Skills Used

The following Excel skills were utilized for analysis:

* 📊 Pivot Tables
* 📈 Pivot Charts
* 🧮 DAX (Data Analysis Expressions)
* 🔍 Power Query
* 💪 Power Pivot

### 📦 Data Jobs Dataset

The dataset used for this project contains real‑world data job information from 2023. It is available through **Luke Barousse's** Excel course and serves as the foundation for analyzing salaries and skills using Excel.

It includes detailed information on:

* 🧑‍💻 Job Titles – covering a wide range of data roles (Analyst, Engineer, Scientist, etc.)

* 🌍 Countries & Regions – showing how salaries vary by location

* ⏰ Job Types & Schedules – such as full‑time, part‑time, and contract positions

* 💰 Salary Data – median salaries for different roles and regions

* 🎯 Skills Required – highlighting the top skills employers request in the data science market

## 1️⃣ What-if more skills get you better pay?

### 🛠️ Skill: Data Preparation with Power Query (ETL)

#### 📥 Extract

I first used Power Query to extract the original dataset (data_salary_all.xlsx) and created two queries:

* 🗃️ **Full Data Jobs Query** – containing all job information from the dataset.

* 🔧 **Skills Query** – listing the skills associated with each job ID.

This step ensured the data was clean, structured, and ready for deeper analysis in Excel.

#### 🎯 Transform

* After extracting the queries, I transformed each one to make the dataset clean and ready for analysis. The steps included:

* 🔢 **Changing column types** – ensuring numbers, text, and dates were in the correct format.

* 🗑️ **Removing unnecessary columns** – keeping only the data relevant for analysis.

* ✂️ **Cleaning text** – eliminating specific unwanted words.

* ⚡ **Trimming whitespace** – removing extra spaces for consistency.

* These transformations helped standardize the dataset and improved accuracy for later analysis with PivotTables, charts, and DAX.

    * 🗂️ data_jobs_all

![data_job_all](/Images/ETL_Query.png)

    * 🗂️ data_jobs_skills

![data_job_skills](/Images/ETL_Query2.png)

#### 📤 Load

* Finally, I loaded both transformed queries into the Excel workbook. This step set the foundation for all subsequent analysis, ensuring that the data was clean, structured, and ready to be explored with PivotTables, charts, and DAX.

    * 🗂️ data_jobs_all

![data_job_all](/Images/data_job_all.png)

    * 🗂️ data_jobs_skills

![data_job_all](/Images/data_job_skills.png)

### 📊 Analysis

#### 💡 Insights

* 📈 There is a clear positive correlation between the number of skills requested in job postings and the median salary. Roles such as **Senior Data Engineer** and **Data Scientist** show the strongest impact.

* 💼 Positions that require fewer skills, like **Business Analyst**, tend to offer lower salaries. This suggests that more specialized and technical skill sets command higher market value in the data science job market.

![insight_analysis](/Images/project_2.png)

#### 🤔 Why It Matters

* This trend highlights the importance of building a diverse and relevant skill set. 

* For professionals aiming at higher‑paying roles, acquiring multiple in‑demand skills—especially technical ones—can significantly increase market value and career opportunities.

## How much salary for data jobs in different countries?

### 🧮 Skills: PivotTables & DAX

#### 📈 Pivot Table

* 🔢 **Data Model** - I created a PivotTable using the Data Model built with Power Pivot.

* 🔢 **Setup** - I placed `job_title_short` in the Rows area and `salary_year_avg` in the Values area to summarize average salaries by role.

* 📊 **Median Salary Measure** - Then, I added a new DAX measure to calculate the median salary specifically for jobs located in the United States.

```DAX
=CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg])
    , data_jobs_all[job_country] = "United States")
```

#### 🧮 DAX

* 🧮 **Median Salary Calculation with DAX** - To calculate the median yearly salary, I used DAX to create an explicit measure within the Data Model

```DAX
Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
```

### 📊 Analysis

#### 💡 Insights

* 💼 **High‑level roles** such as *Senior Data Engineer* and *Data Scientist* command higher median salaries both in the US and internationally, reflecting the strong global demand for advanced data expertise.

* 💰 **Salary disparities** between US and non‑US roles are most evident in high‑tech positions. This gap may be influenced by the concentration of technology industries and competitive markets in the United States.

![pivot_analysis](/Images/pivot_analysis.png)

#### 🤔 Why It Matters

* These salary insights are crucial for both professionals and employers.

* They provide a solid basis for **career planning** and **salary negotiations**, helping individuals understand the value of their skills while guiding companies to align compensation packages with market standards. 

* Importantly, they also highlight how **geographical variations** can influence pay, reminding professionals to consider location when evaluating opportunities.

## 3️⃣ What are the top required skills for data occupation?

### 🔧 Skill: Power Pivot

* 💪 **Power Pivot** - I built a data model by integrating the data_jobs_all and data_jobs_skills tables into a single model.

* 🧹 **Clean Data Integration** - Since the data had already been cleaned using Power Query, Power Pivot was able to automatically establish relationships between the two tables.

### 🔗 **Data Model Relationship** 

* 🗃️ I explicitly created a relationship between the two tables using the job_id column, ensuring that job information and associated skills were properly linked for analysis.

![data_model](/Images/data_model.png)

#### 📃 Power Pivot

![power_pivot](/Images/power_pivot.png)

### 📊Analysis

#### 💡 Insights

* 💻 **Core Skills:**
SQL and Python continue to dominate as the top skills in data‑related jobs, reflecting their foundational role in data processing, analysis, and automation.

* ☁️ **Cloud & Emerging Tech:**
Technologies like AWS and Azure show a strong presence, underlining the industry’s shift towards cloud services and big data platforms. This trend highlights the growing importance of cloud expertise alongside traditional programming skills.

![pivot_chart](/Images/top10_skill_p2.png)


#### 🤔 Why It Matters

* Understanding prevalent skills in the industry not only helps professionals stay competitive, but also guides training programs and educational curricula to focus on the most impactful technologies.

* This alignment ensures that individuals develop the right expertise while organizations and schools invest in teaching skills that truly drive career growth and industry innovation.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 **Skill: Advanced Charts (PivotChart)**

* 📈 **PivotChart Creation**  
I built a combo PivotChart to visualize both median salary and skill likelihood (%) from my PivotTable.

* 🪙 **Chart Setup**

    * **Primary Axis:** Median Salary (Clustered Column)

    * **Secondary Axis:** Skill Likelihood (Line with Markers)

    * **Customization:** Added chart and axis titles, removed connecting lines for skill likelihood, and changed markers to diamond shapes for clarity.

### 📊 **Analysis & Insights**

* 💰 Higher median salaries are strongly associated with technical skills like **Python, Oracle, and SQL**, highlighting their critical role in high‑paying tech jobs.

* 📉 Skills such as **PowerPoint and Word** show the lowest median salaries and likelihood, indicating limited specialization and lower demand in high‑salary sectors.

![pivot_chart](/Images/top10_skills_p2.png)

#### 🤔 Why It Matters

* This chart highlights the importance of investing time in learning **high‑value skills** such as **Python** and **SQL**, which are consistently tied to higher‑paying roles. 

* For professionals aiming to maximize their salary in the tech industry, focusing on these in‑demand skills can significantly boost career opportunities and earning potential.

---

## 📑 Conclusion

As a data enthusiast and being a job seeker, this Excel‑based project gave me the chance to explore the data science job market in depth. By analyzing real‑world job postings from 2023, I uncovered insights into job titles, salaries, locations, and the most in‑demand skills.

With **Excel** tools like **Power Query**, **PivotTables**, **DAX**, and charts, I was able to reveal clear correlations between multiple skills and higher salaries—especially in **Python**, **SQL**, and **Cloud Technologies**.
