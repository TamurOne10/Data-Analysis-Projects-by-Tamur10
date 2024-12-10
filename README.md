# Exploratory Data Analysis (EDA) of the OD Student Satisfaction Survey

Project Overview

This project involves performing exploratory data analysis (EDA) on the "OD Student Satisfaction Survey" dataset. The goal is to understand patterns, trends, and insights into student satisfaction across various courses and departments. The analysis includes data cleaning, statistical summary, and visualization to derive meaningful interpretations.

Table of Contents

Importing Libraries

Loading the Dataset

Data Exploration

Data Cleaning

Statistical Summary

Data Insights and Visualizations

Key Observations

Requirements

1. Importing Libraries

The analysis utilizes the following Python libraries:

pandas: For data manipulation and analysis.

numpy: For numerical computations.

matplotlib.pyplot: For basic plotting.

seaborn: For enhanced data visualization.

plotly.express: For interactive visualizations.

warnings: To suppress unnecessary warnings.

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import plotly.express as px
import seaborn as sns
import warnings

2. Loading the Dataset

The dataset is loaded from a CSV file with the latin-1 encoding.

df = pd.read_csv('Student_Satisfaction_Survey.csv', encoding='latin-1')

Dataset Columns:

SN: Serial number.

Total Feedback Given: Number of feedback submissions.

Total Configured: Total number of configurations.

Questions: Feedback questions.

Weightage 1-5: Scores based on responses.

Average/ Percentage: Overall average/percentage score.

Course Name: Full course name.

Basic Course: Generalized course category.

3. Data Exploration

Initial Exploration

Displaying the first and last rows of the dataset:

df.head()
df.tail()

Checking dataset information:

df.info()

Checking for null and duplicate values:

df.isnull().sum()
duplicates = df.duplicated()
print('Number of duplicate entries:', duplicates.sum())

Observations:

The dataset contains 580 entries with 12 columns.

No missing or duplicate values were found.

4. Data Cleaning

Steps:

Verified data types and ensured appropriate encoding.

Identified and listed unique values in key columns:

df['Questions'].unique()
df['Basic Course'].unique()

Verified spelling consistency and removed any inconsistencies in column names.

5. Statistical Summary

Generated a statistical summary to understand the central tendencies and spread:

df.describe()

Key Metrics:

Count, mean, standard deviation, min, and max values for numerical columns.

6. Data Insights and Visualizations

Key Analysis Performed:

Average Feedbacks Given by Departments:

Grouped data by the Basic Course column to compute average feedback per department.

feed_back = df.groupby('Basic Course')['Total Feedback Given'].mean()
print(feed_back)

Visualizations:

Distribution of Feedbacks:

fig = px.violin(df, y='Total Feedback Given', title='Distribution of Total Feedback Given')
fig.show()

Question-Wise Scores:
Plotted average scores for each question across departments.

Interactive Insights:
Utilized plotly for dynamic data representation.

7. Key Observations

Feedback Distribution: Certain courses receive significantly more feedback than others.

Student-Centric Learning: Courses focusing on participative methods have higher satisfaction scores.

ICT Utilization: Higher ICT (Information and Communication Technology) adoption correlates with improved feedback.

8. Requirements

Software and Libraries:

Python 3.7+

Libraries: pandas, numpy, matplotlib, seaborn, plotly

Dataset:

File: Student_Satisfaction_Survey.csv

Conclusion

This analysis provides actionable insights into student satisfaction, emphasizing areas such as teaching quality, ICT usage, and student engagement. Further analysis and predictive modeling could be conducted to enhance decision-making for educational improvements.
