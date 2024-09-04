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
# Developed by: Dharshini V
# Register no: 212223040038

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
```
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/5ba63490-0329-464c-b2bc-7fac54495cca)

```
df.info()
```
![image](https://github.com/user-attachments/assets/30015ae0-abd1-4002-ab67-f36a08b36f14)

```
df.shape
```
![image](https://github.com/user-attachments/assets/d785b61d-2ee2-46fd-8f48-e6aa03d698d2)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/d6017fda-b37a-4e09-acc8-edc9a6197e28)

```
df.shape
```
![image](https://github.com/user-attachments/assets/83ba4510-e68d-456f-8b9c-735ab5187685)

# Categorical data analysis
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/227e261f-af3e-4992-babe-b2248f394494)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/83546edc-d496-4957-9550-e4872a793102)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/bedce491-5d51-4bf8-9a65-a8423fa91a6c)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/32e3c73e-adf9-4af9-a3aa-412cfa0acf62)

```
df
```
![image](https://github.com/user-attachments/assets/12db591e-a7bb-4e49-8914-62c29ad5b719)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/3dcb00e7-f804-49c8-95cc-62fdcb4e5c99)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/9c254cfd-2932-430d-98e0-cf922d956625)

# Bivariate Analysis

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/cbebd4de-0345-4d12-9b31-56b8d4ae910e)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/7fab29d5-8449-41b8-bd77-ecdbfa1a4122)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/b19692e2-5028-4e65-88ef-300d508bef65)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/f90891b4-187e-4efc-90f7-f53a8c726412)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/b50607ea-d027-472e-83ac-f1032080e160)

# Multivariate Analysis

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/70d5a074-37bf-4848-9342-853bc4c20c0a)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/7ba1f006-4504-462b-8e8b-4eaa62707d1b)

# Co-relation

```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/245b1353-dbc4-4944-90b3-0e46d791a390)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/b60ad170-c2b9-4302-8cbb-b658f6700611)

# RESULT
        We have performed Exploratory Data Analysis on the given data set successfully
