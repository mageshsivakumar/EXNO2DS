# NAME : MAGESH S
# EXP NO 2
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
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/4069d465-7163-4516-959e-a5927d7ed43f)
```
df.info()
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/336e313e-86ed-4ca9-8d6f-12c11c021a96)

```
df.shape
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/e2f8a0d5-e4d7-4242-8897-135b7ba283a5)
```
import pandas as pd
df=pd.read_csv("/content/titanic_dataset.csv")
df.set_index("PassengerId",inplace=True)
print(df.set_index)
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/9d5717de-831f-47bc-b1b2-8397289f3a48)
```
df.describe()
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/f9bc25c7-4d5e-447b-8fb0-918df31c3f1c)
```
df.nunique()
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/1b777e29-4a91-45f3-89fc-253bbce4ed09)
```
df["Survived"].value_counts()
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/55e4fb63-ee1a-4172-8b86-d2b627f2e660)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/7c58eb4c-b52d-4082-bd8d-f590caec9095)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/ad4efdd2-44f9-456f-a4a6-19dee993ca72)
```
df
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/f179e05b-9937-42a9-aa9e-248272de5ec8)

```
df.Pclass.unique()
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/30624b4f-8992-407c-89c7-da46502033d2)

```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/9c114f4f-776a-4cdc-a250-37aace7fa552)
```
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/babf8cfb-be74-4702-b986-7ad16e4f3b62)
```
sns.catplot(x='Survived',hue='Sex',data=df,kind='count')
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/2123b7f7-ff04-4132-af13-36f6b6df03bf)
```
df.boxplot(column='Age',by="Survived")
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/78d02657-3216-4c7e-8eb8-c1a42ac69845)
```
sns.scatterplot(x=df['Age'],y=df["Fare"])
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/566ac388-e884-432b-af8a-ffc9b6f420fb)
```
import matplotlib.pyplot as plt
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/237b77f3-3576-41a2-bf27-747d58cd7e7f)
```
sns.catplot(data=df,col='Survived',x='Sex',hue='Pclass',kind='count')
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/c476e292-9c93-48b9-b376-5c90c1015c7b)
```
import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/7edfb83b-2e25-4385-9333-011243672b41)
```
sns.pairplot(df)
```
![image](https://github.com/Ajith1413/EXNO2DS/assets/139842524/81b2a985-cb2b-4fd1-9753-d8d3d054855d)

# RESULT
     Code are sucessfully executed.
