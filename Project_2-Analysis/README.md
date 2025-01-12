# Salary Analysis
## Introduction
 Studies exploring the most optimal jobs and skills in the Data Analytics discipline are very rare. Here, I investigated what skills top employers request and how to land higher pay. 
[Check out my work here](Project_2-Analysis)

### Key Research Questions
1. **Do more data analytics skills get you better pay?**
2. **What is the salary for data analytics jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What is the pay for the top 10 skills in Data Analytics?**

#### Skills Applied in the Project
The project mainly used the following Excel skills
-**Pivot Tables**
-**Pivot Charts**
-**DAX(Data Anlysis Expressions)**
-**Power Query**
-**Power Pivot**

###Dataset Used
This project utilised a real-world data science jobs data obtain from Luke Barousse's Excel Course (https://www.youtube.com/watch?v=pCJ15nGFgVg). This include detailed information on the following:
-**Job titles**
-**Salaries**
-**Locations**
-**Skills**

## 1. Do more data analytics skills get you better pay?
### Skill: Power Query(ETL)
#### Extract
I started by using Power Query to extract the original data (`data_salary_all.xlsx`) and created two queries:
- First with all the data jobs information
- Second one with listing the skills for each job ID
#### Transform
Each query was tranformed by changing the column types, removing unnecessary column,cleaning text to eliminate specific words, and triming excess whitespace.
- data_jobs_all

- data_job_skills

#### Load
The transformed queries were loaded into the workbook, setting the stage for subsequent analysis.
- data_jobs_all

- data_job_skills


### Analysis
#### Insights
- There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

#### Implications
This shows the value of acquiring multiple relevant skills, especially for those who want higher paying roles.

## 2. What is the salary for data analytics jobs in different regions?
### Skills: PivotTables and DAX
#### Pivot Table
- I created a PivotTable using the Data Model I created with Power Pivot.
- I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- Then I added new measure to calculate the median salary for United States jobs.
   ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```
#### DAX
- To calculate the median year salary I used DAX.
    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```
### Analysis
#### Insights
- Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

#### **Implications**
- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## What are the top skills of data professionals?
### Skill: Power Pivot
#### Power Pivot
- I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### Data Model
- I created a relationship between my two tables using the `job_id` column.

#### Power Pivot Menu
- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

### Analysis

#### Insights



