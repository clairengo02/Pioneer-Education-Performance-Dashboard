# Pioneer-Education-Performance-Dashboard
Power BI dashboard analysing student performance, attendance, enrolment trends and learning weaknesses using Power Query and DAX.

---

## Project Overview

This project was developed to analyse student enrolment and academic performance across different terms.

The dashboard helps users monitor:

- Student attendance
- Enrolment continuation
- Weekly and term performance
- Requirement status
- Score improvement
- Subject performance
- Student learning weaknesses
- Top-performing students

The report contains two interactive dashboard pages:

1. Education Performance Overview
2. Student Performance Overview

## Power BI Dashboard File

The complete interactive Power BI report is available below:

[Download the Power BI Dashboard](Pioneer%20edu%20dashboard.pbix)

> The `.pbix` file requires Microsoft Power BI Desktop to open.

---

## 1. Education Performance Overview

This page provides a high-level overview of student participation, enrolment, and academic performance.

### Key Metrics and Visuals

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

### Interactive Filters

Users can filter the dashboard by:

- Term
- Gender
- Student Group
- Week

![Education Performance Overview](Performance%20Overview%20dashboard.png)

---

## 2. Student Performance Overview

This page focuses on more detailed student-level academic performance and improvement.

### Key Metrics and Visuals

- Top 3 Performing Students
- Average Term Score
- Score Improvement vs Last Term
- Average Weekly Score
- Week 10 vs Week 1 Score Improvement
- Attendance vs Student Performance
- Percentage of Students Meeting Requirements
- Percentage of Students Not Meeting Requirements
- Top Student Weaknesses
- Average Term Score by Subject

### Interactive Filters

Users can analyse performance by:

- Term
- Gender
- Student Group
- Week

![Student Performance Overview](Student%20Performance%20dashboard.png)

---

## Key Features

- Interactive Power BI dashboard with two report pages
- Dynamic slicers for Term, Gender, Student Group, and Week
- DAX measures for student performance KPIs
- Term-over-term performance comparison
- Week 1 vs Week 10 score improvement analysis
- Requirement-status analysis
- Top-performing student analysis
- Attendance vs academic performance analysis
- Student weakness analysis
- Subject-level performance comparison
- Conditional formatting for positive and negative changes
- Cross-filtering between dashboard visuals

---

## Data Preparation

The original dataset was cleaned and transformed using Power Query.

The dataset was normalised into multiple related tables to improve data organisation and support accurate analysis.

### Main Tables

- **Student** – student-level information
- **Enrolment** – enrolment, attendance, subject, term, student group, and weakness information
- **Result** – weekly scores, total term scores, grades, and requirement status
- **Subject** – subject reference information

Relationships were established using student and enrolment identifiers.

---

## Data Model

The data model follows a relational structure:

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
