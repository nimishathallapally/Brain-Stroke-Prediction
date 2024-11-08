# Brain Stroke Prediction

This project predicts the likelihood of stroke in individuals using various health and demographic features. The goal is to build an accurate, interpretable machine learning model that helps identify high-risk individuals, enabling preventive healthcare measures.

## Problem Definition
Our objective is to create a predictive model that assesses the risk of stroke based on specific attributes. This tool could be useful for:
- **Healthcare providers**: To identify and monitor high-risk patients proactively.
- **Insurance companies**: To assess risk profiles in patient populations.

### Target Variable
- **`stroke`**: A binary indicator, where `1` means the individual experienced a stroke, and `0` means no stroke.

### Features Used
The dataset includes a variety of features grouped as follows:
1. **Demographic Features**: `gender`, `age`, `Residence_type`
2. **Medical History**: `hypertension`, `heart_disease`
3. **Lifestyle Factors**: `ever_married`, `work_type`, `smoking_status`
4. **Health Metrics**: `avg_glucose_level`, `bmi`

## Data Visualization
To understand the distribution of data and relationships between features, we used several visualization techniques:
- **Histograms**: For analyzing the distribution of key numerical features like `age`, `avg_glucose_level`, and `bmi`.
- **Correlation Heatmap**: To assess correlations between features, helping identify the most influential variables for stroke prediction.
- **Box Plots**: Used to identify potential outliers in health metrics.
- **Count Plots**: To observe the distribution of categorical variables like `smoking_status` and `work_type`.

## Data Preprocessing
- **One-Hot Encoding**: Applied to categorical variables to prepare them for the model.
- **Handling Imbalanced Data with SMOTE**: Since stroke cases are less frequent, SMOTE (Synthetic Minority Over-sampling Technique) was used to balance the dataset by generating synthetic samples for the minority class.
- **Scaling Decision**: Standardization or normalization was not applied to `age`, `avg_glucose_level`, and `bmi` to retain interpretability and align with medical standards.

## Model Selection
After evaluating several approaches, **Random Forest** was chosen for its robust performance and interpretability in predicting stroke risk. Random Forest handles imbalanced data well, especially when combined with SMOTE, and is effective without requiring scaling.

### Model Evaluation
The model was evaluated using:
- **Accuracy**: Proportion of correct predictions.
- **Precision, Recall, and F1-Score**: These metrics help address class imbalance, with a focus on high recall to minimize false negatives.
- **Confusion Matrix**: To observe true positives, false positives, true negatives, and false negatives.


### Model Evaluation
The model was evaluated using:
- **Accuracy**:  0.9209340434248259 (or 92.09%)
- **Classification Report**:
```
              precision    recall  f1-score   support

         0.0       0.95      0.89      0.92      1224
         1.0       0.90      0.95      0.92      1217

    accuracy                           0.92      2441
   macro avg       0.92      0.92      0.92      2441
weighted avg       0.92      0.92      0.92      2441


```

## How to Run the Project
1. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
2. **Run the Notebook**: Open `Brain_Stroke_Prediction.ipynb` in Jupyter Notebook and follow the steps for data loading, visualization, preprocessing, model training, and evaluation.

## Results
The final model showed robust performance, making it effective for real-world applications in predicting stroke risk.
