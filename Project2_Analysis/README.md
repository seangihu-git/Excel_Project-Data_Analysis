# Project 2 Analysis

## Introduction

As a former job seeker, I’ve always been surprised by the lack of data exploring the most optimal jobs and skills in the data science market. I set out to understand what skills top employers request and how to land more pay.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset is available via my Excel course, which provides a foundation for analyzing data using Excel. 

It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    - 🗃️ First one with all the data jobs information.
    - 🔧 The second listing the skills for each job ID.

#### 🔄 Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    - 📊 data_jobs_all

  <img width="244" height="312" alt="2_Project_Analysis_Screenshot1" src="https://github.com/user-attachments/assets/3d0aabae-c9f0-4fd8-9738-d7234344c6c4" />

    - 🛠️ data_jobs_skills

  <img width="243" height="328" alt="2_Project_Analysis_Screenshot2" src="https://github.com/user-attachments/assets/0a47d5d0-350d-4253-86b1-3d9a7f9c9899" />

#### 🔗 Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    - 📊 data_jobs_all
 
  <img width="1916" height="649" alt="2_Project_Analysis_Screenshot3" src="https://github.com/user-attachments/assets/5fb3be6f-9226-47a9-92df-683e573dc638" />

    - 🛠️ data_job_skills

  <img width="1914" height="702" alt="2_Project_Analysis_Screenshot4" src="https://github.com/user-attachments/assets/98ad8e80-8a16-4c9a-9158-e1358400d4aa" />

### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

<img width="874" height="537" alt="2_Project_Analysis_Chart1" src="https://github.com/user-attachments/assets/463bf80e-2392-42a3-90c7-7d6f851fe64f" />

#### 🤔 So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 Then I added new measure to calculate the median salary for United States jobs.

    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

<img width="1776" height="738" alt="2_Project_Analysis_Chart2" src="https://github.com/user-attachments/assets/226f67d6-dc26-4755-895b-4e2142f16412" />

#### **🤔 So What**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

<img width="1788" height="1264" alt="2_Project_Analysis_Screenshot5" src="https://github.com/user-attachments/assets/fddfc1fd-2dec-463f-9ebd-9faba61adad1" />

#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

<img width="1918" height="742" alt="2_Project_Analysis_Screenshot6" src="https://github.com/user-attachments/assets/3fd20d15-a250-419d-b5ae-274b1cec0aba" />

### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

<img width="759" height="513" alt="2_Project_Analysis_Chart3" src="https://github.com/user-attachments/assets/a28b3ac3-48b8-45b9-8818-915b26114324" />

#### 🤔So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

<img width="862" height="452" alt="2_Project_Analysis_Chart4" src="https://github.com/user-attachments/assets/e5321e28-edad-4cb1-989c-7543fff7f7f1" />

### 🤔So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

I embarked on this Excel-based project to uncover valuable insights about the data science job market. Using a dataset provided to me by my Excel course, I analyzed job titles, salaries, locations, and essential skills. By leveraging Excel features like Power Query, PivotTables, DAX, and charts, I discovered key correlations between multiple skills and higher salaries, particularly in Python, SQL, and cloud technologies. 

I hope this project serves as a practical guide for data professionals and provides an overview of the skills needed for higher-paying roles.
