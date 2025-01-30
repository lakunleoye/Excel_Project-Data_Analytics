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

### Dataset Used
This project utilised a real-world data science jobs data obtain from [Luke Barousse's Excel Course](https://www.youtube.com/watch?v=pCJ15nGFgVg). This include detailed information on the following:
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
 ![data_jobs_all](https://github.com/user-attachments/assets/d41300e2-9c23-4353-ae68-84a1b1a4670b)


- data_job_skills
![data_jobs_skills](https://github.com/user-attachments/assets/529d163a-3d7a-4b97-a794-d1f10c56bca8)


#### Load
The transformed queries were loaded into the workbook, setting the stage for subsequent analysis.
- data_jobs_all
![data_jobs_all mains](https://github.com/user-attachments/assets/1163ed6c-b485-46cf-8a8b-3e7ac787f35a)

- data_job_skills
![data_jobs_skills mains](https://github.com/user-attachments/assets/614bee34-9f1f-407a-947a-cf0b8815ded4)

### Analysis
#### Insights
- There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

![Skills per Job Vs Median Salary](https://github.com/user-attachments/assets/ac93a670-4fd3-4cf1-8baa-32a8f69cfa9e)

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

![Salary_Analysis](https://github.com/user-attachments/assets/cb5c7160-06e2-4609-98a0-306594ca8227)

#### **Implications**
- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3. What are the top skills of data professionals?
### Skill: Power Pivot
#### Power Pivot
- I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### Data Model
- I created a relationship between my two tables using the `job_id` column.

![Tables_Relationship](https://github.com/user-attachments/assets/2118d6f2-38b6-446f-80ae-2bffef112b53)


#### Power Pivot Menu
- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

![Power_Pivot_table](https://github.com/user-attachments/assets/f4ddd08e-b663-43b4-9b87-7fbc546af36a)


### Analysis

#### Insights
- SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- Cloud technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

![Top_skills](https://github.com/user-attachments/assets/a493f997-cc56-4b00-98eb-cdf649bac6e3)


#### Implication
- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4. What is the pay for the top 10 skills in Data Analytics?

### Skill: Advanced Charts (Pivot Chart)

#### Pivotchart

- A combo PivotChart was created by plotting the median salary and skill likelihood (%) from the PivotTable.
- **Primary Axis:** Median Salary (as a Clustered Column)
- **Secondary Axis:** Skill Likelihood(as a Line with Markers)
To customize the chart, I added a title axis, removed the lines (skill likelihood), and changed the markers to diamonds.
### Analysis

#### Insights
- Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

![Pay_of_top_10_skills](https://github.com/user-attachments/assets/8cc49439-4e75-49e3-a02d-c5c7ad9c2160)


### Implication
- The output shows the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion
As a job seeker, I conducted this study to understand the data science job market. Based on dataset from real-world job postings, I analyzed job titles, salaries, locations, and essential skills. The use of Excel features like Power Query, PivotTables, DAX, and charts, helped to discover key correlations between multiple skills and higher salaries, particularly Python, SQL, and cloud technologies. 










