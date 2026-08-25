# Pioneer-Education-Performance-Dashboard
Power BI dashboard analysing student performance, attendance, enrolment trends and learning weaknesses using Power Query and DAX.

## Project Overview

This Power BI project analyses student enrolment, attendance, academic performance, continuation status, and learning weaknesses across different terms.

The dashboard was designed to help educators quickly identify overall performance trends, compare student groups, monitor score improvement, and recognise students who may require additional support.

---

## Dashboard Pages

### 1. Education Performance Overview

This page provides a high-level summary of student participation and overall academic performance.

Key insights include:

- Continuation Rate
- Average Attendance Rate
- Total Students
- Requirement Status
- Student Trend vs Last Term
- Requirement Trend vs Last Term
- Weekly Score by Enrolment Status
- Students by Subject
- Average Weekly Score by Gender
- Enrolments by Student Group

Users can filter the dashboard by:

- Term
- Gender
- Student Group
- Week

![Education Performance Overview](images/Performance%20Overview%20dashboard.png)

---

### 2. Student Performance Overview

This page provides a more detailed analysis of student academic performance.

Key insights include:

- Top Performing Students
- Average Term Score
- Score Improvement vs Last Term
- Average Weekly Score
- Week 10 vs Week 1 Score Improvement
- Attendance vs Student Performance
- Percentage of Students Meeting Requirements
- Percentage of Students Not Meeting Requirements
- Top Student Weaknesses
- Average Term Score by Subject

The dashboard also allows users to explore performance using Term, Gender, Student Group, and Week filters.

![Student Performance Overview](images/Student%20Performance%20dashboard.png)

---

## Key Features

- Interactive Power BI dashboard with multiple report pages
- Dynamic slicers for Term, Gender, Student Group, and Week
- DAX measures for academic performance KPIs
- Term-over-term score comparison
- Week 1 vs Week 10 performance improvement
- Student requirement-status analysis
- Top-performing student analysis
- Attendance and academic performance comparison
- Student weakness analysis
- Conditional formatting for positive and negative performance changes
- Interactive filtering and cross-visual analysis

---

## Data Preparation

The original dataset was cleaned and transformed using Power Query.

The data was normalised into multiple related tables to improve data structure and support accurate analysis.

The main tables include:

- **Student** – student-level information
- **Enrolment** – enrolment, attendance, subject, term, and weakness information
- **Result** – weekly scores, total term scores, grades, and requirement status
- **Subject** – subject reference information

Relationships between the tables were created using student and enrolment identifiers.

---

## Data Model

The Power BI data model follows a relational structure:

```text
Student
   |
   | student_id
   v
Enrolment
   |
   | enrolment_id
   v
Result

Subject
   |
   v
Enrolment
