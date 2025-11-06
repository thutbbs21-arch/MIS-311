# 1. Data Overview 

The Student Performance dataset contains information about students’ academic outcomes and background characteristics that may influence their performance. It includes ***203 rows*** and ***8 columns***, with each row representing an individual student.

<img width="600" height="250" alt="image" src="https://github.com/user-attachments/assets/ce929410-571f-4543-acd0-e16f4d0d15d1" />

_Table 1: Data description_


The dataset features variables such as ***gender, race/ethnicity, parental level of education, and students’ scores in math, reading, and writing***. These variables allow for the examination of how demographic and family background factors relate to academic achievement.

Overall, the dataset is widely used in educational analytics to explore performance patterns, identify potential learning gaps, and support evidence-based strategies aimed at improving student outcomes.

# 2. Data cleaning

## 2.1. Removal of Duplicate Records

To ensure the accuracy and reliability of the dataset, duplicate entries were checked and removed using ***“Remove Duplicates”*** function.
All major columns including ***gender, race_ethnicity, parental_level_of_education, math_score, and reading_score*** were selected to detect identical records.

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/9048e55f-6cdf-4f77-b612-e8c64a4012a1" />

_Figure 1. Columns Selected for Duplicate Checking_

As shown in the process,  with ***203 raw rows***, ***3 duplicate rows*** were found and removed, resulting in ***199 unique*** observations. This step helps maintain data integrity and prevents double-counting, which could otherwise bias the statistical results and insights.


<img width="360" height="179" alt="image" src="https://github.com/user-attachments/assets/83d73646-5f7b-49b1-a604-8711ccb54980" />

_Figure 2. Summary of Duplicate Removal Results_

## 2.2. Handling Missing Data

Missing values were identified in two columns: ***parental_level_of_education*** (categorical) and ***average_score***  (numerical). The blanks were detected using the Filter tool in Excel, which displayed two rows with missing values in both columns. 


<img width="961" height="109" alt="image" src="https://github.com/user-attachments/assets/e15292b7-cf3a-4361-8f3e-172f0b662714" />

_Figure 3. Identifying Blank Values in Average Score Columns_

<img width="958" height="73" alt="image" src="https://github.com/user-attachments/assets/3d206b20-8e22-448c-922e-75ba706e5fb3" />

_Figure 4: Identifying Blank Values in Parental Education Columns_

### 2.2.1. Imputing Average Score

For the variable ***average_score***, some missing values were found due to incomplete data entry. To maintain data consistency, the missing values were recalculated using Excel by dividing the total score by 3 (since each student’s total score represents the sum of three subjects: ***math, reading, and writing***).

The formula used was: <img width="300" height="150" alt="image" src="https://github.com/user-attachments/assets/d4fc0210-018a-4367-9fdc-d28e8df3d7d3" />

<img width="500" height="150" alt="image" src="https://github.com/user-attachments/assets/807e0934-5adf-4c7b-8335-4a75bd1ce5bd" />

_Figure 5. Recalculating Missing Average Score Using Excel Formula_

> This method was chosen because ***average_score*** is a derived variable that depends directly on existing subject scores. Recalculating missing values ensures accuracy and internal consistency, as it relies on already available, valid data rather than estimation or deletion. After this process, no missing values remained in the ***average_score*** column.

### 2.2.2. Imputing Parental Education

To determine appropriate values for the missing entries in the ***parental_level_of_education*** column, a PivotTable was created in Excel to analyze the frequency of each education level within each race/ethnicity group.

As shown in _Figure 6_, the data range ***A1:H200*** from the cleaned dataset was selected, and the PivotTable was inserted through the Insert → PivotTable function.

<img width="434" height="282" alt="image" src="https://github.com/user-attachments/assets/aab4da7c-073d-4041-9125-3e7367689419" />

_Figure 6. Selecting Data Range for PivotTable Creation in Excel_

In the PivotTable field settings:
+ ***Race_ethnicity*** was placed in the Rows area.
+ ***Parental_level_of_education*** was placed in the Columns area.
+ The values area was set to ***Count of parental_level_of_education***.

<img width="269" height="310" alt="image" src="https://github.com/user-attachments/assets/80936c1a-b3d3-49cf-bf57-1cc026e5cd3f" />

_Figure 7. PivotTable Field Settings for Analyzing Parental Education by Ethnicity_

The resulting PivotTable displayed the frequency of each education level across all ethnic groups. From this analysis, it was observed that:
+ **Group A** had associate’s degree as the most common education level.
+ **Group D** had some college as the most common education level.

<img width="898" height="175" alt="image" src="https://github.com/user-attachments/assets/f3d80b7a-92d4-4c3e-b87f-9ffb3035862a" />

_Figure 8. Frequency of Parental Education Levels by Race/Ethnicity Group_

Thus, the two missing values were imputed accordingly:
+ ***Group A → associate’s degree***
+ ***Group D → some college***

> This method was selected because This method was selected because ***parental_level_of_education*** is a categorical variable, making mode imputation the most suitable approach.
> Using the most frequent category within each ethnic group (conditional mode) preserves both the data’s distribution and the relationship between demographic variables, ensuring realistic and unbiased replacements.

# 3.  Descriptive Statistics
## 3.1. Insight 1: Gender-Based Differences in Subject Performance
> “Gender is coded 0/1 (dataset codebook does not specify mapping); analysis treats them as Group 0 and Group 1.”
### 3.1.1. How the insight was generated
To explore the relationship between gender and student academic performance, a PivotTable was created in Excel. 
+ ***Gender*** was placed in the Rows area.
+ The average of ***writing_score, reading_score, and math_score*** were placed in the Values area.

<img width="216" height="290" alt="image" src="https://github.com/user-attachments/assets/4880c235-7899-4cc2-b7a8-c44503bee72f" />

_Figure 9. PivotTable Field Settings for Gender-Based Performance Analysis_

### 3.1.2. Results and Interpretation

<img width="580" height="383" alt="image" src="https://github.com/user-attachments/assets/f5c80374-73e2-47de-b434-9db0fff118ca" />


_Figure 10. Average Subject Scores by Gender_

✍🏻**Reason and Observation**
+ The analysis of average writing, reading, and math scores by gender shows clear performance differences between the two groups (coded as 0 and 1).
+ Group 0 achieved higher scores in writing (72) and reading (72), while group 1 performed slightly better in math (65).
+ This pattern suggests that one gender may have stronger verbal skills, whereas the other demonstrates relatively stronger quantitative ability.

✍🏻**Interpretation and Educational Implication**
+ The difference could result from learning preferences, confidence levels, or social expectations that shape how students engage with each subject.
+ From an educational perspective, this finding highlights the need for balanced teaching approaches that strengthen weaker subject areas for each gender.
+ For instance, teachers might use gender-inclusive learning materials or targeted support programs to improve both literacy and numeracy outcomes.

## 3.2. Insight 2: Impact of Parental Education on Student Performance
### 3.2.1. How the Insight Was Generated
To explore the relationship between parental education and student academic performance, a PivotTable was created in Excel.
+ ***Parental_level_of_education*** was placed in the Rows area.
+ Average of ***average_score*** was placed in the Values area.

<img width="216" height="283" alt="image" src="https://github.com/user-attachments/assets/53807fce-5801-4475-a642-48760b573ebb" />

_Figure 11. PivotTable Field Settings for Parental Education Analysis_

### 3.2.2. Results and Interpretation

<img width="768" height="317" alt="image" src="https://github.com/user-attachments/assets/a724f07a-53dd-4fc5-8127-51ed0588c4c4" />


_Figure 12. Average Student Score by Parental Education Level_

✍🏻**Reason and Observation**
+ This insight investigates how parents’ education levels relate to their children’s academic performance.
+ The results show a positive correlation: students whose parents have a bachelor’s or master’s degree achieve average scores around 72–73, whereas those with high school or lower backgrounds score around 60–62.

✍🏻**Interpretation and Educational Implication**
+ The pattern suggests that higher parental education provides students with greater academic support, learning resources, and motivation at home. This relationship emphasizes the importance of family engagement in education.
+ Schools can apply this insight by developing parent–teacher partnerships or community learning programs that guide parents on how to support their children’s learning, especially for families with lower educational backgrounds.
