# Excel Salary Dashboard

![Salary_Dashboard](https://github.com/user-attachments/assets/183ac263-7bfd-4318-b560-05cdb1fd4e7c)

## Introduction
I created a jobs salary dashboard to help me and other job seekers investigate salaries for desired jobs and adequate compensation. 
This project used a real-world data science jobs data obtain from [Luke Barousse's Excel Course](https://www.youtube.com/watch?v=pCJ15nGFgVg). It provides a foundation in analyzing data using Excel. The data contains detailed information on job titles, salaries, locations, and essential skills.

### Dashboard File

The dashboard file is available in [1_Salary_Dashboard.xlsx](https://github.com/user-attachments/files/18483093/1_Salary_Dashboard.xlsx)


### Skills Used for the Project
These are the Excel skills used for the analysis;
- **Charts**
- **Formulas and Functions**
- **Data Validation**

### Datasets used for the project
The dataset used for the project contains real-world data science job information from 2023. It includes detailed information on:

- **Job titles**
-  **Salaries**
-  **Locations**
-  **Skills**
## Dashboard Build
### Charts
#### Data Science Job Salaries - Bar Chart

![Job_Title](https://github.com/user-attachments/assets/cdfc842b-86fc-411e-bf61-c838cab8c8be)

- **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- **Data Organization:** Sorted job titles by descending salary for improved readability.
- **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### Country Median Salaries - Map Chart

![Map_Chart](https://github.com/user-attachments/assets/f158a123-4d22-4e3f-89be-a9d350163bd2)

- **Excel Features:** Excel's map chart feature was used to plot median salaries globally.
- **Design Choice:** Color-coded map was used to visually differentiate salary levels across regions.
- **Data Representation:** Median salary were plotted for each country based on available data.
- **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### Formulas and Functions

#### Median Salary by Job Titles
```
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
- **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

Background Table

![Background Table](https://github.com/user-attachments/assets/99dc56f6-2a21-4a14-a4d8-69792c8efd0e)

Dashboard Implementation

![Job_Title](https://github.com/user-attachments/assets/b45d62f9-05fe-459a-83f3-09590f2cbcf0)

#### Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```
- **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

Background Table

![Background Table_2](https://github.com/user-attachments/assets/10900c45-352f-4b13-a54a-84daf6ae39b8)

Dashboard Implementation

![Type](https://github.com/user-attachments/assets/0975cfdf-d880-451f-8f5c-5034a5d0efd5)

### Data Validation

#### Filtered List

- **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - User input is restricted to predefined, validated schedule types
    - Incorrect or inconsistent entries are prevented
    - Overall usability of the dashboard is enhanced
 
## Conclusion

This dashboard was created to showcase insights into salary trends across various data-related job titles. This dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries. 
  

