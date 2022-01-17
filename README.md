# school-district-analysis

## Overview
This analysis uses pandas in Jupyter Notebook to visualize relationships between student performance at 14 schools and several other variables: school size, type, and budget per student. In addition, it examines the impact of discounting untrustworthy data by removing the 9th grade scores from a school suspected of tampering with those grades, then analyzing the resulting changes to that school's overall performance.

## Results
### Impact to District Summary
At the district level, the impact is negligable: the average math score has been nudged slightly lower, but the passing percentages are unchanged. 

Note: in the dataframes displayed below, the scores and passing percentages have been corrected to exclude the 9th grade students from Thomas High School (the group whose grades showed evidence of tampering), but these students have not been removed from the total count of students. This split is deliberate and consistent throughout this analysis: while the scores and passing percentages at this high school reflect only the 10th-12th graders, removing the 9th graders from the overall student count would potentially impact other metrics calculated in this analysis (school size categorization and budget per student), further diminishing the accuracy of any metrics concerning Thomas High School.

Original dstrict summary
![district summary](Resources/district_summary_df.png)
Corrected district summary
![district summary corrected](Resources/district_summary_df_corrected.png) 

### Impact to School Summary

Here too, the impact of removing the fraudulent grades makes minimal changes to the metrics recorded for Thomas High SChool
- average math score decreases from 83.4 to 83.35
- average reading score increases from 83.8 to 83.9
- % passing math descreases from 93.3 to 93.1
- % passing reading decreases 97.3 to 97.0
- % overall passing decreases from 90.9 to 90.6

With such little gain, and penalties for academic dishonesty, one wonders why Thomas High School bothered to cheat at all!
- Original school summary
![per school summary](Resources/per_school_summary_df.png)
- Corrected school summary
![per school summary corrected](Resources/per_school_summary_df_corrected.png)

### Impact to Relative Performance
Removing the altered grades does not change Thomas High School's relative performance: it remains the second-highest performing school in the district, though the gap between it and the third-ranking school is lessened.
- Top schools (original)
![top schools](Resources/top_schools.png)
- Top schools (corrected)
![top schools corrected](Resources/top_schools_corrected.png)

### Impact to Specified Metrics
School district grades were analyzed along several different axes, both before and after the removal of the fraudulent scores. Here we can see impact to these metrics, including average scores by: grade and school, school spending, school size, and school type.
- Math and reading scores by grade, aside from the specific group whose scores were removed, are unaffected
    |Math by Grade|Math by Grade, Corrected|Reading by Grade|Reading by Grade, Corrected|
    |---|---|---|---|
    |![math scores by grade](Resources/math_scores_by_grade.png)|![math scores by grade, corrected](Resources/math_scores_by_grade_corrected.png)|![reading scores by grade](Resources/reading_scores_by_grade.png)|![reading by grade, corrected](Resources/reading_scores_by_grade_corrected.png)
- Scores by school spending: Thomas High School is in the third spending range, $630-644, so this is where we would expect to see any changes. However, the difference in the school's scores is so small that it does not impact the group average
    - Scores by spending (original)
![scores by spending](Resources/spending_summary_df.png)
    - Scores by spending (corrected)
![scores by spending, corrected](Resources/spending_summary_df_corrected.png)
- Scores by school size: Thomas is a medium-sized school, but once more, thre removal of 461 students' scores is too small to impact the averaged scores the whole group. With or without the altered scores, small to medium-sized schools greatly outperform large schools
    - Scores by school size (original)
![scores by size](Resources/size_summary_df.png)
    - Scores by school size (corrected)
![scores by size, corrected](Resources/size_summary_df_corrected.png)
- Scores by school type is also unchanged. Charter schools continue to significantly outperform district schools in all metrics, even with the removal of the altered scores.
    - Scores by type (original)
![scores by type](Resources/type_summary_df.png)
    - Scores by type (corrected)
![scores by type, corrected](Resources/type_summary_df_corrected.png)

## Summary

Removing the altered test scored did make small changes to Thomas High School's math and reading scores, as well as the percentage of students passing math, reading, or both. However, the students whose scores were removed accounted for only 1% of the district's students, a change so small that it had no impact on the metrics of either the entire district or smaller subsets of schools grouped by spending, size, or type.