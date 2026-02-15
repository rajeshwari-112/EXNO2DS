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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
<img width="568" height="239" alt="image" src="https://github.com/user-attachments/assets/1a84249e-1dae-48cf-8547-75ad008cb04e" />

  df.info()
  
 <img width="335" height="296" alt="image" src="https://github.com/user-attachments/assets/46a53c1d-2f77-4a1f-9dd9-9c3ff19ee656" />

df.shape()

<img width="119" height="31" alt="image" src="https://github.com/user-attachments/assets/262bc3c7-6eea-46a0-8fa9-ded3d7c2d915" />

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
<img width="533" height="256" alt="image" src="https://github.com/user-attachments/assets/055760fe-723b-489c-905f-bc6d387f2bb7" />

df.shape

<img width="119" height="36" alt="image" src="https://github.com/user-attachments/assets/b67e74ed-9f08-4ea1-bb14-b67f19e9eea2" />


df.nunique()

<img width="191" height="373" alt="image" src="https://github.com/user-attachments/assets/770cac6f-aab9-4690-a165-d7a1170331d5" />

df["Survived"].value_counts()

<img width="161" height="149" alt="image" src="https://github.com/user-attachments/assets/314db7c9-02c0-4d17-8864-7d2a77143966" />

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
<img width="229" height="153" alt="image" src="https://github.com/user-attachments/assets/9141ea4f-e9d4-4166-a296-68e1dbab874f" />

sns.countplot(data=df,x="Survived")

<img width="483" height="347" alt="image" src="https://github.com/user-attachments/assets/671fb688-97d7-4713-8125-1af37a661708" />

df

<img width="565" height="239" alt="image" src="https://github.com/user-attachments/assets/c9298433-9add-42e7-9fa3-2fcf7feda395" />

df.Pclass.unique()

<img width="155" height="30" alt="image" src="https://github.com/user-attachments/assets/39631946-aa45-4203-bcb0-aa9d7d43e374" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="550" height="242" alt="image" src="https://github.com/user-attachments/assets/1457177f-2ea8-4f73-b306-08188ab61097" />

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)

<img width="554" height="348" alt="image" src="https://github.com/user-attachments/assets/ac920ef6-920b-4cfa-929d-ece91a79ab69" />

Bivariate Analysis

sns.catplot(x="Survived",hue="Gender",data=df,kind="count")

<img width="652" height="397" alt="image" src="https://github.com/user-attachments/assets/406a57b5-89ba-4aa9-8a06-897ffb5dd62d" />

df.boxplot(column="Age",by="Survived")

<img width="512" height="395" alt="image" src="https://github.com/user-attachments/assets/07e3c541-5787-4400-a816-6e96d5ff0e9c" />

sns.scatterplot(x=df["Age"],y=df["Fare"])

<img width="571" height="351" alt="image" src="https://github.com/user-attachments/assets/f3f7db1b-4400-47ec-9c62-14fc237a26a8" />

sns.jointplot(x="Age",y="Fare",data=df)

<img width="464" height="380" alt="image" src="https://github.com/user-attachments/assets/edb57b02-690e-48e7-999a-0b2b4a96a381" />
Multivariate Analysis

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="509" height="311" alt="image" src="https://github.com/user-attachments/assets/eeecc98d-213d-457b-b6ab-c7b6a34d3fc6" />

sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")

<img width="563" height="272" alt="image" src="https://github.com/user-attachments/assets/abf324ee-1398-4453-b097-6a830be1679d" />

```
df_numeric = df.select_dtypes(include=['number'])
corr=df_numeric.corr()
sns.heatmap(corr,annot=True)
plt.show()
```
<img width="439" height="365" alt="image" src="https://github.com/user-attachments/assets/9e36bc99-5c69-47c9-a287-5c85a37cf506" />

sns.pairplot(df)

<img width="431" height="424" alt="image" src="https://github.com/user-attachments/assets/08d8cf7c-0f96-480c-93a8-97ca7f0857bc" />

# RESULT
        <<INCLUDE YOUR RESULT HERE>>
