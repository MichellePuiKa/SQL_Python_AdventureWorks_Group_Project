# 📊 AdventureWorks Cycles Data Analysis 

## **1. Project Overview**
This project was contributed by our six project members that focus on analysing the AdventureWorks database, a simulated business operations dataset for a global bicycle retailer. Using SQL and Python, we explored key revenue drivers, including regional sales performance, employee behavior, store characteristics, and sales trends. Additionally, external data sources such as WorldBank.org were integrated to provide a broader economic context for the analysis.


## **2. Data Source, Data Preparation & Cleaning**
### **Data Sources**
AdventureWorks2022 dataset was obtained from **[Microsoft Learn](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver15&tabs=ssms)**
    
### **Data Preparation**
To understand the data structure and identify the relevant tables, relationships, and necessary joins between tables, we created a database diagram for the AdventureWorks2022 in SQL Server Management Studio (SSMS) before planning the data extraction process.  The data for store sizes, annual revenue, and the number of employees is stored in XML data structures in Table Sales.Store. We need to extract the data from the XML using the CAST() function in SQL before proceeding with any further steps

### **Data Cleaning**
Data cleaning involved handling missing values in the 'TotalDue' column and removing duplicate records from the sales transactions. Outliers in store revenue were also identified and addressed. To analyse store performance over time, we created a new variable, 'StoreDuration', by calculating the difference between the current year and the year the store was opened.  The data was cleaned by removing unnecessary information, and the required data was processed by joining relevant tables to facilitate the analysis.


## **3. Executive Summary**
### 📌 **Key Findings**
- The southwest region of the US has the most sales
- A correlation was found between annual leave and bonus, this could offer insights for employee benefit decisions
- The US is the strongest performing market, but sales are being bottlenecked by overseas tariffs, especially in Europe.
- The analysis found no conclusive evidence of a significant relationship between job title and sick leave hours.
- No relation between sales revenue and store duration Larger stores typically require a bigger workforce and generate higher revenue.
- Sales trend of bikes is strongly influence by the external factors (Olympic events)


## **4. Insights Deep Dive**
### **4.1 Which Country Performing the Best Sales?**
![Sales Performance Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Top%20Sales%20by%20Country.PNG)

**US** leading at **$26,411,060** followed by Canada, Australia and UK


![USA Regional Sales Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/US%20Best%20Performing%20Regional%20Sales.PNG)

The Best Performing Region in US is **Southwest with Sales of $10,510,853.87**


### **4.2 What is the Relationship Between Annual Leave Taken and Bonus?**
![Scatter Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Annual%20Leave%20and%20Commission%20Relationship.PNG)

- Examines the relationship between **vaction hours** and **commission percentage**
- **Commission percentage**: Earnings based on Sales
- **Vacation hours**: Time off taken by Employees


![Correlation Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Vacation%20Hours%20and%20Bonus%20Percentage%20Relationship.PNG)

- There is a **moderate positive correlation (0.82)** between vacation hours and bonus percentages.  This suggests that employees with more vacation hours tends to receive higher bonuses.
- **Relationship is not statistically significant**
- **Slight positivie effect**: Each additional vacation hour may slightly increase commission, but the effect is minimal

  
![Line Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Annual%20Leave%20and%20Bonus%20Relationship.PNG)

- The company's leave and bonus policies show a relationship between higher vacation leave and increased bonuses
- Further analysis on organisational levels and employee tenure could provide more specific insights


### **4.3 What is the Relationship Between Country and Reveune?**
![Bar Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Sales%20YTD%20by%20Territory.PNG)

- **US has the highest number of sales**, with the Southwest region alone accounting for more sales than the other countries
- **European sales are the weakest**


![Line Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/GDP%20Figures.PNG)

- **US** had the highest GDP of all countries in the database which matches their sales performance relative to the other nations
- Despite **Canada** had the second lowest GDP of the group in 2014 (1.81 trillion) they still accounted for the second highest sales
- This points further to issues with overseas sales performances (a strong GDP should imply more readiness to purchase the product)

  
![Tariff & Agreement Table](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Tariff%20%26%20Agreement.PNG)

- **Europe had the highest tariffs** as they did not have a special trade agreement with the US in 2014
- **Canada** has a special trade agreement with US that allows AdventureWorks to export their goods **tariff free**
- **Australia** had a trade agreement with US in this period, but it would not have covered this industry, so **standard tariffs were applied**


### **4.4 What is the Relationship Between Sick Leave and Job Title?**
![Bar Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Average%20Sick%20Leave%20by%20Job%20Titles.PNG)

![Top10 Bar Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Top%2010%20Most%20Job%20Titles%20with%20Most%20Sick%20Leave%20Hours.PNG)

- The Organisation Level with the Highest Number of Sick Leave Hours is Level 4 (the lowest level)
- The second level with the Greatest Number of Sick Leave Hours is Level 3 then Level 2


![Scatter Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Average%20Sick%20Leave%20Hours%20by%20Rates%20of%20Pay.PNG)

- **Slight negative correlation**, but it is not significant enough to draw conclusions
- The correlation coefficient between the two values is -0.00341312
- Does not correspond with what we saw about the Organisation Level, as we saw that those who are on a lower level tend to take more sick leave


### **4.5 What is the Relationship between Store Trading Duration and Revenue?**

![Scatter & Bar Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Store%20Revenue%20by%20Trading%20Duration.PNG)

![Bubble Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Link%20Between%20Store%20Duration%2C%20Size%20%26%20Revenue.PNG)

- Weak/Inconsistent Correlation: no trend or clear pattern
- Possible Reasons for this weak or fluctuating relationship: Location, seasonality, marketing efforts and product offerings


### **4.6 What is the Relationship between The Size of The Stores, Number of Employees and Revenue?**
![Pairplot](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Pairplot%20of%20Store%20Attributes.PNG)

![Matrix](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Correlation%20Matrix.PNG)

![Scatter Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Relationship%20between%20Store%20Size%2C%20Employees%20%26%20Revenue.PNG)

- **Number of Employees vs Store Size:** Larger Stores generally require more employees
- **Number of Employees vs Revenue:**
   1. Comparision Between Clusters: Larger Stores with more employees tend to generate higher revenue
   2. Comparision Within Each Cluster: The number of employees will NOT affect revenue
- **Number of Employees vs Store Size vs Revenue:** Larger Stores with more employees will generate more revenue


### **4.7 The Sales Trends of Bikes (Jan 2011 - Jun 2014)**
![Line Chart](https://github.com/MichellePuiKa/SQL_Python_AdventureWorks_Group_Project/blob/main/Bikes%20Sales%20Reveune%20Trend.PNG)

- **January 2011 - January 2013**
  - **Significant Sales Reveune Increase for both Road Bikes and Mountain Bikes**
  - **External Factor :** The influence of Cycling at the **2012 Summer Olympics**

- **January 2013 - January 2014**
  - **Sharp Decline of Sales for all three types of Bikes**
  - **External Factor:** The growth of **Bikes Share Programme** and the emergence of alternative transport options


## **5. Recommendations**
🚀 **Updated Data**: The data used in this analysis is last updated to year 2014, which is over 10 years old and does not account for significant events like the COVID-19 pandemic. To gain more accurate 
insights into current performance trends, it is recommended to update the analysis with more recent data, ideally from 2019 to 2023. This would reflect changes in consumer behaviour, business operations, and other post-pandemic factors that could impact store performance.
 
📢 **Inclusion of Variable Factors**: it would be beneficial to include variables that reflect more recent economic and social factors. For instance, incorporating data on online sales, changes in 
customer demographics, or the impact of marketing campaigns could provide a more comprehensive view of the factors influencing store performance. 
   
📊 **Provision of Store Rental Costs**: One potential area for further analysis is to gather information on rental costs for various store sizes and employee salaries. This would allow us to calculate the total cost for each store and help determine the optimal store size and number of employees needed to maximize revenue while minimizing costs.



## **External References**
- WorldBank.org: Used to analyze GDP performance in relevant countries and its correlation with sales
- “Bicycle-sharing system” - Wikipedia Bicycle-sharing system - **[Wikipedia](https://en.wikipedia.org/wiki/Bicycle-sharing_system)**
- “Bike-Sharing Clicks Into Higher Gear” - by Felix Richter, Jul 3 2018, **[Statista](https://www.statista.com/chart/14542/bike-sharing-programs-worldwide/)**
- “Cycling at the 2012 Summer Olympics” - **[Wikipedia](https://en.wikipedia.org/wiki/Cycling_at_the_2012_Summer_Olympics)**
- “Demand for Bikes Soars Following Olympic Cycling Events, New Research Suggests” posted on 9 Sep 2024 in **[Association of Cycle Trader](https://www.cycleassociation.uk/news/?id=4046&name=Demand+for+bikes+soars+following+Olympic+cycling+events%2C+new+research+suggests.)**



## **💡 Connect & Feedback**
🔗 Have suggestions or feedback? Feel free to **open an issue**!  


