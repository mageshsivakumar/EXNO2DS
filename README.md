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
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/0c652797-4090-40ca-9af0-f092945c0351)

```
dt.info()
```
![image](https://github.com/user-attachments/assets/a8b99d66-70e8-433a-a153-10b18bb35a04)

```
dt.shape
```
![image](https://github.com/user-attachments/assets/665037a2-b8a6-4be2-8a01-3dcaca5299f9)

```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![image](https://github.com/user-attachments/assets/7a80c49c-d541-4829-8720-650d19a570bf)

```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/faee32e9-8207-4e09-b462-daa0e3affb0d)

```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/ecde6acd-bffb-4dd2-b87a-2a2d9965a392)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/85321619-7986-4001-bb17-bd0c062de1c9)

```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/d4fa9472-9c2e-49b5-8208-a567876c4342)

```
dt
```
![image](https://github.com/user-attachments/assets/8ae44a3c-7726-40f2-b685-ed6030a2e5f6)

```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/93a2f95f-461b-46e8-b945-db4cb2f55e84)

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/148d3158-8c2e-4066-905b-dcd68f8601d1)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/17386307-3894-4e0b-9b18-9ce86d6c9da8)

```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```
![image](https://github.com/user-attachments/assets/ae699e62-0acd-417c-b6eb-70d7861f9272)

```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/43052f3c-bc9b-4688-991e-35124352d5f0)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/35225253-46f5-48b8-976d-0e9b9f9df203)

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/e1e904dd-4f11-4027-a6ba-aba12e87c0d3)

```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```
![image](https://github.com/user-attachments/assets/42e13db0-0079-4cd3-ae89-e23366361420)

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/5e73a056-562f-444f-8e7d-5f89af62520c)

```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/38f8ec21-c424-4a4f-aff5-fa544cfa2fa1)

```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/367dff04-d031-497c-9fa4-644e022cfd57)

# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
