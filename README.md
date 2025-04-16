# STATS 3DA3 Assignment 6
This is the repository for assignment 6.

## Question 1
Consider the diabetes dataset available on Kaggle: https://www.kaggle.com/datasets/mathchi/diabetes-data-set

The goal is to develop a classification model to predict whether a patient has diabetes based on their diagnostic measurements. Additionally, the project will analyze and interpret the logistic regression model to understand its findings.

url = "https://raw.githubusercontent.com/PratheepaJ/datasets/refs/heads/master/ass6-dataset.csv"
df = pd.read_csv(url)
General view of the data frame:
df.head()

df.shape
There are 303 records and 13 features in the data frame. 
The response variable is num, which will be transformed to binary in the analysis.

## Q1(1) Classification Problem: 
The goal is to use medical and personal information (such as age, sex, cholesterol levels, and chest pain type) to predict whether a person has heart disease. Each row in the dataset represents a different patient, and the final column shows if the patient was diagnosed with heart disease. By analyzing these features, we will train a model to classify future patients as either having heart disease or not.

## Q1(2) Whether the data transformation is needed or not:
check the data type of the response variable in the data
df.num.dtype

Since num is a numerical variable but represents categories, it should be converted to a categorical type.

df['num'] = df['num'].astype('category')

## Q1(3) Detailed Description:
df.drop('num', axis=1).describe()
column 2 sex: 1 = male; 0 = female.
column 3 cp: chest pain type (0,1,2,3,4)
column 4 trestbps: resting blood pressure (in mm Hg)
column 5 chol: serum cholesterol in mg/dl
column 8 thalach: maximum heart rate achieved

This heart disease dataset includes 303 patients and 13 clinical variables. The average age is approximately 54.4 years, ranging from 29 to 77. The majority of patients are male (around 68%). 

Most patients reported chest pain types around category 3, with a maximum value of 4.

Resting blood pressure (trestbps) has an average of 131.7 mm Hg, while serum cholesterol (chol) averages 246.7 mg/dl, reaching up to 564 mg/dl. 

The thalach variable (maximum heart rate achieved) ranges from 71 to 202, with a mean of about 149.6.