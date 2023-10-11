# ODD2023-Datascience-Ex-04

# AIM:
To perform Multivariate EDA on the given data set.

# EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
# STEP 1:
Import the built libraries required to perform EDA and outlier removal.

# STEP 2:
Read the given csv file

# STEP 3:
Convert the file into a dataframe and get information of the data.

# STEP 4:
Return the objects containing counts of unique values using (value_counts()).

# STEP 5:
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()

# STEP 8:
Save the final data set into the file.

# PROGRAM:
```

# SuperStore.csv file:

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore (1).csv")
df=pd.DataFrame(data)
df.head()
df.info()
df.describe()
df.isnull().sum()
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

sns.scatterplot(x=df['Region'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)

states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()

sns.boxplot(x=df['Ship Date'],y=df['Sales'])
sns.displot(df, x="Region", hue="Category")
df.corr()
sns.heatmap(df.corr(),annot=True)

# diabetes.csv file:

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes (1).csv")
df
df.describe()
df.info
df.isnull().sum()

sns.scatterplot(x=df['Glucose'],y=df['BloodPressure'])

sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])

Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)

Age=df.loc[:,["BloodPressure","Glucose"]]
Age=Age.groupby(by=["BloodPressure"]).sum().sort_values(by="Glucose")
sns.barplot(x=Age.index,y="Glucose",data=Age)
plt.xticks(rotation = 90)
plt.xlabel=("BloodPressure")
plt.ylabel=("Glucose")
plt.show()

sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])

sns.displot(df, x="Glucose", hue="Outcome")

df.corr()

sns.heatmap(df.corr(),annot=True)
```
# OUTPUT:

# SUPERSTORE:

# DATA FRAME OF SUPERSTORE

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/bb2f1494-3624-41dc-bd38-5d647e469c06)


# Data information

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/5a220e39-6f0a-4b6d-869d-ffcf189fad24)


# Data describing

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/b284d438-572d-4346-bc9d-c26ef54d8058)


# Sum of null values


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/a48ae8fa-3c1c-43ce-a513-806ed7b31b5d)

# After removing null values

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/dac01647-9ef6-4f43-a55c-9a2fcc205c29)

# Scatter plot

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/1f4ba19b-291f-450c-a491-f98836b6f6f8)


# Bar plot

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/a45d5223-b945-4202-b506-986437757ba0)


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/d8033d46-60d3-4b99-8971-52dd0b669c1f)


# Box plot

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/422b53c0-08f0-4720-98d4-5c1773e552fa)

# Dist plot

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/69f3c8ec-83db-4a92-89f7-2d05c405e68f)

# Correlation coefficient interpretation


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/14f7335d-06bc-4674-b563-72a3553f445a)


# Heat map

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/ebdb8426-8858-4158-9321-c2d1549b7d14)

# DIABETES

# DATA FRAME FOR DIABETES

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/3e9571ab-b205-4569-a67f-e08f4a9a3ae3)


# Data information


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/b1388c3e-4a1b-4daa-a8b2-667fff07a620)


# Data describing


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/f9e9f6cb-ebf8-4664-8417-af575abe47f0)


# Sum of null values


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/3f17eb04-3503-4e8b-945c-dd126bcfe267)

# Scatter plot

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/e3515497-52df-419b-808f-52b574d8dc7b)


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/443fedbb-6256-4272-8271-2ec2a5017545)


# Bar plot

![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/548a0c23-90f5-4711-a9e1-2133d87de497)


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/60e286da-3a66-48a8-a0ff-b5b38c49282c)


# Box plot


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/2e42e214-7ed5-4096-b7d8-9405ff76333e)

# Dist plot


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/c26eec48-6d62-419b-9fe1-4fe33c976092)

# correlation coefficient interpretation


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/1d18fc4c-00ca-47c5-8e24-dd84a6d009c0)

# Heat map


![image](https://github.com/Pavithraramasaamy/ODD2023-Datascience-Ex-04/assets/118596964/6eab2754-2c5f-46af-8b00-e1b0ccf0f366)



# RESULT:
   Thus we have read the given data and performed the multivariate analysis with different types of plots.



