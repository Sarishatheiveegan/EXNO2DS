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
### DEVELOPED BY:MARINO SARISHA
### REG NO:22223240084
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
![Screenshot 2025-03-27 153005](https://github.com/user-attachments/assets/0fee265d-d537-4068-b4c8-65a8df7580aa)

```
df.info()
```
![Screenshot 2025-03-27 153018](https://github.com/user-attachments/assets/08a3ce36-eccf-427d-a29e-624e7c7e1dc2)

```
df.shape
```
![Screenshot 2025-03-27 153027](https://github.com/user-attachments/assets/f4c64902-e544-4571-9e6f-01cd909689a5)

```
 df.set_index("PassengerId",inplace=True)
 df.describe()
```
![Screenshot 2025-03-27 153034](https://github.com/user-attachments/assets/7dd19ab8-b132-4852-9f7a-cc834f99b303)

```
 df.nunique()
```
![Screenshot 2025-03-27 153051](https://github.com/user-attachments/assets/2a8d9c2f-4b68-4ad9-a881-cd3f3742656e)

```
 df["Survived"].value_counts()
```
![Screenshot 2025-03-27 153108](https://github.com/user-attachments/assets/71421db8-8e8f-47d5-aec1-05a484bcb6c6)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2025-03-27 153119](https://github.com/user-attachments/assets/0b5df077-627a-46ab-a419-93d704d06d57)

```
 sns.countplot(data=df,x="Survived")
```
![Screenshot 2025-03-27 153128](https://github.com/user-attachments/assets/ab311078-ae5d-4f9e-be89-6a5f01da7699)

```
df.Pclass.unique()
```
![Screenshot 2025-03-27 153221](https://github.com/user-attachments/assets/2d8aaa82-e89d-4986-82e2-62b10cd73e1d)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2025-03-27 153231](https://github.com/user-attachments/assets/5439f8ab-d9c9-41a2-b7e2-fa6475858bb9)

```
 sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2025-03-27 153311](https://github.com/user-attachments/assets/4893c4cf-efe2-4230-95fb-5f9a96dbe7bb)

```
 sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![Screenshot 2025-03-27 153321](https://github.com/user-attachments/assets/42b8170e-0c78-43b6-a4bb-4f1cac885799)

```
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-03-27 153331](https://github.com/user-attachments/assets/f5645d3c-43a7-4e5f-b7f6-44127916ebb4)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Screenshot 2025-03-27 153412](https://github.com/user-attachments/assets/9dcddb70-0fb4-4f11-934d-2fca024b3c3b)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2025-03-27 153420](https://github.com/user-attachments/assets/70e4ded8-b648-46f1-805e-2a03fc272bf4)

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![Screenshot 2025-03-27 153431](https://github.com/user-attachments/assets/f7ce5b9d-2a36-47ec-9a97-076cf925c30c)

```
 sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2025-03-27 153447](https://github.com/user-attachments/assets/6a1f79d3-0f29-4d9d-a35a-52d806153df7)

```
# Select only numeric features for correlation calculation
numeric_df = df.select_dtypes(include=np.number)

# Calculate the correlation matrix
corr = numeric_df.corr()

# Plot the heatmap
sns.heatmap(corr, annot=True)
```
![Screenshot 2025-03-27 153456](https://github.com/user-attachments/assets/a6dba043-3ed6-4c1d-a1e6-c0669634d1b9)

```
sns.pairplot(df)
```
![Screenshot 2025-03-27 153554](https://github.com/user-attachments/assets/73ac35fe-d545-4ac9-a98a-7bc6b9b7e31d)

# RESULT
     We have perfomed exploratory data analysis on the given data set successfully.
