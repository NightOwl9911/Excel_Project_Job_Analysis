<h1 align="center"> ⚡ Job Analysis using Power Query and Power Pivot </h1>

![Excel Dashboard](/Gifts/Project_2/Excel%20Power%20Query%20Pivot.png)

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

        ![Transformation load - Data 2025](/Gifts/Project_2/Transformation%20-%20Load%20-%20Data%202025.png)

    - Data Skills

        ![Transformation load - Data Skills](/Gifts/Project_2/Transformation%20-%20Load%20-%20Data%20Skills.png)

### Analysis 📊

✨ **Insights**

- The analysis shows a positive relationship between the number of skills requested in job postings and the median salary. Roles that require a broader set of skills tend to offer higher salaries.

- Positions such as Business Analysts and Data Analysts generally offer lower salaries, which is partly associated with the smaller number of skills typically required for these roles.

- The highest-paying roles tend to demand a more extensive skill set, particularly positions such as Senior Data Engineers and Data Scientists.

![Analysis Question 1](/Gifts/Project_2/Analysis_Question_1.png)

🎯 **Implication**

- The analysis shows that developing a broader set of complementary skills can help individuals qualify for and secure higher-paying roles, particularly when those skills align with the requirements of a specific data-related position.

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

✨ **Insights**
- Data roles such as Senior Data Engineer and Senior Data Scientist lead the field with the highest median salaries both in the United States and globally, highlighting the demand for advanced data expertise.

- The analysis also shows that salaries in the United States tend to be higher overall, making it an attractive location to pursue data-related roles, particularly in high-tech and senior-level positions such as Data Scientists and Senior roles.


![Analysis Question 2](/Gifts/Project_2/Analysis_Question_2.png)

🎯 **Implication**

- The analysis helps inform salary negotiations by enabling professionals and employers to adjust their expectations and offers based on market standards, while also considering geographical differences.

## 🤟 What are the top skills of data professionals?

###  Skill Used: Power Pivot 🧩
- A **Data Model** was created by using the queries transformed and loaded in Power Query (Data 2025 and Data Skills) into one model.
- Since we have already cleaned up the tables/queries, we were able to create a relationship by using job_id as the foreign key.

![Data Model](/Gifts/Project_2/Data%20Model.png)

- The Power Pivot menu was used to enhance the data model and simplify the creation of measures, such as the previously calculated Median Salary.

![Power Pivot Menu](/Gifts/Project_2/Power%20Pivot%20Menu.png)

### Analysis 📊

✨ **Insights**
- The analysis shows that SQL and Python are fundamental skills for most data roles, serving as the core foundation for data processing and analysis.

- Cloud technologies such as AWS and Azure are increasingly important and are becoming essential skills for many data-related positions.

- Data analysis and visualization tools such as Excel, Power BI, and Tableau are also in high demand, as it is important not only to process and analyze data but also to effectively communicate insights and results.

![Analysis Question 3](/Gifts/Project_2/Analysis_Question_3.png)

🎯 **Implication**

- The analysis allows us to identify the core skills that data professionals should focus on, as well as emerging technologies that are becoming increasingly important. This helps professionals stay aligned with industry trends and continue developing relevant skills.

## 🖖 What’s the pay of the top 10 skills?

###  Advanced Charts (Pivot Charts) 🖥️

- A combo chart was created from a PivotTable to visualize both the median salary and the likelihood (%) of each skill, supporting the analysis.
    - **Primary Axis**: Used to represent the median salary of each skill - **As a clustered column** -
    - **Secondary Axis**: Used to represent the likelihood (%) for an skill to appeared in a Job Posting - **As a line with markers** -
    - We formatted and customized the line chart by removing the line and increasing the size of the markers, so we only see the points on the likelihood of skills in diamond shape.

### Analysis 📊

✨ **Insights**

- Skills such as Python, SQL, AWS, and Excel are not only highly demanded in data roles but are also associated with higher median salaries. This makes them both core competencies to learn and attractive from a salary perspective, highlighting their critical importance in data-related positions.

- Cloud and big data technologies such as Spark, AWS, Snowflake, and Azure are linked to some of the highest salaries while also appearing frequently in job postings. This combination of strong salary potential and high demand makes them essential skills for many data roles.

![Analysis Question 4](/Gifts/Project_2/Analysis_Question_4.png)

🎯 **Implication**

- The analysis helps professionals identify not only the essential skills needed to secure a data-related role, but also those that offer the greatest potential for higher income.

## 📢 Conclusion

The project was developed with the goal of uncovering valuable insights from the data job market by leveraging the powerful tools available in Excel. Through this analysis, I examined salaries, locations, and key skills required to pursue roles such as Data Scientist and other data-related positions.

The analysis revealed that core skills across most data roles include Python and SQL, while additional skills tend to vary depending on the specific role within the data field. Overall, this project serves as a practical guide for aspiring and current data professionals to better understand the skills associated with higher-paying roles in the industry.




