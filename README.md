# EXNO2DS
# NAME.- THRISHANTH E
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
        ```py
  import pandas as pd
  import numpy as np
  import matplotlib.pyplot as plt
  import seaborn as sns
  dt=pd.read_csv("/content/titanic_dataset.csv")
  dt
 ```
         
![Screenshot 2024-09-13 153035](https://github.com/user-attachments/assets/c1271d70-c329-46c5-aced-a9715ca69a2a)

```py
        dt.info()
```
![Screenshot 2024-09-13 153240](https://github.com/user-attachments/assets/279a8c67-aafb-42aa-b01e-d0ef028d425c)

 ```py
      dt.shape

 ```
![Screenshot 2024-09-13 154013](https://github.com/user-attachments/assets/6f32b99d-518b-4031-a5ea-3b0078a6ccc9)

 ```py
      df.set_index("PassengerId",inplace=True)
      df.describe()
  ```
![Screenshot 2024-09-13 160702](https://github.com/user-attachments/assets/d2e8cb24-0137-427a-ac3b-a575519b190e)

```py
  df.nunique()
```
![Screenshot 2024-09-13 160754](https://github.com/user-attachments/assets/29bf2dd5-e2d7-42be-a1ff-25a8dab14f8c)

```py
  df["Survived"].value_counts()     

```
![Screenshot 2024-09-13 160850](https://github.com/user-attachments/assets/69e47624-7295-448c-a285-ab131411e932)

```py
   per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
   per      
```
![Screenshot 2024-09-13 160934](https://github.com/user-attachments/assets/e99b9af6-30e4-4f52-9b50-c35824373683)

```py
  sns.countplot(data=df,x="Survived")     
```
![Screenshot 2024-09-13 161026](https://github.com/user-attachments/assets/5a14144c-0309-4329-afb2-13cdce3fd9de)

```py
   df.Pclass.unique()
```
![Screenshot 2024-09-13 161132](https://github.com/user-attachments/assets/6bc169b8-77ba-4790-b314-a23f347b160d)


```py
   sns.catplot(x="Sex",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2024-09-13 161340](https://github.com/user-attachments/assets/887552ba-5687-4ca2-851d-641ab142b27d)

```py
    sns.catplot(x="Survived",hue="Sex",data=df,kind="count")
```
![Screenshot 2024-09-13 161503](https://github.com/user-attachments/assets/20f0a2f0-fa30-4555-a786-0eb1606a6220)


```py
  df.boxplot(column="Age",by="Survived")
```
![Screenshot 2024-09-13 161645](https://github.com/user-attachments/assets/2da4c88b-e79c-42c6-988c-9e0638059813)

```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Screenshot 2024-09-13 161738](https://github.com/user-attachments/assets/ae61a369-2f04-4135-acc2-7bd278430d1d)

```py
  sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2024-09-13 161821](https://github.com/user-attachments/assets/5f3c7cb0-29da-4a46-8649-be168769b895)

```py
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```
![Screenshot 2024-09-13 162022](https://github.com/user-attachments/assets/629d80b0-e56b-484a-9d06-50a40ecd1f7e)

```py
 sns.catplot(data=df,col="Survived",x="Sex",hue="Pclass",kind="count")
```
![Screenshot 2024-09-13 162139](https://github.com/user-attachments/assets/fa5e1102-fe95-4386-a75e-8e767b376149)


```py
numeric_df = df.select_dtypes(include=[np.number])
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)
```
![Screenshot 2024-09-13 162225](https://github.com/user-attachments/assets/3c939c8a-4423-4b0e-9302-159e27e0105a)

```py
  sns.pairplot(df)
```
![dsex02](https://github.com/user-attachments/assets/1974c5ba-dabc-437b-be8d-be64184e15fd)



# RESULT
Exploratory Data Analysis on the given data set is completed successfully.



