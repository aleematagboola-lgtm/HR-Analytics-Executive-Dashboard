# HR-Analytics-Executive-Dashboard
An interactive HR Analytics Dashboard built in Excel, featuring data cleaning, transformation, and executive-level retention insights.

![HR Executive Dashboard](Executive_Dashboard.png)

# Data Cleaning & Transformation Documentation

**1. Initial Data Exploration & Observations**

After loading the HR dataset into Excel, I carried out an initial review to understand its structure and identify any data quality issues before beginning the analysis.

**Dataset Structure**

The dataset contains employee records with information on demographics, job details, performance, compensation, and employment status.

**Initial Observations**

a. Some text fields contained unnecessary trailing spaces.

b. Date values were not consistently formatted across the dataset.

c. A few important columns contained missing values that needed to be handled carefully to preserve the integrity of the data.

**2. Data Quality Issues Identified**

During the initial data audit, I identified the following issues:

a. Missing Employee First Names: Some records did not contain employee first names, making those records difficult to identify.

b. Incorrect Formula References: A few lookup and calculation formulas initially referenced the wrong cells, resulting in inaccurate outputs that needed to be corrected.

c. Chart Axis Formatting: The Years of Service field was stored as a number, causing Excel charts to display plain integers instead of more descriptive labels.

# Data Cleaning & Transformation Process

**Step 1: Removing Duplicate Records**

**Decision**

I checked the entire dataset for duplicate records and removed all identical rows before performing any calculations or analysis.

**Reason**

Removing duplicates ensures that employee counts, salary totals, averages, and other calculations are based only on unique employee records. This prevents duplicate entries from affecting the accuracy of the analysis.


**Step 2: Creating the Full Name Column**

**Decision**

I combined the First Name and Last Name columns into a single Full Name column using an IF-based formula with ISBLANK, PROPER, TRIM, and TEXTJOIN functions. The formula also accounted for records with missing first names by displaying a "-" in place of the missing value.

**Reason**

Creating a single Full Name column provides a consistent way to identify employees across the dataset. Using TRIM removed any unnecessary spaces, PROPER standardised the text formatting, and the conditional logic ensured that records with missing first names were still displayed clearly instead of producing blank or incorrectly formatted names.


**Step 3: Standardising Text Format**

**Decision**

I applied the PROPER function to text fields such as employee names, departments, and job roles.

**Reason**

The raw data contained inconsistent text formatting, including uppercase, lowercase, and mixed-case entries. Using the PROPER function standardised the text by capitalising the first letter of each word, making the dataset more consistent and easier to read.


**Step 4: Categorising Data and Mapping Information**

**Decision**

I used the SWITCH function to assign standardised category values based on specific conditions. I also used XLOOKUP throughout the project to retrieve and map related employee information across reference tables.

**Reason**

The SWITCH function simplified conditional logic and made formulas easier to maintain. XLOOKUP was chosen because it performs exact matches by default, supports lookups in any direction, and continues to work even if columns are added or removed from the dataset.



**Step 5: Handling Missing Numerical Values**

**Decision**

Missing values in the Performance Score and Salary columns were replaced using the median value for each column.

**Reason**

Replacing missing values allowed all employee records to be retained for analysis. The median was chosen instead of the average because salary and performance data can be affected by extreme values. Using the median provides a better representation of the typical employee.

**Step 6: Calculating Eligible Bonus Amount**

**Decision**

I created a calculated column to determine each employee's eligible bonus amount based on their salary and the bonus percentage assigned to their performance rating.

**Reason**

This calculation converted the raw salary and performance data into a meaningful financial metric, making it possible to analyse and visualise bonus payouts across different performance levels.

**Step 7: Handling Missing First Names**

**Decision**

Some employee records had missing first names. Instead of deleting these records or filling the missing values with random names, I replaced each missing first name with a "-".

**Reason**

Using "-" clearly indicates that the first name is missing while preserving the integrity of the dataset. This approach keeps all employee records intact and makes it easy for anyone reviewing the data to identify records with missing first-name information.



# Executive Insights & Key Findings

**Workforce Profile**

a. The organisation has a total workforce of 150 employees across six departments.

b. The Information Technology (IT) department has the largest number of employees, followed by Sales and Operations.

c. Finance has the smallest workforce.

**Compensation & Financial Analysis**

a. The organisation's average salary is $83,604.

b. IT has the highest salary expenditure at approximately $3.5 million, reflecting both its larger workforce and higher overall payroll.

c. Sales and Operations are the next largest salary cost centres.

d. Finance has the lowest salary expenditure at just over $1.5 million.

**Bonus Distribution**

The relationship between bonus allocation and employee performance shows a generally healthy pattern. Most bonuses are awarded to employees rated as Achieving and Exceeding expectations.

However, it may be worthwhile to review whether employees rated as Outstanding are receiving rewards that appropriately reflect their level of performance.

**Retention & Attrition Analysis**

One of the most important findings from the analysis is the organisation's 22.67% attrition rate.

In HR analytics, an attrition rate above 15% often indicates potential retention challenges that should be investigated.

**Departmental Attrition**

a. Finance and Human Resources have the highest attrition rates relative to their department sizes.

b. Although Operations has a slightly lower attrition rate, its larger workforce means the department contributes a significant number of employees leaving the organisation.

**Performance of Employees Who Left**

Using the Employment Status (Left) slicer together with the Performance by Status chart shows that many employees who left were performing at stable or high levels.
This suggests the organisation is losing valuable talent rather than only low-performing employees.

**Employee Tenure**

a. The average employee stays with the organisation for approximately 6 years.

b. The Employee by Service Year chart shows noticeable peaks around Year 4 and Year 9.

This suggests that employees who remain beyond their early years are likely to stay longer, but there are noticeable points where employees tend to leave. These patterns indicate opportunities to strengthen retention efforts around Years 3–4 and again around Year 8 before employees reach these transition points.

# Recommendations

Based on the findings from the analysis, the following actions are recommended:

**Target HR and Finance Retention**

a. Conduct stay interviews and employee engagement or culture assessments within the HR and Finance departments to better understand the reasons behind their higher attrition rates.

b. Review Operations Employee Experience.

c. Since Operations represents both a large workforce and a significant salary investment, review compensation, bonus structures, workload, and work-life balance to ensure they remain competitive.

**Strengthen Mid-Career Development**

a. Introduce clearer career progression opportunities, development programmes, and retention initiatives around Years 3–4 and Year 8 to reduce employee turnover during these critical periods.

## 📂 Project Files & Access

To interact with the live charts, dynamic slicers, and KPI cards shown above, you can download the working dataset directly:

**Excel Workbook:** [Download HR_Analytics_Executive_Dashboard.xlsx](HR_Analytics_Capstone_Completed_(Aleemat_Agboola).xlsx)
  


