# Titanic Dataset: Data Cleaning & Preprocessing

![Titanic](https://upload.wikimedia.org/wikipedia/commons/thumb/f/fd/RMS_Titanic_3.jpg/1200px-RMS_Titanic_3.jpg)

A comprehensive data cleaning and preprocessing pipeline for the Titanic dataset, preparing it for machine learning applications.

## 📋 Overview

This Python script performs:
- Missing value imputation
- Categorical feature encoding
- Numerical feature scaling
- Outlier detection and handling
- Data quality validation

## 🛠️ Features

- **Smart Missing Value Handling**:
  - Age: Median imputation
  - Cabin: Column dropped (77% missing)
  - Embarked: Mode imputation
  - Fare: Median imputation

- **Feature Engineering**:
  - Sex converted to binary (0=male, 1=female)
  - Embarked one-hot encoded
  - Non-predictive columns removed (PassengerId, Name, Ticket)

- **Data Normalization**:
  - Standard scaling for numerical features (Age, Fare, SibSp, Parch)

- **Outlier Management**:
  - Visual detection using boxplots
  - Optional IQR-based removal

## 📊 Data Visualization

![Boxplot Screenshot](Boxplot.png)

## 🚀 Usage

1. Ensure required packages are installed:
```
pip install pandas numpy matplotlib seaborn scikit-learn
```

2. Run the Script in Jupyter Notebook or Google colab

3. Output includes:
- Cleaned dataset in memory
- Console logs of transformation steps
- Visualizations of data distributions

## 🧩 Code Structure

```
# 1. Data Loading & Exploration
titanic = pd.read_csv('Titanic-Dataset.csv')

# 2. Missing Value Handling
titanic['Age'].fillna(titanic['Age'].median(), inplace=True)

# 3. Categorical Encoding
titanic['Sex'] = titanic['Sex'].map({'male': 0, 'female': 1})

# 4. Feature Scaling
scaler = StandardScaler()
titanic[numerical_cols] = scaler.fit_transform(titanic[numerical_cols])

# 5. Outlier Handling
def remove_outliers(df, columns):
    # IQR implementation
    return df
```

## 📈 Results
Final cleaned dataset contains:
- 891 observations
- 9 features (after preprocessing)
- Zero missing values
- Properly scaled numerical features

## 🤖 Machine Learning Ready
The output is optimized for:
- Classification models (Survived: 0/1)
- Feature importance analysis
- Model interpretability

## 📚 Dependencies
- Python 3.7+
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn