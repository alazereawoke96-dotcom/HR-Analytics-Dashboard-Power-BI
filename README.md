
 HR-Analytics-Dashboard-Power-BI
This HR Analytics project uses Power BI to analyze employee attrition, workforce demographics, salary distribution, and performance. It includes data cleaning, data modeling, DAX measures, and interactive dashboards across three pages. The project delivers actionable insights to support data-driven HR decisions and improve employee retention.

## 📊 HR Analytics Dashboard

### 1. Attrition Dashboard
<img width="764" height="386" alt="attrition page" src="https://github.com/user-attachments/assets/63d3a782-70e0-480b-8cb0-1fddeea3db72" />

### 2. Workforce Dashboard
<img width="784" height="411" alt="workforce page" src="https://github.com/user-attachments/assets/5dd2df22-65b9-4428-8c1c-277ac81487d0" />

### 3. Salary and Performance Dashboard
<img width="767" height="412" alt="salary and performance" src="https://github.com/user-attachments/assets/f77734a9-ba05-4efb-b491-f5724afe28f2" />


# DAX Documentation — HR Analytics Project

## 1. Total Employees

**Business Purpose:** Measures the number of unique employees in the dataset.

```dax
**DAX Measure:**

Total Employees =
DISTINCTCOUNT(HR_Analytics[EmpID])
```
---

## 2. Employees Left

**Business Purpose:** Measures the number of unique employees whose attrition status is Yes.

**DAX Measure:**

Employees Left =
CALCULATE(
    DISTINCTCOUNT(HR_Analytics[EmpID]),
    HR_Analytics[Attrition] = "Yes"
)
```
## 3. Attrition Rate

**Business Purpose:** Measures the percentage of employees who left relative to the defined employee population.

**DAX Measure:**

```dax
Attrition Rate =
DIVIDE(
    [Employees Left],
    [Total Employees],
    0
)
```

---

## 4. Average Monthly Salary

**Business Purpose:** Calculates the average recorded monthly income of employees.

**DAX Measure:**
```dax
Average Monthly Salary =
AVERAGE(HR_Analytics[MonthlyIncome])
```

## 5. Total Monthly Payroll

**Business Purpose:** Calculates the sum of recorded monthly employee incomes.

**DAX Measure:**

Total Monthly Payroll =
SUM(HR_Analytics[MonthlyIncome])
```

## 6. Average Salary Hike

**Business Purpose:** Calculates the average recorded salary hike percentage.

**DAX Measure:**

```dax
Average Salary Hike =
AVERAGE(HR_Analytics[PercentSalaryHike])
```


## 7. Average Job Satisfaction

**Business Purpose:** Measures the average recorded job satisfaction rating.

**DAX Measure:**

```dax
Average Job Satisfaction =
AVERAGE(HR_Analytics[JobSatisfaction])
```

## 8. Average Work Experience

**Business Purpose:** Measures the average total work experience recorded for employees.

**DAX Measure:**

```dax
Average Work Experience =
AVERAGE(HR_Analytics[TotalWorkingYears])
```
