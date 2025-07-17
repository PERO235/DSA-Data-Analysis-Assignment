# Project Overview
This is my first project as astudent of DSA incubator hub,it is a  Gender Equality Audit for Palmoria Group
Client: Palmoria Group
Location: Nigeria (Operations across 3 regions)
Project Lead: Mr. Yunus Shofoluwe (CHRO)
HR Analytics Consultant: [P.A (myself)]
Based on the data anlysed ,key findings were made and recommendations were given.


# Steps :
Various steps were taken  to analyse this data and include the following
Import the employee data into Power BI.
Do a proper cleaning E.g
1. Remove employees without salaries and departments indicated as "NULL".
2. Assign a generic gender status to employees who refused to disclose their gender.
   
https://github.com/PERO235/DSA-Data-Analysis-Assignment/blob/main/CLEAN%20FILE%20NOW.pbix

#1: Gender Distribution Analysis
1. Create a bar chart:
    - Axis: Region/Department
      
    - Value: Count of Employees by Gender
  
      
2. Use a slicer to filter by region/department.
3. Visualize the overall gender distribution using a pie chart.

Visualization: 
- Bar chart: "Gender Distribution by Region"
- Pie chart: "Overall Gender Distribution"

Measures
- `Gender Count = COUNT('Employee'[Gender])`
- `Gender Percentage = DIVIDE(CALCULATE(COUNT('Employee'[Gender])), CALCULATE(COUNT('Employee'[Gender]), ALL('Employee'[Gender])))`
  # 2: Ratings Insights Based on Gender
1. Create a histogram/box plot:
    - Axis: Rating
    - Value: Count of Employees by Gender
2. Use a slicer to filter by gender.
3. Calculate the average rating by gender using a measure.

Visualization:
- Histogram: "Ratings Distribution by Gender"
- Box plot: "Ratings Comparison by Gender"

Measures
- `Average Rating by Gender = AVERAGE('Employee'[Rating])`
- `Rating Count by Gender = COUNT('Employee'[Rating])`
  #3: Salary Structure and Gender Pay Gap Analysis
1. Create a scatter plot:
    - X-axis: Salary
    - Y-axis: Gender
2. Calculate the average salary by gender using a measure.
3. Identify departments and regions with significant pay gaps.

Visualization:
- Scatter plot: "Salary vs. Gender"
- Bar chart: "Average Salary by Department and Region"

Measures 
- `Average Salary by Gender = AVERAGE('Employee'[Salary])`
- `Salary Count by Department and Region = COUNT('Employee'[Salary])`
  # 4: Minimum Salary Requirement Analysis
1. Create a histogram:
    - Axis: Salary Band ($10,000 increments)
    - Value: Count of Employees
2. Use a slicer to filter by region.
3. Calculate the number of employees below the minimum salary threshold.

Visualization:
- Histogram: "Salary Distribution by $10,000 Band"
- Bar chart: "Employees Below Minimum Salary Threshold by Region"

Measures
- `Employees Below Minimum Salary = COUNTX(FILTER('Employee', 'Employee'[Salary] < 90000), 'Employee'[Salary])`
# 5: Bonus Payment Calculation
1. Create a measure to calculate the bonus amount based on performance ratings.
2. Calculate the total amount to be paid to individual employees (salary + bonus).
3. Create a bar chart to visualize the total amount to be paid out per region.

Visualization:
Bonus Payments
- Bar chart: "Total Bonus Payout by Region"
- Table: "Individual Employee Bonus Payments"

Measures
- `Bonus Amount = IF('Employee'[Rating] > 3, 'Employee'[Salary] * 0.1, 0)`
- `Total Amount to be Paid = 'Employee'[Salary] + 'Bonus Amount'`

# Data Sources
The primary source of data is  an open-source file that can be easily downloaded from an open-source online platform.

