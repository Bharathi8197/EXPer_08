Exp 8: Exploratory Data Analysis on Wine Quality Dataset

AIM:
To perform exploratory data analysis (EDA) on the Wine Quality dataset using Python to understand key patterns, feature relationships, and correlations that influence wine quality.

EQUIPMENTS REQUIRED:
Python
Libraries: pandas, matplotlib, seaborn

ALGORITHM:
Load the wine dataset using the URL.
Perform initial inspection and cleaning.
Generate statistical summaries.
Visualize the distribution of variables.
Plot correlations using a heatmap.
Draw pairplots and boxplots for deeper analysis.
Interpret insights about the data.

PROGRAM:

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Step 1: Load the dataset from URL
url = 'https://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/winequality-red.csv'
df = pd.read_csv(url, sep=';')

# Step 2: Display basic information
print("Dataset Head:\n", df.head())
print("\nDataset Info:\n")
print(df.info())

# Step 3: Check for missing values
print("\nMissing values:\n", df.isnull().sum())

# Step 4: Summary statistics
print("\nStatistical Summary:\n", df.describe())

# Step 5: Distribution of wine quality
plt.figure(figsize=(8, 5))
sns.countplot(x='quality', data=df, palette='Set2')
plt.title("Distribution of Wine Quality")
plt.xlabel("Quality")
plt.ylabel("Count")
plt.show()

# Step 6: Correlation Heatmap
plt.figure(figsize=(12, 8))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm', fmt=".2f")
plt.title("Correlation Heatmap of Wine Features")
plt.show()

# Step 7: Boxplot of alcohol vs quality
plt.figure(figsize=(8, 5))
sns.boxplot(x='quality', y='alcohol', data=df, palette='Set3')
plt.title("Alcohol Content by Wine Quality")
plt.show()

# Step 8: Pairplot (optional, heavier)
# sns.pairplot(df, hue='quality', palette='husl')
# plt.show()


EXPECTED OUTPUT:
A count plot of wine quality ratings.
A correlation heatmap showing strong/weak relationships.
Boxplot showing how alcohol levels affect quality.
Summary statistics like mean, std, min, and max for all variables.

RESULT:
The EDA helps understand the factors affecting wine quality. Features like alcohol, volatile acidity, and sulphates show significant correlation with wine quality.
