# Analysis of High School Standardized Test Data

## Delete me later: Deliverable 3 requirements

1. Overview of the school district analysis: Explain the purpose of this analysis.

3. Summary: Summarize four changes in the updated school district analysis after reading and math scores for the ninth grade at Thomas High School have been replaced with NaNs.

## Delete me later: Deliverible 3 grading rubric

Results:

There is a bulleted list that addresses how each of the seven school district metrics was affected by the changes in the data (10 pt).
Summary:

There is a statement summarizing four changes to the school district analysis after reading and math scores have been replaced (5 pt).

## Project Overview

Presentation to state board of education. Standardized tests in math and science.  Proficiency of performance metrics by school.  Segment by multiple levels:
dist,school,grade,schooltype, budget.

Budget is included and the purpose of this analysis is to calculate budgetary consideraations.

Two copies of this analysis are contained:
* the initial analysis; `name of original file`
* a secondary analysis `name of second file` conducted to remove flawed test data after a cheating scandal was identified in one specific school at one grade level.. analysis was altered to remove all traces of that grade leverl.

## Table of contents

2. Resources
3. The Data
    * Data cleanliness considerations
4. [Analysis](#analysis)
    * General observations
    * Effect of cheating scandal on aggregates
7. Challenges
8. Further analysis
9. [Appendix](#appendix)


## Resources

* jupyter lab (version)
    * Python (version)
    * pandas, os, numpy modules
* VS code

## The Data

Two csv files:
* `schools_complete.csv` contains data for each individua lschool including:
    * SchoolID
    * Name
    * Type
    * Size (student count)
    * Total budget

* `students_complete.csv` contains records for **39,170 student records**, each affiliated with one of the schools in the other csv.
    * Student ID
    * student_name
    * gender
    * grade level
    * school_name
    * reading_score
    * math_score

These two files can be mapped together using the school's name, enabling us to conduct aggregation exercises for the test scores and grade levels.

### Data Cleanliness considerations

Data had to be scrubbed before the initial anlysis due to containing honorifics and professional titles, apparently a common gag among students in this district.

Data was subsequently re-calculated to factor in changes to remove 9th graders at Thomas from the sample set.

## Code refactor

As part of the work on altering the analysis to exclude Thomas High 9th graders, a larger code refactor was undertaken.

Eliminated unecessary print statements and other debug statements in initial analysis for diagnostic purposes and replaced them with more streamlined purpose-driven cells for simplicity and legibility.

Added markdown cells to better document flow of analysis.

Renamed data frames and other artifacts for legibility.

## Analysis <a name="analysis"></a>

### General observations
Current budget is inversely correlated with actual performance.  (How does this analysis compare with charter v district discussion?)

### Effect of cheating scandal on aggregates

All data tables used an anaysis are referenced below in the [Appendix](#appendix).

* District summary:
    * Average math score drops from 79.0 to 78.9, but average reading score remains 81.9.
    * Percent passing math drops from 75% to 74.8%.
    * Percentage passing reading drops from 85.8% to 85.7%.
    * Overall passage rate drops from 65.2% to 64.9%
* School Summary:
    * Thomas High average reading score rises from 83.8 to 83.9, while math stays steady at 83.4.
    * Percent passing math drops from 93.3% to 93.2%.
    * Percentage passing reading drops from 97.3% to 97.2%.
    * Overall passage rate drops from 90.9% to 90.6%
* Top 5 schools:
    * Thomas High's reduced overall passage rate drops it from uncontested #2 ranked school in the district, to a tie with Griffin High School, which also has a 90.6% overall passing rate.
* Math and reading scores by grade:
    * Because the cheating scandal was contained in one grade level at one school, the only difference in this analysis is the missing values for Thomas High 9th graders (listed in the tables below as "nan", which stands for "not a number".)
* The following categories had negligible effect based on calculation methodology and significant figures in output:
    * Scores by school spending
    * Scores by school size
    * Scores by school type

## Challenges

Formatting was a significant concern.  In particular, the ability to retain a formatted column before more analysis needed to be conducted.

## Further analysis 

## Appendix <a name="appendix"></a>

### District aggregation

#### Original
![Original district summary](Analysis/Original/district_summary.png)

#### Revised
![Revised district summary](Analysis/Revised/district_summary.png)

### By school

#### Original
![Original per school results](Analysis/Original/per_school_results.png)

#### Revised
![Revised per school results](Analysis/Revised/per_school_results.png)

### Best performing schools

#### Original
![Original best performing schools](Analysis/Original/top_5_schools.png)

#### Revised
![Revised best performing schools](Analysis/Revised/top_5_schools.png)

### Worst performing schools

#### Original
![Original worst performing schools](Analysis/Original/bottom_5_schools.png)

#### Revised
![Revised worst performing schools](Analysis/Revised/bottom_5_schools.png)

### Math scores by school/grade

#### Original
![Revised math scores by school and grade](Analysis/Original/math_scores_by_grade.png)

#### Revised
![Revised math scores by school and grade](Analysis/Revised/math_scores_by_grade.png)

### Reading scores by school/grade

#### Original
![Original reading scores by school and grade](Analysis/Original/reading_scores_by_grade.png)

#### Revised
![Revised reading scores by school and grade](Analysis/Revised/reading_scores_by_grade.png)

### By per-student budget expenditure

#### Original
![Original binning by per-student budget](Analysis/Original/spending_summary.png)

#### Revised
![Revised binning by per-student budget](Analysis/Revised/spending_summary.png)

### By student body size

#### Original
![Original binning by student body](Analysis/Original/school_size_summary.png)

#### Revised
![Revised binning by student body](Analysis/Revised/school_size_summary.png)

### By school type

#### Original
![Original binning by school type](Analysis/Original/school_type_summary.png)

#### Revised
![Revised binning by school type](Analysis/Revised/school_type_summary.png)

