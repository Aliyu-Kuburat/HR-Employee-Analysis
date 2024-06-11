# HR Employee Analysis

## Data Exploration

### EmployeeID Analysis:

1)	How many employees do we currently have in our database?
2)	Can we identify any patterns or trends in employee IDs?
3)	Are there any duplicate or missing IDs that need to be addressed?
4)	How many employees have the same name?
5)	Can we identify any naming conventions or patterns?

### Job Title, Department and Business Analysis:

6)	What is the distribution of job titles across departments and business units?
7)	Are there any discrepancies between job titles and assigned departments?
8)	Which job titles have the highest turnover rates?
9)	How many departments do we have, and what are they?
10)	Can we identify any departments with particularly high or low employee retention rates?
11)	Are there any departments with a higher frequency of promotions or demotions?
12)	How many business units are there, and what are they?
13)	Are there any business units that consistently outperform or underperform compared to others?

### Gender and Ethnicity Analysis:

14)	What is the gender distribution across the organization?
15)	Are there any gender disparities in terms of salary, bonuses, or promotions?
16)	What is the ethnic diversity within the organization?
17)	Are there any disparities in hiring, retention, or promotion based on ethnicity?

### Age distribution Analysis:

18)	What is the age distribution of employees?
19)	Are there any trends in the age of employees based on job title or department?

### Annual Salary and Bonus Analysis:

20)	What is the average salary across different job titles and departments?
21)	Are there any significant differences in salary based on gender or ethnicity?
22)	What is the average bonus percentage given to employees?
23)	Are there any trends in bonus percentages over time or based on job performance?

### Country and City Analysis:

24) In which countries does the company operate?
25) Are there any differences in employee demographics or turnover rates between countries?
26) What are the primary locations of our employees?
27) Are there any correlations between city location and job satisfaction or performance?

### Hire and Exit Date Analysis:

28) How long, on average, do employees stay with the company?
29) Can we identify any patterns in hiring trends over time?
30) What is the turnover rate within the organization?
31) Can we identify any patterns or trends in employee exits, such as seasonal variations or departmental trends?

## Data Cleaning:

-	I imported the data into Excel to get more information about the data
  
-	I sorted the data set by Employee ID and discovered 172 duplicate Employee IDs with different other column information.
  
-	I changed the last digit of the employee ID ensuring there were no more duplicates.
  
-	While cleaning, I noticed a discrepancy in the job title. I had 110 records of Sr. Manger in place of Sr. Manager so I used the Find and Replace function to replace 
        Sr. Manger with Sr. Manager.
 	
-	I created a new column named ‘Hire Month’ which was extracted from the hire date
  
-	I created another column and named it ‘Age Group’ and this segregates the employees into age groups of Young adults, Adults, Middle-Aged Adults and Elderly. I used 
        this formula: =IF(AND(Age>=20, Age<=30), "Young Adult", IF(AND(Age>=31, Age<=40), "Adult", IF(AND(Age>=41, Age<=50), "Middle Aged Adult", "Elderly"))).
 	
-	Excel using this formula =INDEX(C2:C1001, MODE(MATCH(C2:C1001,C2:C1001,0))) to create the most frequent job title.
  
-	I added another column called ‘Duration of Employment’ which I calculated using this formula =IF(AND(Hire Date<>"", Exit Date<>""), Exit Date - Hire Date, IF(Hire 
        Date  <>"", DATE(2024,4,16)- Hire Date, ""))
	
### Data Transformation and Visualization in Power BI:

**1.	Data Preparation and Verification:**
   
    a.	Imported and meticulously reviewed the cleaned Excel dataset in Tableau.
  	
    b.	Ensured the accuracy of data types for each column, making necessary adjustments where required.

**2.	Exploratory Data Analysis (EDA):**

    a. Visualized key exploratory questions identified beforehand, ensuring a comprehensive understanding of the dataset.

**3.	Employee Distribution Analysis:**

    a.	Utilized a Clustered Bar Chart to illustrate the distribution of employees across various departments.

    b.	Highlighted the most frequent job title using a Card visual, leveraging the Top N filter functionality.

**5.	Key Insights Visualization:**
   
    a.	Presented the department with the highest number of employees and the average annual salary using Card visuals for clear and concise representation.
    
    b.	Employed a Pie Chart to showcase gender distribution among employees.

**6.	Trend Analysis:**

    a.	Utilized a Line Chart to depict hiring trends over the years, providing insights into recruitment patterns.

**7.	Demographic Analysis:**

    a.	Visualized age groups across different genders using a Stacked Column Chart, facilitating a deeper understanding of demographic distributions.

    b.	Calculated and displayed the average highest bonus percentage for each department using a Stacked Bar Chart.

**8.	Longest-serving Employees Analysis:**

    a.	Employed a Clustered Column Chart to identify the top 5 employees with the longest tenure in the organization, with varying shades of color for distinction.

**9.	Employee Demographics Page:**
   
    a.	On a separate page titled "Employee Demographics," presented various metrics such as total exited and active employees, months of hiring, and resignation trends.

    b.	Implemented slicer functionality for efficient filtering of records by age group.

## Employee Overview Analysis

**Job Title, Department, and Business Analysis:**

![Screenshot 2024-06-10 115553](https://github.com/Aliyu-Kuburat/HR-Employee-Analysis/assets/156312358/686e06cd-b7b2-4b4a-ad3f-cf3e65e76783)


•	Total employees over time: 1,000 (915 current, 85 exited)

•	33 job titles across 7 departments and 4 business units

•	Average department size: 44 employees

•	Highest number of employees in IT (241) followed by Engineering (158), both above the department average of 142

•	Four departments with bonuses above average of 12: Marketing, Human Resources, Finance, and IT

•	Human Resources and Finance have the highest exit rates, while Accounting has the least exits

•	Specialty Products and Corporate have the highest number of employees, surpassing the average compared to Research & Development 
	and Manufacturing

•	More exits in Specialty Products and Research & Development compared to Corporate and Manufacturing

**Gender and Ethnicity Analysis:**

![Screenshot 2024-06-10 121205](https://github.com/Aliyu-Kuburat/HR-Employee-Analysis/assets/156312358/cd6fc10d-c0cc-4ea9-baa0-6ce38081c290)


•	Gender distribution: 52% female, 48% male

•	Ethnicity breakdown: 25% Latino, 40% Asian, 27% Caucasian, 7% Black

•	Gender distribution by department: More females in Manufacturing, Specialty Products, and Research & Development; 
	more males in Corporate

•	Bonus distribution: Females received more bonuses than males, with both genders above average

•	Ethnicity and bonus: Asians have above-average bonuses, Blacks have the least bonuses, some Latinos and Caucasians have above-average bonuses in IT and Engineering 
        but below average in other departments

•	Ethnic representation: 404 Asians, 271 Caucasians, 251 Latinos, 74 Blacks

•	Exits by ethnicity: More Asians, Caucasians, and Latinos left the company compared to Blacks

•	Country and ethnicity: Employees from Brazil, China, and the United States. United States employees are Asian, Black, Caucasian, and Latino. Latinos are from 
        Brazil, Asians are from China.

**Age Distribution Analysis:**

•	Age groups: 150 Young Adults, 234 Adults, 283 Middle-aged Adults, 333 Elderly

•	Elderly employees constitute the largest age group in the company

•	Average age group across all departments: 44-46 years

**Annual Salary and Bonus Analysis:**

![Screenshot 2024-06-10 121205](https://github.com/Aliyu-Kuburat/HR-Employee-Analysis/assets/156312358/19fb1168-a6aa-4230-be49-1436b4b10303)


![Screenshot 2024-06-10 121111](https://github.com/Aliyu-Kuburat/HR-Employee-Analysis/assets/156312358/160cd74f-a5e1-4926-9484-a8948725b704)



•	Salary distribution: Latinos and Blacks are paid below average compared to other ethnicities

•	Bonus eligibility: Only Vice Presidents, Managers, Senior Managers, Directors, and Engineering Managers are entitled to bonuses

•	Gender and ethnicity distribution: More male and female Asians in the company, with Blacks being the least represented

**Country and City Analysis:**

•	Employees predominantly located in the United States, followed by Brazil and China

•	Country distribution by ethnicity: United States has Asian, Black, Caucasian, and Latino employees; Brazil has Latino employees; China has Asian employees

**Hire and Exit Date Analysis:**

![Screenshot 2024-06-10 121357](https://github.com/Aliyu-Kuburat/HR-Employee-Analysis/assets/156312358/54815278-93fb-45b7-a35f-a13c2b33e2a7)


•	Continuous upward trend in hiring, with the highest count in 2021 indicating company expansion

•	Yearly exits: At least one exit per year except from 2000-2002, with the highest exits in 2021 (20) and a decrease in 2022 (7)

## Analysis Summary:

•	The company has a robust and expanding workforce with significant hiring in recent years, especially in 2021.

•	IT and Engineering departments have the highest number of employees, with Human Resources and Finance seeing the highest exit rates.

•	Gender distribution is relatively balanced, with a slight female majority, while ethnicity distribution shows a higher representation of Asians and a lower 
        representation of Blacks.

•	Age distribution reveals a higher number of Elderly employees, with the average age group between 44-46 years.

•	Salary and bonus analyses indicate disparities, with Latinos and Blacks receiving lower average salaries and bonuses.

•	Geographic distribution shows a concentration of employees in the United States, followed by Brazil and China.

**Recommendations:**

•	Investigate factors contributing to high exits in specific departments and develop retention strategies.

•	Address salary and bonus disparities to ensure equitable compensation across all ethnic groups.

•	Continue expanding hiring efforts while monitoring and supporting employee demographics to maintain diversity and inclusion.

•	Focus on understanding the high turnover in 2021 to mitigate future exit spikes and sustain company growth.


**Limitation**

While the analysis provides valuable insights into the company's workforce demographics, hiring, exits, and compensation trends, it is limited by data completeness, lack of contextual information, and a narrow scope of demographic and geographic analysis. Addressing these limitations would require more detailed and comprehensive data, including qualitative insights, to develop a fuller understanding of the factors influencing employee retention, satisfaction, and overall workforce dynamics.

•	There is no information on the reasons behind employee exits, which limits understanding of turnover causes.

•	While the analysis identifies countries where employees are located, it lacks detailed insights into city-level distributions or regional trends within those 
        countries.

•	There is no examination of how geographic location might impact salary, bonus distribution, or employee satisfaction and retention.

•	The salary and bonus analysis highlights disparities but does not explore potential reasons or provide recommendations for addressing these issues.

•	The analysis lists job titles and departments but does not provide detailed insights into the specific roles and responsibilities or how they might affect turnover 
        rates, salary, and bonuses.
  
•	There is no mention of employee feedback or surveys that could provide deeper insights into the workforce's perspectives.

•	The reasons behind employee exits are not explored, which limits the ability to develop targeted retention strategies.

•	There is no distinction between voluntary and involuntary exits, which could provide more nuanced insights into turnover trends.

**NEXT STEP**

**1. Investigate High Exits in Specific Departments:**

 - **Conduct Exit Interviews:** Talk directly to employees who are leaving to understand their reasons for departure. This can be done through surveys or one-on-one 
   interviews.

 - **Analyze Exit Data:** Look for patterns in the data related to exits, such as department, tenure, age group, or job title.

 - **Focus Group Discussions:** Facilitate discussions with current employees in high-exit departments to understand their concerns and perspectives.
   
 - **Review Management Practices:** Evaluate management styles and leadership practices in departments with high turnover. Are there opportunities for improvement?

**2. Address Salary and Bonus Disparities:**

 - **Compensation Review:** Conduct a comprehensive review of salaries and bonuses across departments and ethnicities. Identify any statistically significant disparities.

 - **Pay Equity Analysis:** Use statistical tools to assess whether differences in pay can be justified by factors like experience, performance, or job requirements.

 - **Adjust Compensation:** If disparities are found to be unfair, develop a plan to adjust salaries and bonuses to ensure equal pay for equal work across all ethnicities.

**3. Continue Expanding Hiring with Diverse Demographics:**

 - **Diversity and Inclusion Initiatives:** Implement programs to attract and retain talent from diverse backgrounds. This could involve partnering with diverse 
     professional organizations or revamping job descriptions to be more inclusive.
   
 - **Diversity Recruiting Strategies:** Target colleges and universities with diverse student populations for recruitment efforts. Partner with organizations focused on 
     underrepresented groups in your industry.
   
 - **Track Hiring Demographics:** Monitor the demographics of new hires to ensure progress towards diversity and inclusion goals.

**4. Understand High Turnover in 2021:**
   
 - **Identify Specific Triggers:** If possible, pinpoint major events or changes in the company that might have contributed to the high turnover in 2021.
 
 - **Compare to Industry Standards:** Benchmark your company's turnover rate against industry averages to see if it's a broader issue or company-specific.

 - **Review Company Culture:** Evaluate the overall company culture and employee engagement. Are employees feeling valued and supported?

