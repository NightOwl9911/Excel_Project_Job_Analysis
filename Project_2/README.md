<h1 align="center"> ⚡ Job Analysis using Power Query and Power Pivot </h1>

![Excel Dashboard](/Gifts/Project_2/Excel%20Power%20Query%20Pivot.gif)

## 🗂️ Introduction
Many times while researching the skills required to become a Data Analyst or Data Scientist, I found myself wondering which tools I should focus on learning—whether I should prioritize Tableau, Power BI, or both.

In this project, you will be able to identify the key skills and tools required for roles such as Data Analyst, Data Scientist, Data Engineer, and other data-related positions. The goal is to better understand the job market and focus on learning the most relevant technologies to move faster toward your career objective (in my case, becoming a Data Scientist).

### Analysis File 🗄️
Here you will find the final outcome of the project to interact with it [- Job Analysis PQ / PP -](/Project_2/Project_2_Final.xlsx)


### Questions to Analyze 🧐
For this project, we formulated the following question to better understand the data job market:
#### 1. Does having a broader set of skills lead to obtaining a job with higher income potential? 🛠️📈
#### 2. What are salaries like across different countries compared to those in the United States and globally? 🌍💰
#### 3. What are the top 10 skills required for data roles, and how frequently are they requested in job postings? 📊🔎
#### 4. What are the salary levels associated with the top 10 skills in data roles? 🧠💰

### Excel Skills Used 🧾
In the project, the following Excel skills were used:
#### - Pivot Tables 📋
#### - Pivot Charts 📉
#### - DAX (Data Analysis Expressions) 🧠
#### - Power Query 🔍
#### - Power Pivot 🔗


### Data Jobs Dataset 💿
The dataset used in this project contains real-world job posting data from 2025. The dataset is available through Luke Barousse’s platform (datanerd.tech).

It provides valuable information that can be analyzed using Excel to explore different aspects of the data job market, including:

- Job Titles 💼

- Salaries (hourly and yearly) 💰

- Location (country) 🌍 

- Skills required for data positions 🧠

## ☝️ Do more skills get you better pay?

###  Skill Used: Power Query 🔍

 **Load** 🔄

- First I uploaded the information of the **Data Jobs Dataset** (Data 2025) by using the Power Query option (From CSV).

 **Extract** 🧲
- Then I extracted the information from the CSV file and created the two queries for the project (**Data 2025** and **Data Skills**).
    - **Data 2025** comes from the CSV File, and then for the creation of **Data Skills**, the job_id column was used to list the skills the specific job requested.

 **Transform** 🔧
- Subsequently, each query was transformed by adding a reference (index - job_id) column, removing unnecessary columns, renaming fields for better clarity, cleaning null values, reshaping column values, and trimming excess whitespace.
    - Data 2025

        ![Transformation steps - Data 2025](/Gifts/Project_2/Transformation%20-%20Data%202025.png)
    - Data Skills

        ![Transformation steps - Data Skills](/Gifts/Project_2/Transformation%20-%20Data%20Skills.png)

**Load to Excel Workbook** 📗
- Finally, the transformed queries were loaded into the Excel workbook to begin the analysis for the project.
    - Data 2025

        ![Transformation load - Data 2025](/Gifts/Project_2/Transformation%20-%20Load%20-%20Data%202025.gif)

    - Data Skills

        ![Transformation load - Data Skills](/Gifts/Project_2/Transformation%20-%20Load%20-%20Data%20Skills.gif)

### Analysis 📊


![Analysis Question 1](/Gifts/Project_2/Analysis_Question_1.png)

## ✌️ What’s the salary for data jobs in different regions?

###  Skill Used: Power Query 🧮

- The PivotTable used to answer the question was created using the Data Model built in Power Pivot.

- I used the column `job_title_short` to the rows area to get the different **Data Roles**  and then I proceed to calculate a new measure for the median salary by jobs using the model in **Power Pivot** and I put them into the values area.

    ![Median Salary](/Gifts/Project_2/Median%20Salary.png)

- **DAX to calculate the median salary (general)**

```excel
Median Salary:=MEDIAN('Data - 2025'[salary_year_avg])
```

- Then, for our analysis, I calculated the value for the median salary by job title on the US and Non-Us (all information outside the US) by creating a new measure for each one.

![New Measure](/Gifts/Project_2/New%20Measure.png)


- **DAX to calculate the median salary in the US**
```excel
=CALCULATE([Median Salary];'Data - 2025'[job_country]="United States")
```

- **DAX to calculate the median salary outside the US**

```excel
=CALCULATE([Median Salary];'Data - 2025'[job_country]<>"United States")
```
### Analysis 📊

![Analysis Question 2](/Gifts/Project_2/Analysis_Question_2.gif)

## 🤟 What are the top skills of data professionals?

###  Skill Used: Power Pivot 🧩
- A **Data Model** was created by using the queries transformed and loaded in Power Query (Data 2025 and Data Skills) into one model.
- Since we have already cleaned up the tables/queries, we were able to create a relationship by using job_id as the foreign key.

![Data Model](/Gifts/Project_2/Data%20Model.png)

- The Power Pivot menu was used to enhance the data model and simplify the creation of measures, such as the previously calculated Median Salary.

![Power Pivot Menu](/Gifts/Project_2/Power%20Pivot%20Menu.png)

### Analysis 📊

![Analysis Question 3](/Gifts/Project_2/Analysis_Question_3.png)


## 🖖 What’s the pay of the top 10 skills?

###  Advanced Charts (Pivot Charts) 🖥️

- A combo chart was created from a PivotTable to visualize both the median salary and the likelihood (%) of each skill, supporting the analysis.
    - **Primary Axis**: Used to represent the median salary of each skill - **As a clustered column** -
    - **Secondary Axis**: Used to represent the likelihood (%) for an skill to appeared in a Job Posting - **As a line with markers** -
    - We formatted and customized the line chart by removing the line and increasing the size of the markers, so we only see the points on the likelihood of skills in diamond shape.

### Analysis 📊

![Analysis Question 4](/Gifts/Project_2/Analysis_Question_4.png)

## 📢 Conclusion

The project was developed with the goal of uncovering valuable insights from the data job market by leveraging the powerful tools available in Excel. Through this analysis, I examined salaries, locations, and key skills required to pursue roles such as Data Scientist and other data-related positions.

The analysis revealed that core skills across most data roles include Python and SQL, while additional skills tend to vary depending on the specific role within the data field. Overall, this project serves as a practical guide for aspiring and current data professionals to better understand the skills associated with higher-paying roles in the industry.




