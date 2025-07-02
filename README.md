# Analyzing-Student-Habits-and-Academic-Performance-Predictive-Modelling-Key-Success-Factors
This project analyzes a dataset of 10,000 university student records to predict academic performance (exam scores) and identify key influencing factors, such as study time, sleep hours, social media usage, and mental health. It implements and compares four regression models—Linear Regression, Decision Tree, Random Forest, and Gradient Boosting—using Python and scikit-learn, with comprehensive data preprocessing, exploratory data analysis (EDA), and model evaluation.

Repository Structure:
```
├── Main.ipynb              # Jupyter notebook with data analysis and modeling
├── data/                   # Directory for dataset (not included, synthetic data used)
├── requirements.txt        # Required Python libraries
├── README.md               # Project documentation

```

Dataset
The dataset consists of 10,000 student records with the following features:

Continuous Variables: Study time per day (strong positive correlation: 0.71), sleep hours (0.12), social media hours (-0.17), Netflix hours (-0.17), mental health rating (0.32), exercise frequency (0.16), attendance percentage (0.09).
Categorical/Binary Variables: Gender, diet quality, parental education, part-time job, extracurricular participation, internet quality.
Target Variable: Exam score (continuous).

Preprocessing steps:
```
Minimal data cleaning due to high-quality synthetic dataset.
Binary variables encoded as 1 (Yes) or 0 (No).
Categorical variables one-hot encoded to avoid multicollinearity.
Continuous features retained unscaled, suitable for tree-based models and interpretable via Linear Regression coefficients.
```
Methodology:
```
1) Data Preprocessing

Handled missing values (none significant in dataset).
Applied one-hot encoding for categorical variables (e.g., gender, parental education).
Split dataset into 80% training (8,000 records) and 20% testing (2,000 records).
```
```
2) Exploratory Data Analysis

Correlation analysis to identify feature-target relationships.
Visualizations (histograms, scatter plots, correlation matrices) using pandas, seaborn, and matplotlib.
Key insights: Study time is the strongest predictor, followed by mental health; social media/Netflix usage negatively impacts scores.
```
```
3) Modeling
Four regression models were implemented using scikit-learn:
Linear Regression: Baseline for linear relationships, interpretable via coefficients.
Decision Tree Regressor: Captures non-linear patterns, prone to overfitting.
Random Forest Regressor: Ensemble of 100 trees, robust for tabular data.
Gradient Boosting Regressor: Sequential ensemble with learning rate 0.1, optimized for residual correction.
Hyperparameters were kept at scikit-learn defaults for baseline comparison, with potential for tuning in future iterations.
```
```
4) Evaluation Metrics
Mean Absolute Error (MAE): Mean absolute difference between predicted and actual scores.
Root Mean Squared Error (RMSE): Emphasizes larger errors.
R² Score: Proportion of variance explained by the model.
```
```
5) Experiments

Experiment 1: Simulated impact of increasing study hours on predicted exam scores.
Experiment 2: Analyzed optimal sleep range (7-8 hours) for performance.
```
```
6) Results:

Model Performance

Model
MAE
RMSE
R²

Linear Regression
4.183
5.144
0.896


Decision Tree
7.390
9.253
0.666


Random Forest
4.971
6.211
0.849


Gradient Boosting
4.627
5.531
0.880

```

Linear Regression outperformed others (R²: 0.896), indicating predominantly linear relationships in the data.
Gradient Boosting and Random Forest performed well but did not significantly surpass Linear Regression.
Decision Tree showed poor generalization (R²: 0.666) due to overfitting.

Feature Importance:
Linear Regression Coefficients:
Study time: Strongest positive impact.
Social media/Netflix hours: Negative impact (-2.0 and -2.3 points per hour).
Mental health rating, sleep hours: Smaller positive effects.


Random Forest & Gradient Boosting:
Study time and mental health as top predictors.
Age, gender, diet quality, parental education: Minimal impact (<1%).



Key Insights:
```
Study time is the dominant predictor of academic success.
Mental health and sleep (7-8 hours) positively influence performance.
Social media and Netflix usage negatively affect grades.
Background factors (e.g., gender, parental education) have negligible impact when habits are accounted for.
```
Dependencies
Install required libraries using:
```
pip install -r requirements.txt
```
requirements.txt:
```
pandas==2.0.3
numpy==1.24.3
scikit-learn==1.3.0
seaborn==0.12.2
matplotlib==3.7.2
jupyter==1.0.0
```

Installation:

Clone the repository:
```
git clone <repository-url>
```


Navigate to the project directory:
```
cd <project-directory>
```

Install dependencies:
```
pip install -r requirements.txt
```

Launch Jupyter notebook:
```
jupyter notebook Main.ipynb
```


Usage

Open Main.ipynb to explore the full pipeline: data loading, preprocessing, EDA, model training, evaluation, and experiments.
The notebook is modular, with sections for each analysis step, making it easy to modify or extend.


