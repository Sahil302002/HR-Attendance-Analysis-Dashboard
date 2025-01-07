# HR-Attendance-Analysis-Dashboard
# **Project Overview:**

The project focuses on analyzing employee attendance data, with a key focus on work-from-home preferences, attendance patterns, and sick leave trends to provide actionable insights. The goal is to help the HR and management team better understand employee behavior, optimize workforce planning, and improve workplace policies. The analysis aims to deliver insights on the working preferences of employees (work-from-home vs. office), sick leave patterns, and how attendance patterns may align with specific events or external factors, like the flu season or company events (e.g., cricket matches).

### **Tasks to Done**

1. **Data Collection:**
    - Gather the employee attendance data for the current fiscal year (April to March).
    - Identify relevant data fields such as attendance (work-from-home, half-day work-from-home, sick leave, etc.).
2. **Data Cleaning:**
    - Clean the data to ensure that it’s structured properly for analysis (handling missing values, duplicate entries, or any data inconsistencies).
3. **Work-from-Home Analysis:**
    - Analyze work-from-home preferences (e.g., Monday or Friday) and any patterns associated with these choices.
    - Identify reasons behind frequent work-from-home patterns, such as illness or personal preference.
4. **Attendance Patterns:**
    - Calculate attendance percentages for employees on a weekly and monthly basis.
    - Identify any trends or anomalies in employee attendance, such as high absenteeism on certain days.
5. **Sick Leave Analysis:**
    - Analyze patterns of sick leave taken by employees.
    - Identify potential correlations between sick leave and external factors (e.g., flu season, COVID, or other seasonal illnesses).
6. **Data Integration for System Migration:**
    - Understand the requirements for the new system that will be implemented by HR.
    - Create a similar database structure to the upcoming system to ensure smooth migration and minimal changes.
7. **Visualization and Reporting:**
    - Use Power BI (or similar tools) to create dashboards and reports that highlight the key insights.
    - Create visuals that allow HR and management to easily interpret the data.
8. **Training and Documentation:**
    - Train the HR team (especially Pinali) on how to use Excel and the new system for self-service reporting and analysis.
    - Provide clear documentation to ensure that they can easily understand and navigate the reports and insights.
    
Dataset used in this project <a href = "Attendance Sheet 2022-2023_Masked.xlsx">Attendance Sheet Dataset</a>
    

# **Goals of the Project:**

1. **Provide Insights for Better Workforce Planning:**
    - Understand work-from-home preferences and attendance patterns to assist in capacity planning and optimize office space utilization.
2. **Improve Attendance and Sick Leave Monitoring:**
    - Identify sick leave trends and possible reasons (e.g., seasonal diseases, COVID, or other epidemics) to enable proactive measures such as sanitization and flu shots.
3. **Support Decision Making for Team Activities:**
    - Provide insights to help HR plan team-building activities, lunches, and other events on days with the highest attendance.
4. **Smooth System Transition:**
    - Align the data structure with the new system being implemented by HR, ensuring easy migration and minimal manual effort post-transition.
5. **Empower HR with Data Skills:**
    - Enable HR to independently analyze attendance data by training them in Excel and data analysis tools like Power BI, providing them with long-term self-sufficiency in handling similar tasks.
6. **Cost Optimization:**
    - Help the company optimize office space usage and infrastructure costs by analyzing employee presence and attendance patterns.

# Tasks done

### **Power Query and Data Transformation Tasks**:

1. **Understanding the Dataset**:
    - Imported multiple sheets with attendance data for different months.
    - Each sheet contained dates and attendance data for employees.
2. **Transforming the Data**:
    - Reformatted the data to have one column for dates and another for employee names and attendance.
    - Converted date columns into the correct `date` format.
    - Identified and handled non-date values like "holidays" and "off" as errors, and set up an error-handling mechanism.
3. **Creating Parameters for Dynamic Data Filtering**:
    - Created a dynamic parameter to filter data based on the specific month, allowing for flexible data analysis and reporting.
4. **Automation via Functions**:
    - Encapsulated transformation steps into a **custom function** to ensure reusability across all sheets.
    - Applied the custom function to multiple sheets (e.g., April, May, June) for consistency in the data format.
5. **Invoking the Custom Function**:
    - Applied the custom function to each sheet to transform the data consistently and automatically.
6. **Data Cleanup**:
    - Removed unnecessary columns (e.g., "attendance key") and renamed columns for clarity (e.g., `Employee Code`, `Name`, `Date`, `Value`).
    - Adjusted data types (e.g., setting date columns to the `date` format).
7. **Data Validation**:
    - Performed random checks to validate the transformation, including verifying employee attendance data for accuracy.
8. **Loading Data into Power BI**:
    - Prepared the cleaned and transformed dataset for loading into Power BI.
    - Ensured only the relevant data was loaded, excluding unnecessary sheets.
9. **Finalizing the Data for Visualization**:
    - Loaded the cleaned data into Power BI, ensuring proper naming and formatting for use in visualizations.

---

### **Metrics Creation in Power BI Tasks**:

1. **Introduction to Metrics**:
    - Defined metrics such as Work from Home percentage and Sick Leave.
2. **Setting Up a Measure Table**:
    - Created a dedicated measure table using Power BI’s "Enter Data" feature for better organization of metrics.
3. **Creating Measures**:
    - Developed the **Total Working Days** measure, excluding weekly offs and holidays.
    - Developed the **Present Days** measure, considering full and partial workdays (e.g., work from home and sick leave).
4. **Work from Home (WFH) Calculations**:
    - Created a new column to count work from home days using a `SWITCH` statement to assign values for full work from home, half work from home, and others.
    - Summed the work from home column to create the **Work from Home Measure**.
5. **Adjusting Present Days Calculation**:
    - Incorporated the work from home values into the Present Days calculation.
6. **Calculating the Presence Percentage**:
    - Defined the **Presence Percentage** formula and formatted it as a percentage for clarity.
7. **Visualization and Validation**:
    - Validated the calculations by checking intermediate outputs (e.g., Work from Home counts and Present Days).
    - Added a slicer for date-based filtering to enable dynamic insights and reporting.

---

### **Key Learnings**:

- Organization of measures in Power BI.
- Use of DAX functions like `CALCULATE`, `IF`, `SWITCH`, and `SUM` to manage real-world scenarios.
- Handling complex conditions (e.g., partial workdays).
- Visualization techniques for improved data interpretation.

HR Attendance Analysis Dashboard file <a href ="HR_Attendance_Analytics_Dashboard.pbix">HR Attendance Analysis Dashboard file</a>

![HR Attendance Analytic Dashboard](https://github.com/user-attachments/assets/e65bd983-622e-4fdb-b895-b47c44d07153)


## Explanation of the Dashboard

This is an **HR Attendance Analysis Dashboard** used to track and analyze employee attendance metrics over a specific period (April 2022 - June 2022). It provides insights into:

1. **Overall Metrics** (Top Left):
    - **Presence %**: The average percentage of days employees were present (91.8%).
    - **WFH %**: The percentage of Work-From-Home days (10.00%).
    - **SL %**: The percentage of Sick Leave days (1.10%).
2. **Employee-Specific Attendance Details** (Table):
    - Shows individual employees' Presence %, WFH %, and SL %.
3. **Attendance Trends** (Graphs):
    - **Presence % by Date**: Tracks daily trends in employee presence.
    - **WFH % by Date**: Tracks daily Work-From-Home trends.
    - **SL % by Date**: Tracks daily Sick Leave trends.
4. **Weekday Insights** (Right):
    - **Presence % by Weekday**: Shows attendance performance by day of the week.
    - **WFH % by Weekday**: Indicates which days employees worked from home the most.
    - **SL % by Weekday**: Highlights sick leave trends by weekday.
5. **Attendance by Date** (Bottom Table):
    - Provides a granular view of individual employees' attendance for specific dates (e.g., P = Present, WO = Work-From-Home).

---

### Key Insights

1. **Overall Attendance Performance**:
    - Employees were present for 91.8% of the recorded period.
    - Work-From-Home accounted for 10% of the attendance, suggesting flexibility in the workplace.
    - Sick Leave percentage is very low (1.1%), indicating a healthy workforce or underutilization of sick leaves.
2. **Employee Trends**:
    - Some employees, such as **Alexander Davenport** and **Alyson Huber**, maintained 100% presence.
    - **Ana Little** had a low Presence % (76.4%) compared to the team average.
    - **Ayanna Atkins** shows high sick leave utilization (10.71%).
3. **Weekly Trends**:
    - **Monday** and **Tuesday** have the highest presence percentages (93.2% and 93%, respectively).
    - **Friday** has the highest WFH percentage (13.01%), indicating employees prefer remote work at the end of the week.
    - **Monday** has the highest SL %, possibly reflecting illness trends after the weekend.
4. **Date-Specific Trends**:
    - Presence % shows minor dips but is generally consistent across the timeline.
    - WFH spikes are noticeable, particularly on certain Fridays and Thursdays.
    - SL % gradually increases toward the end of the period, possibly indicating seasonal patterns.

---

### Recommendations

1. **Optimize Work-From-Home Policies**:
    - The high WFH % on Fridays suggests employees might benefit from an official remote-work policy for Fridays. This could boost employee satisfaction and productivity.
2. **Investigate Attendance Patterns**:
    - Employees with consistently low attendance (e.g., Ana Little and Ayanna Atkins) should be engaged in one-on-one discussions to understand and address potential challenges.
3. **Address Sick Leave Trends**:
    - Since Monday has the highest SL %, consider implementing wellness initiatives, such as stress management programs or optional light-duty workdays, to reduce burnout from the weekend.
4. **Analyze WFH Trends**:
    - If WFH trends are seasonal or workload-dependent, review policies to ensure productivity is not compromised. Train managers to effectively monitor and support remote employees.
5. **Encourage Healthier Attendance**:
    - For employees like Ayanna Atkins, who use high SL %, consider promoting health programs, offering incentives for consistent attendance, or reviewing their workload for possible stress factors.
6. **Data Accuracy**:
    - Ensure all attendance tracking methods (in-office, WFH, and leave) are accurately recorded to avoid discrepancies that might skew data insights.
7. **Reward High Performers**:
    - Recognize and reward employees like Alexander Davenport and Alyson Huber for their exemplary attendance to encourage similar behavior among others.
8. **Enhance Weekend Productivity**:
    - Since Saturdays have 0% presence, explore the feasibility of optional or flexible work hours to balance workload while respecting work-life boundaries.

This dashboard provides an excellent starting point for attendance analysis, helping HR teams address trends and improve workforce management effectively.

