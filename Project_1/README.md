<h1 align="center"> 🧮 Excel Salary Dashboard </h1>

![Excel Dashboard](/Gifts/Project_1/Excel%20Dashboard.png)

## 📇 Introduction

The dashboard was created with the purpose of helping job seekers identify the **Salary**, the **Top Platform** where the most job offers are posted, and the **Count** of available jobs. These insights can be explored based on the **Job Title**, **Country** of the search, and the **Job Type** (Full-time, Part-time, etc.) in 2025.

### Dashboard File 📈

Here you will find the final dashboard of the project to interact with it [- Final Dashboard -](/Project_1/Project_1_Final.xlsx)

### Excel Skills Used 🧑‍💻

For the **Project** analysis, the following Excel skills were used:

- Charts (to visualize the data) 📊
- Formulas and Functions (to perform calculations and data analysis) 🧭
- Data Validation (to control and restrict the type of data entered) ✅

### Data Jobs Dataset 💾
The dataset used in this project contains real-world job posting data from 2025. The dataset is available through Luke Barousse’s platform (datanerd.tech).

It provides valuable information that can be analyzed using Excel to explore different aspects of the data job market, including:

- Job Titles 💼

- Salaries (hourly and yearly) 💰

- Location (country) 🌍 

- Skills required for data positions 🧠

## ⚙️ Dashboard Build

### Charts 📉
### - Data Jobs Salaries - Bar Chart

![Data jobs salaries](/Gifts/Project_1/Data%20Job%20Salaries%20-%20Bar%20Chart.png)
#### - Excel Features ⚙️
A horizontal bar chart was used, with salary values properly formatted and the layout optimized to enhance readability and clarity.
#### - Design choice ✏️
A horizontal bar chart was selected to improve the visualization of salaries across different data roles, making comparisons easier.
#### - Data Organization 🗂️
The data was organized in descending order based on the median salary for each data role, improving readability and enabling faster identification of the highest-paying positions.
#### - Insights Gained 🌐
From the chart, we can identify salary trends across different data roles. Senior positions and Data Scientists receive the highest median salaries, while Analyst roles tend to have comparatively lower compensation.

### - Country Median Salaries - Map Chart
![Country Median Salaries](/Gifts/Project_1/Countries%20Median%20Salaries%20-%20Map%20Chart.gif)
#### - Excel Features ⚙️
A map chart was used to visualize the median salaries across different countries based on the locations of job postings.
#### - Design choice ✏️
A color-coded map was implemented to highlight salary differences across regions. Darker shades represent higher median salaries, enabling clear visual comparison between countries. 
#### - Insights Gained 🌐
The visualization allows for quick identification of salary levels by country. By observing the color intensity, it becomes easy to detect regional disparities and identify the countries offering the highest salaries.

### Formulas and Functions 🤖
#### Median Salary by Job Titles 💰
```excel
=MEDIAN(
    IF(
        (Job_Information[job_title_short]=A2)*
        (Job_Information[salary_year_avg]<>0)*
        (Job_Information[job_country]=country)*
        (ISNUMBER(SEARCH(type;Job_Information[job_schedule_type])));
        Job_Information[salary_year_avg]
    )
)
```
#### - Multi-Criteria Filtering: ⚙️
The formula applies multiple criteria to calculate the median salary. It first checks the job title, then ensures the salary value is not zero (i.e., not a null value). Next, it verifies the selected country and finally filters by job type (e.g., Full-time, Part-time).
#### - Array Formula ✏️
The **MEDIAN()** function is used together with **IF()** conditions to filter the data and calculate the median salary for the specified job title, selected country, and job type.
#### - Tailored Insights 🌐
We are able to get the specific salary information for the selected country, job type and job title (on the main Dashboard).
#### - Formula Purpose #️⃣
The formula generates the table below by returning the median salary based on the selected job title, job type, and country, filtering the dataset to include only valid salary values.

#### - Background Table 📋

![Back Ground Table 1](/Gifts/Project_1/Background%20table.png)

#### - Dashboard Implementation 🖥️

![Dashboard Implementation 1](/Gifts/Project_1/Dashboard%20Implementation.gif)

#### Count of Schedule Type 🕒
```excel
=UNIQUE(Job_Information[job_schedule_type])
```
```excel
=FILTER(L2#;(ISNUMBER(SEARCH("and";L2#))=FALSE)*(L2#<>0))
```
- #### Unique List Generation 📝:
First we used the function **UNIQUE()** to get all the job types on our information and then **FILTER()** is used to exclude entries that contain "and" or commas alongside omitting zero values.

#### - Formula Purpose #️⃣
The formulas populate the table below, which give us a unique list of job schedule type clean up.
 
- #### Background Table 📋

![Back Ground Table 2](/Gifts/Project_1/Job%20Type%20Table.png)

- #### Dashboard Implementation 🖥️

![Dashboard Implementation 2](/Gifts/Project_1/Dashboard%20Implementation%202.gif)


### Data Validation 📡

- #### Filtered List - Data Validation 📝
In the dashboard, Excel’s Data Validation feature was implemented using three dropdown lists: **Job Title**, **Job Country**, and **Job Type**.

This restricts user input to predefined values, preventing incorrect or inconsistent entries while improving the overall usability, accuracy, and efficiency of the dashboard.

![Data Validation](/Gifts/Project_1/Data%20Validation.png)

## 📍 Conclusion
I created this dashboard to present salary trends across different data roles. The objective of the project was also to apply various Excel skills to enable users to explore the data and support career decision-making.

Through the dashboard, users can analyze **Median Salaries** across roles, identify the **Top Platforms** where job postings are most commonly listed, and review **Job Types** to understand the number of opportunities available based on schedule availability (e.g., full-time, part-time).

