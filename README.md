
# Loan Prediction Data Analysis Project
This project involves analyzing and processing a loan prediction dataset using Python and the Pandas library. The dataset includes information such as applicant income, co-applicant income, education, marital status, loan amount, and more.

## Getting Started


Importing Libraries
The project starts with importing the Pandas library to handle data manipulation and analysis:
```bash
import pandas as pd
```
The dataset is loaded from a CSV file named Loan Prediction Dataset.csv. A sample of the data is displayed to understand its structure:
```bash
  df = pd.read_csv("Loan Prediction Dataset.csv")
  df.sample(5)
```
The dataset contains 614 entries and 13 columns, as confirmed by the following methods:
```bash
  df.shape
```

Retrieving basic information about the dataset:
```bash
  df.info()
```
### Identifying Missing Values

The dataset initially contained missing values in several columns. These were identified using:
```bash
  df.isnull().sum()
```
### Removing Missing Values
Rows containing missing values were dropped to ensure data consistency:
```bash
  df1 = df.dropna()
```
### Verifying Cleaned Data
After dropping the missing values, the dataset was verified to confirm no null values or duplicates existed.
```bash
  df1.info()
```

### Verifying Cleaned Data
Checking for Duplicate Rows:
```bash
  df1.duplicated().sum()
```
### Data Transformation
Replaced values in the "Married" column to standardize responses:
```bash
  f1['Married'] = df1['Married'].replace({'yes': 'Y', 'no': 'N',  'Yes': 'Y', 'No': 'N', 'Y': 'Y', 'N': 'N'})
```
### Grouping and Visualization
Used groupby() to group data based on the "Married" and "Self_Employed" columns.
```bash
  group_1 = df1.groupby(["Married", "Self_Employed"]).size()
  group_1.plot(kind="bar", title="none", color="black")
```
Group 2: Analysis of "Gender" and "Loan_Status"
```bash
  group_2 = df1.groupby(["Gender", "Loan_Status"]).size()
  group_2.plot(kind="pie", title="none", color="black")
```
### Save the final processed data as a CSV file using:

```bash
  df1.to_csv("Final_sheet.csv")
```














