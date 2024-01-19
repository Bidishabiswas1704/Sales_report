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
- Step 9 : Three card visuals were added to the canvas, one representing Total Revenue of the company, other represnting Total sales quantity, and Total profit margin of the company.
           Using visual level filter from the filters pane, basic filtering was used & null values were unselected for consideration into average calculation.
           
           Although, by default, while calculating average, blank values are ignored.

- Step 10 : A card visual was used to represent the Total Revenue of the company.

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/8cb11554-9f34-441b-a2d0-58e595e74825)

Following DAX expression was written for the same,
        
       Revenue = SUM('sales transactions'[sales_amount])
- Step 11 : Second card visual was used to represents Total sales quantity of the company.

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/4a7a9bae-7e60-4fe9-b776-725f8c1aec1c)

Following DAX expression was written for the same,
        
       Sales Qty = SUM('sales transactions'[sales_qty])
       
- Step 12 : Third card visual was used to represents Total profit margin of the company.

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/ab6218fb-a52b-42ac-a943-0ad7ecc15c1a)
 
Following DAX expression was written for the same,
               
      Total Profit Margin = SUM('sales transactions'[profit_margin])
      
- Step 13 : Some other new measures are calculated for the better insights of the revenue and sales. For calculating Profit percentage.

Following DAX expression was written for the same,
        
       Profit Margin % = DIVIDE([Total Profit Margin],[Revenue],0)
- Step 14 : Next Profit Margin contribution percentage is also calculated.


Following DAX expression was written for the same,
        
      Profit Margin Contribution % = DIVIDE([Total Profit Margin],CALCULATE([Total Profit Margin],ALL('sales products'),All('sales customers'),ALL('sales markets')))
- Step 15 : On the similar basis Revenue Margin contribution percentage is calculated.

Following DAX expression was written for the same,
        
       Revenue Margin Contribution % = DIVIDE([Revenue],CALCULATE([Revenue],ALL('sales products'),All('sales customers'),ALL('sales markets')))
- Step 16 : At last, the revenue is comparied with the revenue of the last year.
Following DAX expression was written for the same,
        
       Revenue LY = CALCULATE([Revenue],SAMEPERIODLASTYEAR('sales date'[date]))

- Step 17 : The rest of the report is divided into two sheets, namely Performance analysis and profit analysis which contains six clustered bar charts, one line and column clustered bar  charts, one table and a line chart to clearify the problem statement using various visulazation as mentioned.
 - Step 18 : The report was then published to Power BI Service.
 
 ![Screenshot 2024-01-17 153607](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/09d63a73-6a97-408e-8170-04a9aeb5cf5f) 

# Report Snapshot (Power BI DESKTOP)
 
![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/71b0b1be-5bc3-49d9-8375-776a32d71217)

![image](https://github.com/Bidishabiswas1704/HR_Insights_Dashboard/assets/140384850/ea394b75-1a8c-4f23-a45b-330a2b10bbc6)

# 📈 Insights

A two pages report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;
## A) Performance Analysis:
### [1] Sales Quanity by Maeket
Analyzing sales quantity by market in the Axis Hardware Sales Report unveils geographic patterns, allowing for targeted strategies to meet regional demands. This insight enables the optimization of inventory, marketing efforts, and sales tactics tailored to specific market dynamics. If we check for year 2020,

1.1) Delhi NCR leads with the highest inventory count, reaching an impressive 143K goods.

1.2) Nagpur secures the second position, boasting a substantial inventory of 28K items.

1.3) Mumbai follows closely in the third spot, maintaining an inventory count of 23K goods.

thus, Delhi NCR holds the top position, while Nagpur and Mumbai stand as significant markets based on their respective inventory sizes.

### [2] Revenue by Market
Analyzing revenue by market in the sales report unveils revenue distribution patterns, enabling strategic focus on markets contributing most significantly to overall sales. This insight empowers businesses to allocate resources effectively, tailor marketing strategies, and prioritize efforts for optimal revenue growth. If we check for year 2020,

1.1) Delhi NCR leads with a remarkable revenue of 78 Million, establishing strong market dominance.

1.2) Ahmedabad and Mumbai secure the second position with revenue of 9 Million, presenting an opportunity for refining revenue strategies based on sales performance.

1.3) Nagpur, despite ranking third in revenue with 6 Million, exhibits efficient sales, indicating potential for increased profitability and further revenue growth.

thus, The correlation between sales and revenue emphasizes the need for a focused approach in Ahmedabad and Mumbai to align strategies for sustained growth. Nagpur, with efficient sales conversion despite lower revenue, suggests potential for increased profitability through targeted efforts.

### [3] Revenue Trend
Analyzing the revenue trend over time provides valuable insights into sales performance dynamics, allowing businesses to identify growth patterns, seasonal fluctuations, and areas for strategic improvement. This insight enables data-driven decision-making to optimize sales strategies and enhance overall revenue outcomes.

##### Year 2017:

a) January 2017: Initial baseline.

b) November 2017: Substantial increase.

c) December 2017: Decrease, marking the end of the year.

##### Year 2018:

a) January 2018: Revenue peaks at 25 million.

b) August 2018: Revenue reaches the highest point again at 25 million.

c) October 2018: A dip is observed, hitting the lowest point at 17 million.

##### Year 2019:

a) June 2019: Revenue hits a low point at 14.7 million.

b)July 2019: Steep increase in revenue, reaching 20.9 million.

Subsequent months in 2019: A decline is observed.

##### Year 2020:

a) January to March 2020: Revenue remains steady at 17 million.

b) June 2020: A significant decrease is noted, reaching 8 million.

### Insight:
The analysis reveals distinct patterns in revenue trends for each year, providing insights into peak months, low points, and overall trajectory, aiding strategic planning and decision-making.
### [4] Top Customer by Revenue
Analyzing the Top Customer by Revenue offers crucial insights into key accounts driving significant business income, helping identify customer segments with the highest contribution and enabling strategic efforts to nurture and expand these valuable relationships for sustained revenue growth. This insight guides businesses in tailoring sales and marketing strategies to optimize engagement with top-performing clients. If we check for year 2020,
