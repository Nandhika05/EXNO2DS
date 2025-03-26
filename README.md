# EXNO2DS

## Name : Nandhika P

## Reg no : 212223040125
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

![image](https://github.com/user-attachments/assets/d9262dba-93d2-4adb-9583-6dd0ca86a39b)

```
df.info()
```

![image](https://github.com/user-attachments/assets/8e6da9d5-8d58-4fae-afe3-9e0d46c1ab47)

```
df.shape
```

![image](https://github.com/user-attachments/assets/1a85141d-8b74-4069-9469-23081e0d57ce)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```

![image](https://github.com/user-attachments/assets/25dde7ef-0e50-4314-b728-2a5ba0a50570)

```
df.shape
```

![image](https://github.com/user-attachments/assets/8df7342e-feeb-4916-b9e4-c4ae3ccf7fc3)

```
df.nunique()
```

![image](https://github.com/user-attachments/assets/28b513ff-6e2e-4d47-87d0-9089b30c6700)

```
df["Survived"].value_counts()
```

![image](https://github.com/user-attachments/assets/57bd6238-28ff-42e8-8d51-a0a48d6f3e1b)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```

![image](https://github.com/user-attachments/assets/eb9b7748-6692-4a7d-a102-400e55dd5601)

```
sns.countplot(data=df,x='Survived')
```

![image](https://github.com/user-attachments/assets/d7c50d24-4ace-4039-bd2c-9cd3fd395858)

```
df
```

![image](https://github.com/user-attachments/assets/4d8cf112-36db-42df-b608-a82f0827401a)

```
df.Pclass.unique()
```

![image](https://github.com/user-attachments/assets/1345d76d-4062-45ac-9d1a-99fb39f5c645)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

![image](https://github.com/user-attachments/assets/4a9b0d4d-5bf5-48b7-9310-73c387fb30c5)

## Bivariate Analysis
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

![image](https://github.com/user-attachments/assets/22970a77-d53f-4b5b-977e-83c7164ee1ad)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```

![image](https://github.com/user-attachments/assets/0f3b91ac-3384-4037-9bd7-0ba84ae2f316)

```
df.boxplot(column="Age",by="Survived")
```

![image](https://github.com/user-attachments/assets/2d6e52f9-9423-4fbf-82fd-71d5589b7a20)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

![image](https://github.com/user-attachments/assets/0e4fbc04-175b-462b-98af-dadc5e4ac685)

```
sns.jointplot(x="Age",y="Fare",data=df)
```

![image](https://github.com/user-attachments/assets/e4ce6d08-c73f-4a3a-89a2-0970b981e590)

```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

![image](https://github.com/user-attachments/assets/28caff4e-fe59-4648-98db-d97c8b0fd273)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/user-attachments/assets/955a3152-cfb9-4435-b9d2-49610504be18)

## Co-relation 

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```

![image](https://github.com/user-attachments/assets/23e71ded-ac6c-4649-83b8-cd5fc350a960)

```
sns.pairplot(df)
```

![image](https://github.com/user-attachments/assets/2aa0d52a-4692-46b3-bba5-e1949d2aa969)


![image](https://github.com/user-attachments/assets/47a0bc5f-8704-4e52-9fcf-f63de1a63378)


# RESULT

We have performed Exploratory Data Analysis on  the given data set successfully.
