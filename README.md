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
DONE BY : JAI HARISH R
REG NO: 212224040124
```

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv('/content/titanic_dataset.csv')
df.head()
```
<img width="1387" height="329" alt="image" src="https://github.com/user-attachments/assets/8e05c810-f152-4eb2-ab20-b47fb0cad33f" />

```python
df.info()
```
<img width="832" height="428" alt="image" src="https://github.com/user-attachments/assets/e2fea6c5-a09a-4163-93d9-e22312cd2c4d" />

```python
df.dtypes
```
<img width="866" height="578" alt="image" src="https://github.com/user-attachments/assets/d3632bff-612d-4e43-ae46-76c7a41ac6dd" />

```python
df.describe()
```
<img width="1218" height="379" alt="image" src="https://github.com/user-attachments/assets/0a6f4dda-bed7-4ee7-a105-6439753c8fd7" />

```python
df["Age"].value_counts()
```
<img width="1008" height="611" alt="image" src="https://github.com/user-attachments/assets/032c288f-c9cc-404f-a427-01878a628088" />

```python
df.shape
```
<img width="899" height="54" alt="image" src="https://github.com/user-attachments/assets/6373fd9e-999b-4744-a38f-115a4c5a77f7" />

```python
df.set_index("PassengerId",inplace=True)
df.describe()
```
<img width="1248" height="373" alt="image" src="https://github.com/user-attachments/assets/e3854b06-fdc2-476f-865f-0336e6ae68bd" />

```python
df.nunique()
```
<img width="778" height="523" alt="image" src="https://github.com/user-attachments/assets/2da8a330-e555-4c0d-8612-01df9f54c3b1" />

```python
sns.countplot(data=df,x="Survived")
```
<img width="1099" height="568" alt="image" src="https://github.com/user-attachments/assets/64d7294b-2b5f-4d7d-8ec2-05a2a8fa3a8b" />

```python
df.Pclass.unique()
```

<img width="742" height="59" alt="image" src="https://github.com/user-attachments/assets/233c237c-2ff2-4fc0-9675-323165f8f213" />

```python
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1401" height="627" alt="image" src="https://github.com/user-attachments/assets/d641fcbd-5307-4ace-b637-fdb43865ee1a" />

```python
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="1282" height="664" alt="image" src="https://github.com/user-attachments/assets/211f4ced-8973-4bdc-b1f9-67409700a077" />

```python
df.boxplot(column="Age",by="Survived")
```
<img width="1062" height="629" alt="image" src="https://github.com/user-attachments/assets/2674ebf1-3653-4f41-a46d-ab189f7d9176" />

```python
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="1081" height="573" alt="image" src="https://github.com/user-attachments/assets/8bb7875e-bc61-4c38-8c6c-ba89fe4c89c7" />

```python
fig, ax1 = plt.subplots(figsize=(10,5))
p = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="1396" height="571" alt="image" src="https://github.com/user-attachments/assets/916f510f-66c7-4f25-b5df-823cf13ff666" />

```python
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1407" height="647" alt="image" src="https://github.com/user-attachments/assets/3fea679a-3295-43dd-9f2f-32da2fcc9d70" />

```python
corr = df.select_dtypes(include=np.number).corr()
sns.heatmap(corr, annot=True)
```
<img width="992" height="569" alt="image" src="https://github.com/user-attachments/assets/3657e958-0709-45a4-9f71-7b86fcb422f9" />

# RESULT
Hence performing Exploratory Data Analysis on the given data set is successfully executed.
