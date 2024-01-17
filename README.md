# 📊 Axis Hardware Sales Report

### Dashboard Link : https://app.powerbi.com/view?r=eyJrIjoiMWUyYzIyNzAtYjEyOS00MGM1LThmNDMtOTQ5OTI1YTJiZWMxIiwidCI6ImUxNGU3M2ViLTUyNTEtNDM4OC04ZDY3LThmOWYyZTJkNWE0NiIsImMiOjEwfQ%3D%3D

## 🚀 🚀 Problem Statement for Axis Hardware Sales Report

In contemporary business landscapes, understanding and optimizing sales performance is imperative for sustained growth. The Axis Hardware Sales Report aims to address the challenge of comprehending and enhancing sales metrics by scrutinizing various factors influencing revenue and sales quantity. The primary objective is to uncover insights into the dynamics of sales, taking into account diverse factors such as customer behavior, product preferences, and market trends.

In the context of Axis Hardware, where the Sales Report plays a pivotal role, the report provides a comprehensive overview of revenue, sales quantity, and profit-related metrics. The goal is to identify patterns and trends that can inform strategic decisions for improving business outcomes. With a critical focus on factors impacting sales, including market dynamics, customer preferences, and product performance, the Axis Hardware Sales Report aims to empower decision-makers to proactively implement targeted strategies for enhanced sales performance. 
## 📄 Usage
The report's multifaceted approach includes analyzing top customers, top-selling products, profit percentages, and contributions by market segment. Moreover, the report delves into revenue trends over time, facilitating a comparative analysis with the previous year's performance. This temporal perspective offers valuable insights into the trajectory of business growth and areas for improvement.

In essence, the Axis Hardware Sales Report serves as a vital tool for decision-makers, providing a holistic view of sales performance and equipping them with actionable insights to optimize revenue, improve sales efficiency, and drive business success.
### 🔍 Steps Followed

- Step 1 : Load data into Power BI Desktop, dataset is a SQL file.
- Step 2 : The data is load with the help of My SQL Server. And all the tables of sales database are then loaded, which are:- customers, market, date, product and transactions table.
- Step 3 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 4 : It was observed that no column had some empty data while woreking on the dataset. 
- Step 5 : In the sales database utilizing a star schema, the sales transaction table serves as the central fact table, capturing quantitative data. Surrounding it are dimension tables such as sales product, sales date, sales market, and sales customers, each containing descriptive attributes. This design simplifies querying and reporting, enhancing data analysis and providing a clear, efficient structure for understanding sales performance across various dimensions.

Snap of Star Schema Database ,

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/b85092bf-98e1-4c4e-9735-968897349e14)
- Step 6 : In the report view, under the view tab, theme was selected.
- Step 7 : Since the data is temporal, contains data of various years Visual filters (Slicers) were added for different years and months of that year.

Snap of Visual filters (Slicers),

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/be323eff-2689-4568-8bbe-e6771bf8af0b)
![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/f953791f-3e55-4834-93b9-ec2323e8d720)

- Step 8 : In the report view, under the insert tab, a text boxes was added to the canvas, where name of the Dashboard was mentioned.
- Step 9 : Six card visuals were added to the canvas, one representing Total no. of employees, No. of employees leaving, Employee leaving rate, Average age of employees, Average salary of employee and Average years served at company by the employees leaving it.
           Using visual level filter from the filters pane, basic filtering was used & null values were unselected for consideration into average calculation.
           
           Although, by default, while calculating average, blank values are ignored.

- Step 10 : A card visual was used to represent the Total no. of employees.

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/372ab522-9eba-4091-a4bf-e17c6bc4f966)

Following DAX expression was written for the same,
        
       Total no. of employees  = COUNT(HR_Analytics[EmpID])
- Step 11 : Second card visual was used to represents No. of employees leaving the company.

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/196cc87e-115d-4b5d-8589-8ded941f489e)

Following DAX expression was written for the same,
        
       No. of employees leaving  = SUM(HR_Analytics[AttritionCount])
       
- Step 12 : Third card visual was used to represents Employees leaving rate.

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/bc385c15-d7a1-4317-a779-c73b2d18addb)
 
Following DAX expression was written for the same,
               
      Employees leaving rate = DIVIDE(SUM(HR_Analytics[AttritionCount]), SUM(HR_Analytics[EmployeeCount]), 0)
      
- Step 13 : Fourth card visual was used to represents Average age of employees leaving the company.

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/e34da94d-9f9f-4ab6-984b-a8c441f9b2aa)

Following DAX expression was written for the same,
        
       Employees average age  = AVERAGE(HR_Analytics[AgeGroup])
- Step 14 : Fifth card visual was used to represents Average salary of employees leaving the company.

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/84ccb347-e00b-489c-bff8-ca5e6e160844)

Following DAX expression was written for the same,
        
       Employees average salary  = AVERAGE(HR_Analytics[MonthlyIncome])
- Step 15 : Sixth card visual was used to represents Average years served by the employees before leaving the company.

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/d5b8fff2-ebae-460c-81ef-2e7549032686)

Following DAX expression was written for the same,
        
       Average years served at company  = AVERAGE(HR_Analytics[YearsAtCompany])

- Step 16 : The rest of the report contains a donut chart, two bar charts, two stacked bar charts, one table and an area chart to clearify the problem statement using various visulazation as mentioned.
 - Step 17 : The report was then published to Power BI Service.
 
 
![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/c4fba114-fe06-47f4-b579-ededa2b23ddd)
