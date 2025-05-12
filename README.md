# Hepatic Patient Analysis

This project focuses on analyzing clinical data to predict whether a patient has a liver disease using supervised classification algorithms such as Logistic Regression, KNN, and Decision Trees.

---

##  Objective

The main goal is to build classification models capable of correctly identifying patients with and without liver disease. Due to the class imbalance in the original dataset, specific preprocessing techniques were applied to improve training quality and model performance.

---

## Preprocessing Steps

1. **Exploratory Data Analysis (EDA):**
   - Distribution visualizations and outlier detection.
   - Correlation analysis.

2. **Missing Data Handling:**
   - Imputation of missing values.

3. **Class Imbalance Handling:**
   - **SMOTE** was used to balance the number of healthy and diseased patients.
   - It was applied **only to the training set** to avoid data leakage.

4. **Feature Scaling:**
   - Min-Max Scaling was applied after the train-test split.

---

## Models Evaluated

The following models were trained and optimized using **GridSearchCV** with **Stratified Cross-Validation**:

- **Logistic Regression**
- **K-Nearest Neighbors (KNN)**
- **Decision Tree**

Best hyperparameters were selected based on the **F1 Score**, which is a better performance metric in imbalanced classification problems.

---

## Results

| Model                     | F1 Score |
|---------------------------|----------|
| Logistic Regression (C=31)| 0.681081 |
| KNN (k=7)                 | 0.724490 |
| Decision Tree (depth=9)   | 0.746269 |

---

## Conclusions


Based on the F1 Score results, the Decision Tree model (depth=9) achieved the best performance with a score of 0.746, followed by KNN (k=7) with 0.724, and Logistic Regression (C=31) with 0.681. This suggests that the Decision Tree was better at capturing the non-linear patterns in the dataset. In contrast, Logistic Regression may have struggled due to its linear nature. Overall, tree-based models appear more effective for this classification task. Preprocessing (SMOTE, scaling, cross-validation) played a crucial role in improving the model's generalization, although it would be worth exploring other algorithms for further improvement, such as Random Forest or XGBoost.

---
## Tools and Libraries

- Python 3.11
- NumPy
- Pandas
- scikit-learn
- imbalanced-learn (SMOTE)
- Matplotlib
- Seaborn

--- 

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/Marzerp/Hepatic_Patient_Analisis.git
cd Hepatic_Patient_Analisis

pip install -r requirements.txt

jupyter notebook LiverPatientsAnalisis.ipynb


