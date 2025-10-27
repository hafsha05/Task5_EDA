# Task5_EDA
# Task 5: Exploratory Data Analysis (EDA)

## 🎯 Objective
Extract insights from a dataset using *visual* and *statistical* exploration techniques.

---

## 🧰 Tools Used
- *Python*
- *Pandas*
- *Matplotlib*
- *Seaborn*
- *Jupyter Notebook*

---

## 📊 Dataset
Dataset Used: *Titanic-Dataset*  

The dataset contains details about passengers on the Titanic ship such as:
- Passenger ID  
- Survived (1 = Yes, 0 = No)  
- Pclass (Passenger Class)  
- Name, Sex, Age  
- Siblings/Spouses aboard (SibSp)  
- Parents/Children aboard (Parch)  
- Fare, Embarked (Boarding Port)

---

## 🧠 What is EDA?
*Exploratory Data Analysis (EDA)* is the process of exploring, cleaning, and visualizing data to understand patterns, trends, and relationships before modeling.

### Goals of EDA:
- Understand dataset structure and summary.
- Identify missing values, duplicates, or errors.
- Detect patterns, correlations, and outliers.
- Visualize data for better insights.
- Write meaningful observations from each plot.

---

## ⚙️ Steps Followed

### 1️⃣ Importing Libraries

`import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns`

### 2️⃣ Loading Dataset

`df = pd.read_csv("titanic-Dataset.csv")`

### 3️⃣ Exploring Dataset

`df.head()          # View first 5 rows
df.info()          # Check data types and structure
df.describe()      # Summary statistics
df.isnull().sum()  # Check missing values
df['Sex'].value_counts()  # Count gender distribution`

### 4️⃣ Data Visualization

`sns.countplot(x='Sex', hue='Survived', data=df)
plt.title("Survival count by Gender")
plt.show()`

`sns.countplot(x='Pclass', hue='Survived', data=df)
plt.title("Survival count by Passenger Class")
plt.show()`

`sns.histplot(df['Age'].dropna(), kde=True, bins=30)
plt.title("Age Distribution of Passengers")
plt.show()`

`plt.figure(figsize=(6,4))
sns.countplot(x='Survived', data=df_clean)
plt.title('Survival Count (0=No, 1=Yes)')
plt.show()`

`plt.figure(figsize=(8,4))
sns.boxplot(x='Survived', y='Fare', data=df_clean)
plt.title('Fare by Survival')
plt.show()`

`sns.pairplot(df_clean[['Survived','Age','Fare','Pclass']].dropna(), hue='Survived', corner=True)`
