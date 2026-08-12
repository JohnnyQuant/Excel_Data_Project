# Excel Salary Dashboard

![Salary_Dashboard](/Images/project_1.gif)

## 📝 Introduction

Welcome to my project, this salary dashboard of data jobs instructed by **Luke Barousse**, it was designed to help job seekers explore pay levels and check if they are being fairly compensated.

The dataset comes from Luke Barousse's Excel course, who taught me the basics of analyzing information with this powerful tool. It includes detailed insights on job titles, salaries, locations, and key skills—all presented clearly in this dashboard.

### 📊 Dashboard File

My dashboard file: [Dashboard_File](/Project_1/Salary_Analysis_Dashboard.xlsx)

### 🛠️ Excell Skills Used

The following Excel skills were utilized for analyzing this dashboard:

- 📉 Charts
- 🧮 Formulas and Functions
- ❎ Data Validation

### 🗂️ Data Jobs Dataset

The dataset for this project contains real job information about data science positions from 2025. It is provided through Luke Barousse's Excel course, which can help learners build a strong foundation in analyzing data with Excel. The dataset includes detailed information such as:

- 👨‍💼 Job titles

- 💰 Salaries

- 📍 Locations

- 🛠️ Essential skills

## 💻 Dashboard Build

### 📈 Charts

**📊 Data Job Salaries - Bar Chart**

![Data_Job_Salaries](/Images/column_chart.png)

- 🛠️ **Excel Features**: Used bar chart with formatted salary values and optimized layout for clarity.

- 🎨 **Design Choice**: Horizontal bar chart selected for easy visual comparison of median salaries.

- 📉 **Data Organization**: Job titles sorted by descending salary to improve readability.

- 💡 **Insights Gained**: Quickly highlights salary trends, showing that Senior roles and Engineers earn more than Analyst positions.

**🗺️ Country Median Salaries - Map Chart**

![Country_Median_Salaries](/Images/map.xlsx-Excel-2026-08-12-12-39-30.gif)

- 🛠️ **Excel Features**: Used Excel's map chart to plot median salaries worldwide.

- 🎨 **Design Choice**: Applied color-coded map to visually distinguish salary levels across regions.

- 📊 **Data Representation**: Displayed median salary for each country with available data.

- 👁️ **Visual Enhancement**: Enhanced readability and allowed quick understanding of geographic salary trends.

- 💡 **Insights Gained**: Reveals global salary disparities, highlighting regions with higher or lower pay.

### 🧮 Formulas and Functions

**💰 Median Salary by Job Titles, Country and Schedule Type**

```Excel
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)
    *(jobs[job_country]=country)
    *(ISNUMBER(SEARCH(type,jobs[job_schedule_type])))
    *(jobs[salary_year_avg]<>0)
   ,jobs[salary_year_avg]
    )
)
```

- 🔍 **Multi-Criteria Filtering**: Checks job title, country, schedule type, and excludes blank salaries.

- 📊 **Array Formula**: Uses MEDIAN() with nested IF() to analyze an array.

- 🎯 **Tailored Insights**: Provides specific salary details by job title, region, and schedule type.

- 🔢 **Formula Purpose**: Populates the table below, returning the median salary based on the selected job title, country, and type.

**🍽️ Table in Excel File**

![Table](/Images/job_title_table.png)

**📉 Dashboard Presentation**

![Visualization](/Images/job_title.png)

**⏰ Count of Job Schedule Type**

```Excel
=FILTER(
    J2#
    ,(NOT
        (ISNUMBER(SEARCH("and",J2#))
        +ISNUMBER(SEARCH(",",J2#))))
    *(J2#<>0))
```

- 🔍 **Unique List Generation**: Uses the FILTER() function to exclude entries containing "and" or commas, and omits zero values.

- 🔢 **Formula Purpose**: Populates the table below with a clean list of unique job schedule types.

**🍽️ Table in Excel File**

![Table](/Images/job_schedule_type_table.png)

**📉 Dashboard Presentation**

![Visulization](/Images/job_type.png)

### 📑 Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation**: Applied the filtered list as a data validation rule under Job Title, Country, and Type in the Data tab. This ensures:
  - 🎯 **Restricted Input**: User entries are limited to predefined, validated schedule types.

  - 🚫 **Error Prevention**: Incorrect or inconsistent inputs are blocked.

  - 👥 **Improved Usability**: Overall dashboard experience is more reliable and user-friendly.

## 🎯 Conclusion

I was intructed to build this dashboard to highlight salary trends across different data‑related job titles. It could help users make smarter choices about their career paths. The dashboard also shows how factors like location and job type can influence salaries, making the insights clear and practical.
