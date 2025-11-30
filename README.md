# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```python
import pandas as pd
import numpy as np
import seaborn as sns

df = pd.read_csv("C:\DS\Titanic_dataset.csv")

df.info()
```
<img width="459" height="476" alt="image" src="https://github.com/user-attachments/assets/993aa817-04f3-49c1-822e-ceab7032a658" />

```python
df.describe()
```
<img width="874" height="346" alt="image" src="https://github.com/user-attachments/assets/13476a1e-9bb5-4e2c-a427-5fe0300b7211" />

```python
df.dtypes
```
<img width="288" height="353" alt="image" src="https://github.com/user-attachments/assets/11e6d476-45c9-489e-a15c-2b8fe10cd7a0" />

```python
df.shape
```
<img width="125" height="45" alt="image" src="https://github.com/user-attachments/assets/a413c5ae-75d7-44c3-8a83-3ff10daaebec" />

```python
df.value_counts()
```
<img width="1555" height="323" alt="image" src="https://github.com/user-attachments/assets/7e1686a9-f854-444b-b102-a342a08b8578" />

```python
df['Age'].value_counts()
```
<img width="476" height="349" alt="image" src="https://github.com/user-attachments/assets/289904b6-5b60-46e7-b5f7-606022f71c18" />

```python
df.nunique()
```
<img width="292" height="356" alt="image" src="https://github.com/user-attachments/assets/f930e48f-b83a-4acb-8054-9ba0a7361c58" />

```python
sns.countplot(data=df, x='Survived')
```
<img width="762" height="621" alt="image" src="https://github.com/user-attachments/assets/47761364-aa14-4b9a-8c59-10351f82c813" />

```python
df.rename(columns={'Sex': 'Gender'}, inplace=True)
df
```
<img width="1452" height="473" alt="image" src="https://github.com/user-attachments/assets/0e9f9928-b43f-4093-b60c-128ad7baa7cc" />

```python
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="929" height="691" alt="image" src="https://github.com/user-attachments/assets/c9725960-4cca-4684-9b99-97606ae27c9a" />

```python
df.boxplot(column='Age', by='Survived')
```
<img width="743" height="666" alt="image" src="https://github.com/user-attachments/assets/726888b8-9fe2-40db-b817-026cf78031b5" />

```python
sns.scatterplot(x=df['Age'], y=df['Fare'])
```
<img width="757" height="620" alt="image" src="https://github.com/user-attachments/assets/04b10bed-4c07-41b0-903d-ef923cce8af7" />

```python
import matplotlib.pyplot as plt

fig, ax1 = plt.subplots(figsize=(8,5))
plot = sns.boxplot(ax=ax1, x='Pclass', y='Age', hue='Gender', data=df)
```
<img width="857" height="553" alt="image" src="https://github.com/user-attachments/assets/1fb5a652-757c-4005-9050-50847d785eb0" />

```python
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
<img width="1382" height="668" alt="image" src="https://github.com/user-attachments/assets/79938b7c-eb13-4e88-abd4-0446513ed06e" />

```python
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```
<img width="1363" height="689" alt="image" src="https://github.com/user-attachments/assets/6bc2e726-9327-47d0-854a-5bd553a18c76" />

```python
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="779" height="643" alt="image" src="https://github.com/user-attachments/assets/698064a6-4068-48a5-a0b3-b961b542a406" />

```python
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
<img width="760" height="625" alt="image" src="https://github.com/user-attachments/assets/a3c55273-5765-48ea-9a3c-2da0d412c5c9" />

# RESULT
Thus the code has been executed sucessfully
