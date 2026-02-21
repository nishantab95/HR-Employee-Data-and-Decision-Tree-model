# Employee Attrition Prediction (Decision Tree + SMOTE)

This project focuses on predicting employee attrition (whether an employee is likely to leave the organization) using machine learning. The objective is to build a classification model that can assist HR teams in identifying at-risk employees and taking proactive retention measures.

---

## 📌 Problem Statement

Employee attrition is a major concern for organizations as it leads to increased recruitment costs, loss of experienced talent, and reduced team productivity. This project aims to predict attrition using historical employee data and machine learning techniques.

---

## 📊 Dataset

The dataset contains employee-related features such as:

- Demographics (Age, Gender, etc.)
- Job-related attributes (JobRole, Department, etc.)
- Work conditions (OverTime, JobSatisfaction, etc.)
- Target variable: **Attrition (Yes/No)**

The target variable is imbalanced, with fewer employees leaving compared to those who stay.

---

## ⚙️ Approach

1. **Data Preprocessing**
   - Handled categorical variables using encoding techniques  
   - Checked and handled missing values  
   - Performed exploratory data analysis (EDA)  

2. **Exploratory Data Analysis (EDA)**
   - Generated an automated profiling report using **ydata-profiling**
   - The HTML report provides insights into:
     - Feature distributions  
     - Missing values  
     - Correlations  
     - Class imbalance  

3. **Train–Test Split**
   - Used stratified train-test split to preserve class distribution  

4. **Handling Class Imbalance**
   - Applied **SMOTE (Synthetic Minority Oversampling Technique)** only on the training data to balance the minority class  

5. **Model Building**
   - Trained a **Decision Tree Classifier**  
   - Tuned basic hyperparameters such as max depth and splitting criteria  

6. **Model Evaluation**
   - Evaluated using:
     - Accuracy  
     - Precision  
     - Recall  
     - F1-score  
     - Classification Report  

---

## 📈 Results

The trained model achieved the following performance on the test set:

| Metric                         | Value |
|--------------------------------|-------|
| Accuracy                       | ~76%  |
| F1-score (Attrition = Yes)     | ~0.39 |
| Recall (Attrition = Yes)       | ~49%  |
| Precision (Attrition = Yes)    | ~33%  |

**Interpretation:**
- The model shows moderate ability to identify employees who are likely to leave.  
- Recall for the attrition class improved after applying SMOTE, but precision remains relatively low, indicating a higher number of false positives.  
- Overall accuracy is reasonable for a baseline model, but not sufficient for real-world deployment without further improvement.

---

## 🧠 Key Learnings

- Accuracy alone is not a reliable metric for imbalanced classification problems.  
- SMOTE helps improve minority class recall but can introduce noise.  
- Decision Trees are simple and interpretable but may struggle with generalization.  
- Proper handling of data leakage (applying SMOTE only on training data) is crucial for realistic model evaluation.  

---

## 🚀 Future Improvements

This project will be extended with:

- Ensemble models such as **Random Forest** and **XGBoost**  
- Hyperparameter tuning using **GridSearchCV**  
- Feature importance analysis  
- ROC-AUC evaluation  
- Model deployment as a simple web API (**FastAPI / Streamlit**)  
- Better feature engineering and selection  

---

## 📂 EDA Report (ydata-profiling)

An automated EDA report was generated using **ydata-profiling** and saved as an HTML file.

📄 File:  
```text
reports/employee_attrition_profile.html
