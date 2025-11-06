1. Data Overview 

The Student Performance dataset contains information about students’ academic outcomes and background characteristics that may influence their performance. It includes 203 rows and 8 columns, with each row representing an individual student.

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/ce929410-571f-4543-acd0-e16f4d0d15d1" />

Table 1: Data description


The dataset features variables such as gender, race/ethnicity, parental level of education, and students’ scores in math, reading, and writing. These variables allow for the examination of how demographic and family background factors relate to academic achievement.

Overall, the dataset is widely used in educational analytics to explore performance patterns, identify potential learning gaps, and support evidence-based strategies aimed at improving student outcomes.

2. Data cleaning

2.1. Removal of Duplicate Records

To ensure the accuracy and reliability of the dataset, duplicate entries were checked and removed using Excel’s “Remove Duplicates” function.
All major columns including gender, race_ethnicity, parental_level_of_education, math_score, and reading_score were selected to detect identical records.

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/9048e55f-6cdf-4f77-b612-e8c64a4012a1" />


Figure 1. Columns Selected for Duplicate Checking

As shown in the process, 3 duplicate rows were found and removed, resulting in 199 unique observations. This step helps maintain data integrity and prevents double-counting, which could otherwise bias the statistical results and insights.


<img width="360" height="179" alt="image" src="https://github.com/user-attachments/assets/83d73646-5f7b-49b1-a604-8711ccb54980" />

Figure 2. Summary of Duplicate Removal Results

2.2. Handling Missing Data

Missing values were identified in two columns: parental_level_of_education (categorical) and average_score (numerical). The blanks were detected using the Filter tool in Excel, which displayed two rows with missing values in both columns. 


<img width="961" height="109" alt="image" src="https://github.com/user-attachments/assets/e15292b7-cf3a-4361-8f3e-172f0b662714" />

Figure 3. Identifying Blank Values in Average Score Columns

<img width="958" height="73" alt="image" src="https://github.com/user-attachments/assets/3d206b20-8e22-448c-922e-75ba706e5fb3" />

Figure 4: Identifying Blank Values in Parental Education Columns

