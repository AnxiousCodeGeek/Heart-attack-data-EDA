# Heart Attack Exploratory Data Analysis

## Introduction
This project involves analyzing a dataset of heart attack cases to extract meaningful insights. The analysis includes data preprocessing, visualizing distributions, and examining the relationships between different variables. The results are visualized using Seaborn and Plotly for a comprehensive understanding of the data.

## Prerequisites
Install the below libraries:

 - ```pandas```
 - ```seaborn```
 - ```matplotlib```
 - ```plotly```

## Data Description
The dataset used in this analysis is stored in [```heartattack_processed_data.csv```](https://github.com/AnxiousCodeGeek/Heart-attack-data-EDA/blob/main/heartattack_processed_data.csv). The data includes the following columns:
 - Age
 - Gender
 - Heart rate
 - Systolic blood pressure
 - Diastolic blood pressure
 - Result (0 = Negative, 1 = Positive)
 - CK-MB_normalized (Serum CK-MB normalized level)
 - Troponin (ng/ml)

## Working
### Preprocessing
After loading the data, we preprocess it to drop unnecessary columns, and handle missing values.

```python
heartattackeda = heartattackeda.drop(columns="CK-MB")
heartattackeda.info()
heartattackeda.describe()
heartattackeda.isnull().sum()
heartattackeda.nunique()
heartattackeda.sort_values(by = "Age").head(30)
heartattackeda.corr()
```
### Grouping Data by Gender
Grouping the data by gender and calculate the mean of different features:
```python
heartattackeda_1 = heartattackeda.groupby('Gender')[['Age','Heart rate','Systolic blood pressure', 'Diastolic blood pressure','Result']].mean().sort_values(by = 'Age')

Female_heartattackdata = heartattackeda[heartattackeda['Gender'] == 'Female'][['Age','Heart rate','Systolic blood pressure','Diastolic blood pressure','Result']].sort_values(by = 'Age').head(30)
Male_heartattackdata = heartattackeda[heartattackeda['Gender'] == 'Male'][['Age','Heart rate','Systolic blood pressure','Diastolic blood pressure','Result']].sort_values(by = 'Age').head(30)
```
## Vizualizations
We explored and visualize the data using pie chart, bar plot, histograms, and scatterplots. Our work included exploring:
 - Heart Attack ratio, as in whole data, as well as for both genders
 - Gender Ratio
 - Distribution of Risk Factors ( w.r.t. age, blood pressure and results of heart attack - positive and negative)

Full script is available at the link : [heartattack_data_eda.ipynb](https://github.com/AnxiousCodeGeek/Heart-attack-data-EDA/blob/main/heartattack_data_eda.ipynb)
