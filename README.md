# Pioneer Education Performance Dashboard

A two-page Power BI dashboard analysing student attendance, enrolment continuation, weekly achievement, academic requirements, and learning-support needs. The project demonstrates an end-to-end analytics workflow using Power Query, relational data modelling, DAX, interactive visualisation, and evidence-based recommendations.

---

## Project Overview

Pioneer Education needed a clearer way to monitor student participation and academic performance across the available school terms. The dashboard transforms student, enrolment, and assessment data into an interactive report that helps educators:

- Monitor attendance and enrolment continuation
- Compare weekly and term performance
- Identify students meeting or not meeting academic requirements
- Examine the relationship between attendance and achievement
- Compare outcomes across student groups and demographic filters
- Recognise students who may require early support
- Translate learning patterns into practical teaching strategies

The main findings in this README combine all available terms. Users can use the Term slicer to explore a particular term; however, term-level results should be interpreted cautiously because the terms contain different numbers and groups of students.

## Power BI Dashboard

[Download the Power BI dashboard (.pbix)](https://raw.githubusercontent.com/clairengo02/Pioneer-Education-Performance-Dashboard/main/Pioneer%20edu%20dashboard.pbix)

> Microsoft Power BI Desktop is required to open the PBIX file.

---

## Dashboard Pages

### 1. Education Performance Overview

This page provides a high-level view of participation, enrolment, and academic outcomes.

#### Key metrics

- Continuation rate
- Average attendance rate
- Total students
- Overall requirement status
- Student trend compared with the previous available term
- Requirement trend compared with the previous available term

#### Visuals

- Weekly Score by Enrolment Status
- Average Weekly Score by Gender
- Requirement Achievement by Student Group
- Enrolments by Student Group
- Minimum expected weekly-score reference line

![Education Performance Overview](Performance%20Overview%20dashboard.png)
### 2. Student Performance Overview

This page provides a more detailed view of student achievement and potential support needs.

#### Key metrics and visuals

- Top-performing students
- Average term score
- Term score comparison with the previous available term
- Average weekly score
- Week 10 versus Week 1 score improvement
- Attendance versus Student Performance scatter chart
- Regression trend line showing the association between attendance and performance
- Percentage of students meeting and not meeting requirements
- Average Attendance Rate by Gender
- Average Term Score by Subject

![Student Performance Overview](Student%20Performance%20dashboard.png)

### Interactive filters

Both pages can be explored using:

- Term
- Gender
- Student Group
- Week

The visuals cross-filter one another, allowing users to investigate specific student segments and periods.

---

## Key Features

- Two interactive Power BI report pages
- Data cleaning and transformation in Power Query
- Normalised relational data model
- DAX measures for attendance, continuation, requirement achievement, weekly performance, and score comparisons
- Term-over-term and Week 1-to-Week 10 comparisons
- Regression analysis of attendance and academic performance
- Reference line for the minimum expected weekly mark
- Conditional formatting for positive and negative changes
- Page navigation and consistent dashboard styling
- Dynamic slicers and cross-filtering
- Written learning-needs analysis instead of a standalone weakness chart

---

## Data Preparation

The original Excel dataset contained 25 student records and weekly scores from Week 1 to Week 10. Power Query was used to clean and restructure the data before analysis.

Key preparation activities included:

- Correcting column names and removing unnecessary spaces
- Trimming text values to prevent duplicate categories
- Checking blank values and duplicate records
- Assigning appropriate text, whole-number, decimal, and percentage data types
- Separating student, enrolment, result, and subject information
- Unpivoting weekly score columns where required for week-based analysis
- Creating identifiers and relationships to support filtering between tables

## Data Model

The model uses four main tables:

- **Student** – student identifier, name, and gender
- **Enrolment** – enrolment identifier, student, subject, term, attendance, student group, weakness, and enrolment status
- **Result** – enrolment-level weekly scores, term score, grade, and requirement status
- **Subject** – subject identifier and subject name

```text
Student (1)
    |
    | student_id
    v
Enrolment (*)
    |
    | enrolment_id / education_id
    v
Result (*)

Subject (1)
    |
    | subject_id
    v
Enrolment (*)
```

The model is designed so that student and subject dimensions filter the related enrolment and result records.

---

## Key Data Insights

### Overall participation and performance

- The dataset contains **25 students**.
- The overall average attendance rate is approximately **94%**.
- **13 of 25 students (52%)** met the academic requirements, while **12 students (48%)** did not.
- **16 of 25 students (64%)** continued their enrolment, while **9 students (36%)** discontinued.
- The average weekly score is approximately **7.24 out of 10**.
- Four students were tied for the highest recorded term score of **86**: Damon Dang, Justin Duong, Lucas Emmanuel Hutomo, and Sienna Healy-Sanchez.

### Attendance and academic achievement

Attendance showed the clearest association with performance:

| Student outcome | Students | Average attendance | Average recorded term score |
|---|---:|---:|---:|
| Met requirement | 16 | 98% | 77.36 |
| Did not meet requirement | 9 | 87% | 41.87 |
| Continued enrolment | 16 | 99% | 76.92 |
| Discontinued enrolment | 9 | 86% | 42.64 |

Students who met requirements and continued enrolment generally had higher attendance and stronger term results. This is an association within the dataset and does not by itself prove that attendance causes higher marks.

### Requirement achievement by student group

- **75% of junior students** met the academic requirements.
- Approximately **61.9% of primary students** met the academic requirements.

The percentages help compare outcomes between differently sized groups. Because there are only 25 students and the groups are unbalanced, these differences should be treated as indicators for further investigation rather than definitive conclusions.

### Learning weaknesses

The two most frequently recorded weaknesses were:

1. **Carelessness** – 13 students
2. **Lack of attention** – 6 students

Incomplete homework and spelling were each recorded for three students.

Carelessness was the most common label, but students in this category also achieved a relatively high average recorded term score. It may therefore describe avoidable errors among otherwise capable students rather than the main cause of low overall achievement.

Students recorded with incomplete homework had the lowest average attendance and term performance. Although this subgroup contains only three students, it indicates that homework completion and participation may deserve closer monitoring.

Following mentor feedback, weaknesses are discussed as contextual insights and teaching recommendations rather than displayed as a standalone chart. This keeps the dashboard focused on measurable outcomes and avoids overemphasising subjective categories.

---

## Higher- and Lower-Performing Student Profiles

### Common characteristics of higher-performing students

- High and consistent attendance
- Strong weekly results across the term
- Fewer extremely low or missing weekly scores
- Achievement of academic requirements
- Greater likelihood of continuing enrolment
- Consistent engagement with assigned work

### Common characteristics of students requiring support

- Lower or inconsistent attendance
- Multiple low weekly scores
- Incomplete homework or difficulty maintaining attention
- Failure to meet academic requirements
- Greater likelihood of discontinuing enrolment

Some students achieved stronger results in Week 10 despite weak results earlier in the term. Educators should therefore review the complete weekly performance pattern rather than judge progress using only the final week.

---

## Recommendations

### 1. Introduce weekly early-intervention flags

Flag a student for review when they:

- Record attendance below 90%
- Score below the expected weekly benchmark
- Submit incomplete homework
- Record declining scores over consecutive weeks

Early identification would allow educators to provide support before performance declines further.

### 2. Provide specific, actionable feedback

Student feedback should state:

- What the student did well
- The exact skill or behaviour requiring improvement
- One action to complete before the next lesson
- How and when progress will be reviewed

For example:

> You applied the correct method, but avoidable calculation errors reduced your final score. For the next task, use the checking checklist and review each calculation before submitting your work.

This is more useful than general feedback such as “be more careful” or “pay more attention.”

### 3. Create short individual improvement plans

Students not meeting requirements could receive a short plan containing:

- One or two priority learning areas
- A weekly attendance target
- A homework-completion target
- A score target for the following weeks
- A scheduled progress review

The plan should contain a small number of achievable actions so that improvement remains manageable and measurable.

### 4. Reduce careless errors through structured checking

The program could introduce:

- End-of-task checking checklists
- A dedicated answer-review period
- Worked examples of common mistakes
- Self-correction activities
- Personal error logs for repeated mistakes

### 5. Improve attention and lesson engagement

Possible strategies include:

- Dividing lessons into shorter activities
- Using visual explanations and practical examples
- Asking frequent checking-for-understanding questions
- Providing short individual practice activities
- Setting one clear learning goal at the beginning of each lesson
- Including brief movement or activity breaks where appropriate

### 6. Strengthen homework monitoring

The program could use:

- A simple homework-completion tracker
- Reminders for students or parents
- Follow-up after repeated incomplete work
- Short catch-up sessions
- Smaller tasks with clear instructions and deadlines

### 7. Review outcomes each term

Management should regularly review:

- Attendance rates
- Requirement-achievement rates
- Weekly score patterns
- Enrolment continuation
- Students receiving intervention
- Student outcomes before and after support

This would help determine whether program changes are producing measurable improvements.

---

## Conclusion

The dashboard suggests that consistent attendance, sustained weekly performance, homework completion, and active participation are associated with stronger academic outcomes.

Higher-performing students generally attended more regularly, maintained stronger results, met academic requirements, and continued their enrolment. Students requiring additional support were more likely to have lower attendance, incomplete work, weaker weekly performance, and discontinued enrolment.

The analysis supports an education program focused on early identification, targeted feedback, attendance monitoring, structured homework support, and individual improvement plans. These strategies would allow educators to respond earlier and give students clearer, more personalised guidance.

---

## Data and Analysis Limitations

- The dataset contains only 25 students.
- Terms 1, 3, and 4 contain different numbers and groups of students.
- Term comparisons are not necessarily based on the same students and should not be treated as direct individual improvement.
- Subject groups are substantially unbalanced, with considerably more Mathematics than English records.
- Attendance contains only three recorded levels: 80%, 90%, and 100%.
- Learning weaknesses are broad categories and may reflect educator judgement.
- The regression line indicates association, not causation.
- Results should be validated using a larger dataset covering more students and comparable terms.
- Calculated score fields and requirement measures should be validated against the agreed business rules before operational use.

---

## Future Improvements

- Add more students and comparable term-level records
- Track the same students consistently across terms
- Add intervention dates and outcomes to measure program effectiveness
- Add homework-completion and assessment-type fields
- Create an individual-student drill-through page
- Add dynamic written insights for the selected filters
- Introduce data-quality validation for score and status calculations
- Apply role-level security if the report is shared with educators or parents

---

## Tools and Skills Demonstrated

- Microsoft Power BI
- Power Query
- DAX
- Data cleaning and transformation
- Relational data modelling
- Data visualisation and dashboard design
- KPI development
- Exploratory and descriptive analysis
- Education performance analysis
- Evidence-based recommendations

---

## Repository Contents

```text
Pioneer-Education-Performance-Dashboard/
├── Pioneer edu dashboard.pbix
├── Performance Overview dashboard.png
├── Student Performance dashboard.png
└── README.md
```

## Author

**Bao Nghi Ngo**  
Business Analytics and Information Systems graduate  
Interested in business analysis, data analytics, process improvement, and dashboard development

