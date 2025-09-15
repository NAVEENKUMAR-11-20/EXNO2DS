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
DONE BY : NAVEEN KUMAR P
REG NO: 212224240102
```

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv('/content/titanic_dataset.csv')
df.head()
```
<img width="1416" height="337" alt="image" src="https://github.com/user-attachments/assets/3b2e222e-ed5d-4ea7-a296-56758f301f7e" />

```python
df.info()
```
<img width="765" height="444" alt="image" src="https://github.com/user-attachments/assets/bd2e16c4-9364-439e-be3f-e246726bef68" />

```python
df.dtypes
```
<img width="1287" height="578" alt="image" src="https://github.com/user-attachments/assets/824a2d93-4033-4950-b27b-a5deea46352f" />

```python
df.describe()
```
<img width="1350" height="385" alt="image" src="https://github.com/user-attachments/assets/4c6e65b8-39af-4463-8955-29a0f1d693d8" />


```python
df["Age"].value_counts()
```
<img width="654" height="616" alt="image" src="https://github.com/user-attachments/assets/a67b1868-7920-4d35-ab15-8a52a486efb6" />

```python
df.shape
```
<img width="326" height="50" alt="image" src="https://github.com/user-attachments/assets/371b4427-20ca-4e89-bc0f-c0bccd5a25de" />

```python
df.set_index("PassengerId",inplace=True)
df.describe()
```
<img width="947" height="383" alt="image" src="https://github.com/user-attachments/assets/4dba225c-d7de-494f-adbb-ea417f22476b" />

```python
df.nunique()
```
<img width="494" height="541" alt="image" src="https://github.com/user-attachments/assets/222a4123-ced9-4aae-b4e0-00b362714d05" />

```python
sns.countplot(data=df,x="Survived")
```
<img width="819" height="586" alt="image" src="https://github.com/user-attachments/assets/7e688f0f-4618-4f17-a68b-d183151079c0" />

```python
df.Pclass.unique()
```

<img width="254" height="47" alt="image" src="https://github.com/user-attachments/assets/02143fa3-57f6-4e5d-9995-a94f8ec36958" />

```python
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1391" height="648" alt="image" src="https://github.com/user-attachments/assets/9edd209d-eca2-4b00-baf3-d3d327183ddb" />

```python
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="987" height="654" alt="image" src="https://github.com/user-attachments/assets/ffe1c5bc-7ef9-40e1-981f-e034ad7aa9aa" />

```python
df.boxplot(column="Age",by="Survived")
```
<img width="789" height="623" alt="image" src="https://github.com/user-attachments/assets/7a0bface-7e03-4c4a-8a00-7fb8ee1c9828" />

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
