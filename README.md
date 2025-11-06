# 1. Data Overview 

The Student Performance dataset contains information about students’ academic outcomes and background characteristics that may influence their performance. It includes 203 rows and 8 columns, with each row representing an individual student.

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/ce929410-571f-4543-acd0-e16f4d0d15d1" />

Table 1: Data description


The dataset features variables such as gender, race/ethnicity, parental level of education, and students’ scores in math, reading, and writing. These variables allow for the examination of how demographic and family background factors relate to academic achievement.

Overall, the dataset is widely used in educational analytics to explore performance patterns, identify potential learning gaps, and support evidence-based strategies aimed at improving student outcomes.

# 2. Data cleaning

## 2.1. Removal of Duplicate Records

To ensure the accuracy and reliability of the dataset, duplicate entries were checked and removed using Excel’s “Remove Duplicates” function.
All major columns including gender, race_ethnicity, parental_level_of_education, math_score, and reading_score were selected to detect identical records.

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/9048e55f-6cdf-4f77-b612-e8c64a4012a1" />

Figure 1. Columns Selected for Duplicate Checking

As shown in the process, 3 duplicate rows were found and removed, resulting in 199 unique observations. This step helps maintain data integrity and prevents double-counting, which could otherwise bias the statistical results and insights.


<img width="360" height="179" alt="image" src="https://github.com/user-attachments/assets/83d73646-5f7b-49b1-a604-8711ccb54980" />

Figure 2. Summary of Duplicate Removal Results

## 2.2. Handling Missing Data

Missing values were identified in two columns: parental_level_of_education (categorical) and average_score (numerical). The blanks were detected using the Filter tool in Excel, which displayed two rows with missing values in both columns. 


<img width="961" height="109" alt="image" src="https://github.com/user-attachments/assets/e15292b7-cf3a-4361-8f3e-172f0b662714" />

Figure 3. Identifying Blank Values in Average Score Columns

<img width="958" height="73" alt="image" src="https://github.com/user-attachments/assets/3d206b20-8e22-448c-922e-75ba706e5fb3" />

Figure 4: Identifying Blank Values in Parental Education Columns

### 2.2.1. Fill Average Score

For the variable average_score, some missing values were found due to incomplete data entry. To maintain data consistency, the missing values were recalculated using Excel by dividing the total score by 3 (since each student’s total score represents the sum of three subjects: math, reading, and writing).

The formula used was: <img width="300" height="150" alt="image" src="https://github.com/user-attachments/assets/d4fc0210-018a-4367-9fdc-d28e8df3d7d3" />

<img width="500" height="150" alt="image" src="https://github.com/user-attachments/assets/807e0934-5adf-4c7b-8335-4a75bd1ce5bd" />

Figure 5. Recalculating Missing Average Score Using Excel Formula

As shown in Figure 5, this calculation ensured that each student record had a valid and consistent average score derived directly from their subject results.
After this process, no missing values remained in the average_score column.

### 2.2.2.Fill Parental Education

To determine appropriate values for the missing entries in the parental_level_of_education column, a PivotTable was created in Excel to analyze the frequency of each education level within each race/ethnicity group.

As shown in Figure 6, the data range A1:H200 from the cleaned dataset was selected, and the PivotTable was inserted through the Insert → PivotTable function.

<img width="434" height="282" alt="image" src="https://github.com/user-attachments/assets/aab4da7c-073d-4041-9125-3e7367689419" />

Figure 6. Selecting Data Range for PivotTable Creation in Excel

In the PivotTable field settings:
+ Race_ethnicity was placed in the Rows area.
+ Parental_level_of_education was placed in the Columns area.
+ The values area was set to Count of parental_level_of_education.

<img width="269" height="310" alt="image" src="https://github.com/user-attachments/assets/80936c1a-b3d3-49cf-bf57-1cc026e5cd3f" />

Figure 7. PivotTable Field Settings for Analyzing Parental Education by Ethnicity

The resulting PivotTable displayed the frequency of each education level across all ethnic groups. From this analysis, it was observed that:
+ Group A had associate’s degree as the most common education level.
+ Group D had some colleges as the most common education level.

<img width="898" height="175" alt="image" src="https://github.com/user-attachments/assets/f3d80b7a-92d4-4c3e-b87f-9ffb3035862a" />

Figure 8. Frequency of Parental Education Levels by Race/Ethnicity Group

Thus, the two missing values were imputed accordingly:
+ Group A → associate’s degree
+ Group D → some college
# 3.  Descriptive Statistics
## 3.1. Insight 1: Gender-Based Differences in Subject Performance
### 3.1.1. How the insight was generated
To explore the relationship between gender and student academic performance, a PivotTable was created in Excel. 
+ Gender was placed in the Rows area.
+ The average of writing_score, reading_score, and math_score were placed in the Values area.

<img width="216" height="290" alt="image" src="https://github.com/user-attachments/assets/4880c235-7899-4cc2-b7a8-c44503bee72f" />

Figure 9. PivotTable Field Settings for Gender-Based Performance Analysis

### 3.2.2. Results and Interpretation

<img width="509" height="401" alt="image" src="https://github.com/user-attachments/assets/a3ca2182-4f1a-4f4b-b252-552a5d37f1fa" />

Figure 10. Average Subject Scores by Gender

Reason and Observation
+ The analysis of average writing, reading, and math scores by gender shows clear performance differences between the two groups (coded as 0 and 1).
+ Group 0 achieved higher scores in writing (72) and reading (72), while group 1 performed slightly better in math (65).
+ This pattern suggests that one gender may have stronger verbal skills, whereas the other demonstrates relatively stronger quantitative ability.

Interpretation and Educational Implication
+ The difference could result from learning preferences, confidence levels, or social expectations that shape how students engage with each subject.
+ From an educational perspective, this finding highlights the need for balanced teaching approaches that strengthen weaker subject areas for each gender.
+ For instance, teachers might use gender-inclusive learning materials or targeted support programs to improve both literacy and numeracy outcomes.
