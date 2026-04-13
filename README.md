# Excel_Project-Data_Analysis

## Salary Dashboard
A dashboard to display the median salary and amount of jobs of data-related jobs by job type and country.

![1_Salary_Dashboard_Final_Dashboard](https://github.com/user-attachments/assets/5b55833f-e676-498a-9513-349d706725d9)

The data is from my Excel course, which provides a foundation in analyzing data using this powerful tool. The data contains detailed information on job titles, salaries, locations, and essential skills that are presented here. 

### Dashboard File

My final dashboard is in [Data_Analysis_Project1.xlsx](Data_Analysis_Project1.xlsx)

### Excel Skills Used
- 📈Charts
- 🧮Formulas and Functions
- ❎Data Validation

### Data Jobs Dataset 

The dataset used for this project contains real-world data science job information from 2023. The dataset is available via my Excel course, which provides a foundation for analyzing data using Excel. It includes detailed information on:

- 🧑🏻‍💼Job Titles
- 💰Salaries
- 📍Locations
- 🛠️Skills

## Dashboard Build 

### 📈Charts
📊Data Science Job Salaries - Bar Chart

<img width="1336" height="867" alt="1_Salary_Dashboard_Chart1" src="https://github.com/user-attachments/assets/3716e4e4-c734-4ab7-abd3-95b309c02878" />

- 🛠️**Excel Features**: Utilized bar chart feature(with formatted salary values) and optimized layout for clarity.
- 🎨**Design choice**: Horizontal bar chart for visual comparison of median salaries.
- 📉**Data Organization**: Sorted job titles by descending salary for improved readability.
- 💡**Insights Gained**: This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

### 🗺️Country Median Salaries - Map Chart

<img width="564" height="395" alt="1_Salary_Dashboard_Chart2" src="https://github.com/user-attachments/assets/78f72424-4b1f-42f4-9bf5-04989dfed924" />

- 🛠️**Excel Features**: Utilized Excel's map chart feature to plot median salaries globally. 
- 🎨**Design choice**: Color-coded map to visually differentiate salary levels across regions. 
- 📉**Data Representation**: Plotted median salary for each country with available data.
- 👁️**Visual Enhancements**: Improved readability and immediate understanding of geographic salary trends. 
- 💡**Insights Gained**: Enables quick grasp of global salary disparities and highlights high/low salary regions.

### 🧮Formulas and Functions 

💰**Median Salary by Job Titles**

``` python
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```
- 🔍**Multi-Criteria Filtering**: Checks job title, country, schedule type, and excludes blank salaries.
- 📊**Array Formula**: Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯**Tailored Insights**: Provides specific salary information for job titles, regions, and schedule types.
- 🔢**Formula Purpose**: This formula populates the table below, returning the median salary based on job title, country, and type.

🍽️Background Table 

<img width="265" height="220" alt="1_Salary_Dashboard_Screenshot1" src="https://github.com/user-attachments/assets/1654aebf-9022-441f-ae0d-45feecd15359" />

📉Dashboard Implementation 

<img width="1148" height="1214" alt="1_Salary_Dashboard_Job_Title" src="https://github.com/user-attachments/assets/5083aa2c-212d-471b-8a80-f9bcc0307753" />

⏰Count of Job Schedule Type

``` python
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#)))*(J2#<>0))
```
- 🔍**Unique List Generation**: This Excel formula above employs the `FILTER()` function to exclude  entries containing "and" or commas, and omit zero values.
- 🔢**Formula Purpose**: This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

<img width="195" height="119" alt="1_Salary_Dashboard_Screenshot2" src="https://github.com/user-attachments/assets/8d515819-d98a-4e23-86ec-5dfcb1d0b60f" />

📉 Dashboard Implementation

<img width="942" height="1212" alt="1_Salary_Dashboard_Type" src="https://github.com/user-attachments/assets/7afc8127-73fc-47eb-9408-101ae9fb8729" />

### ❎Data Validation

🔍Filtered List

  - 🔒**Enhanced Data Validation**: Implementing the filtered list as a data validation rule under the Job Title, Country, and Type option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 Overall usability of the dashboard is enhanced

![1_Salary_Dashboard_Data_Validation](https://github.com/user-attachments/assets/8784b548-37de-44a6-87cb-818eb27a7e76)

## Conclusion 

I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing data from my Excel course, this dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries.

