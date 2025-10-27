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

## Interview Questions and Answer


### 1️⃣ What is EDA and why is it important?

Exploratory Data Analysis (EDA) is the process of examining datasets to summarize their main characteristics, often using visual methods.
It helps to understand data patterns, detect anomalies, test assumptions, and identify relationships between variables before applying modeling or machine learning.
Importance: It ensures data quality, guides feature selection, and provides insights for decision-making.

### 2️⃣ Which plots do you use to check correlation?

#### Correlation between numerical variables can be checked using:

-*Heatmap (using `sns.heatmap()`):* shows correlation coefficients between features.
-*Pairplot (using `sns.pairplot()`):* visualizes scatterplots between all numeric variables.
-*Scatter Plot:* useful to examine relationships between two continuous variables.

### 3️⃣ How do you handle skewed data?

#### To handle skewed data:

-Apply log transformation, square root, or Box-Cox transformation to reduce skewness.
-Use robust statistics (median, IQR) instead of mean if the data has outliers.
-Visualize with histograms or boxplots to confirm improvement after transformation.

### 4️⃣ How to detect multicollinearity?

Multicollinearity occurs when independent variables are highly correlated.
#### It can be detected using:

-*Correlation Matrix:* look for correlation coefficients > 0.8 or < -0.8.
-*Variance Inflation Factor (VIF):* VIF > 10 indicates high multicollinearity.

### 5️⃣ What are univariate, bivariate, and multivariate analyses?

-*Univariate Analysis:* analysis of a single variable (e.g., histogram of Age).
-*Bivariate Analysis:* analysis between two variables (e.g., Age vs. Fare).
-*Multivariate Analysis:* analysis among more than two variables (e.g., Age, Fare, and Survival together).

### 6️⃣ Difference between heatmap and pairplot?

-A *heatmap* shows the correlation between all numerical variables using colors to represent the strength of relationships.
It gives a quick overview of which features are strongly or weakly correlated.
-A *pairplot*, on the other hand, displays multiple scatterplots between pairs of variables along with histograms or KDE plots.
It helps to visualize the distribution and relationships in detail between each pair of features.

### 7️⃣ How do you summarize your insights?

#### To summarize insights:

-Use bullet points to highlight *key findings and trends*.
-Mention *relationships*, *outliers*, and *important patterns*.
-Support insights with visuals (plots, charts).
-End with a short *business or data interpretation* — what the data tells you and how it helps decision-making.
