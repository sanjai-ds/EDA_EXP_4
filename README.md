# EDA_EXP_4   Titanic Survival Analysis using Univariate Analysis
### NAME : Sanjai S
### REGISTER NUMBER : 212223230186
## Aim:

To perform univariate analysis on the Titanic dataset to understand the distribution and characteristics of individual variables (such as Age, Sex, Pclass, Fare, and Survived) and to draw insights about passengers and their survival patterns.


## Algorithm:

**1)Import Libraries:**

Load the required Python libraries (pandas, numpy, matplotlib, seaborn).

**2)Load the Dataset:**

Read the Titanic dataset from available sources (e.g., seaborn’s built-in Titanic dataset or a CSV file).

**3)Data Inspection:**

View the first few rows using head().

Get dataset summary using info() and describe().

**4)Handle Missing Data:**
Identify missing values using isnull().sum() and handle them appropriately (e.g., fill or drop).

**5)Univariate Analysis:**
Perform univariate analysis for each variable:

**Categorical Variables: (e.g., Sex, Pclass, Survived, Embarked)**
Use frequency tables and count plots.

**Numerical Variables: (e.g., Age, Fare)**
Use histograms, box plots, and summary statistics.

**6)Interpretation:**
Analyze distributions, central tendencies, and spread.
Identify patterns (e.g., more passengers in 3rd class, survival differences by gender).


## Program:
```
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df=sns.load_dataset('titanic')
df.info()
df.head()
df.describe()
df.isnull(), value counts()
sex=df['sex'].value_counts()
print(sex)
sur=df['survived'].mean()*100
print(sur, "%")
categories=['sex', 'survived', 'sibsp', 'embarked', 'class', 'who', 'adult_male', 'deck
for i in categories:
plt.figure(figsize=(6,4))
sns.countplot(data=df,x=i)
print(df[i].value_counts())
plt.xlabel(i)
plt.ylabel("Count")
plt.show()
meanage=df['age'].mean()
medianage=df['age'].median()
age_range=(df['age'].min(),df['age'].max())
print(meanage)
print(medianage)
print(age_range)
plt.figure(figsize=(10,10))
sns.histplot(df['age'].dropna(), bins=30, kde=True)
plt.xlabel('age')
plt.ylabel('count')
plt.show()
import seaborn as sns
numerical_features = ['age', 'fare']
for col in numerical_features:
plt.figure(figsize=(6,4))
sns.histplot (df [col], kde=True, bins=30)
plt.title(f'Distribution of {col}')
plt.show()
plt.figure(figsize=(6,4))
sns.boxplot(x=df[col])
plt.title(f'Boxplot of {col}')
plt.show()
print(f"\nSummary Statistics for {col}:\n", df[col].describe())
print("-"*50)
```

## Output:

<img width="1283" height="840" alt="image" src="https://github.com/user-attachments/assets/2b21d43c-3ea2-4905-a37a-65ae72773e0b" />
<img width="1134" height="718" alt="image" src="https://github.com/user-attachments/assets/5be2daf2-604b-4c65-9b9c-9d5e6bdc412b" />
<img width="1140" height="691" alt="image" src="https://github.com/user-attachments/assets/4822674d-0784-4019-9e05-0f9b7f906b59" />
<img width="1181" height="893" alt="image" src="https://github.com/user-attachments/assets/9591dbe4-26e6-4bb6-ae7b-1e90a254f1ea" />
<img width="1086" height="274" alt="image" src="https://github.com/user-attachments/assets/be10fd50-2992-4add-9b24-eb345de6321e" />
<img width="1132" height="841" alt="image" src="https://github.com/user-attachments/assets/e3828c1b-89ed-4ec3-85a9-8588df91643e" />
<img width="1115" height="921" alt="image" src="https://github.com/user-attachments/assets/f76afb7e-6a5a-4bde-936d-e4eaf20c4f42" />
<img width="991" height="869" alt="image" src="https://github.com/user-attachments/assets/3417ff73-9203-4a49-8f51-a85ef9f8729a" />
<img width="1005" height="578" alt="image" src="https://github.com/user-attachments/assets/543bf028-7f29-4d99-9972-93386ae27edc" />
<img width="1055" height="886" alt="image" src="https://github.com/user-attachments/assets/dcd40b88-0283-4b41-9b17-8c2593cb87c3" />

## Result:

From the univariate analysis:

Majority of passengers were male and in 3rd class.

Around 38% survived, majority being females and higher-class passengers.

Age is right-skewed with most passengers aged 20–40 years.

Fare distribution shows a few high outliers for 1st class passengers.

Thus, univariate analysis helps understand the distribution and spread of each individual feature in the Titanic dataset before moving to bivariate or multivariate analysis.
