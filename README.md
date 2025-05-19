# Customer Churn Prediction with Machine Learning

### `Data Analyst Intern Entrance Test`

---

> **Problem Type**: Supervised Binary Classification  
> **Goal**: Predict the `Churn` status of customers based on behavioral and usage features

---

## 1. Dataset

- **Source**: Provided by MCI, `churn-bigml-80.csv`
- **Rows**: 2,666 samples
- **Target**: `Churn` (bool)
- **Features**: 19 features including call durations, service plans, and support interactions

| Feature Name             | Description                                |
| ------------------------ | ------------------------------------------ |
| `International plan`     | Whether the user has an international plan |
| `Voice mail plan`        | Whether the user has a voicemail plan      |
| `Customer service calls` | Number of times customer called support    |
| ...                      | See code for full list                     |

---

## 2. Exploratory Data Analysis (EDA)

- Class imbalance (Churned: ~14%)
- Strong correlation between `Customer service calls` and churn
- Plan-based variables (`Intl plan`, `Voice mail plan`) affect churn

**Visualizations:**

- Correlation heatmap
- Churn distribution
- Boxplots of calls vs. churn

---

## 3. Methodology

- Preprocessing: encoding, dropping non-informative features
- Model: `RandomForestClassifier` with `class_weight='balanced'`
- Evaluation: Accuracy, Precision, Recall, F1, AUC-ROC
- Feature Importance plotted to interpret model

---

## 4. Results

```bash
Classification Report:
              precision    recall  f1-score   support

           0       0.92      1.00      0.95       455
           1       0.95      0.47      0.63        79

    accuracy                           0.92       534
   macro avg       0.93      0.73      0.79       534
weighted avg       0.92      0.92      0.91       534

ROC-AUC Score: 0.7320
```

> Feature importances highlight that `Customer service calls`, `Intl Plan`, and `Total day charge` are most predictive.

---

## 5. How to Run

1. Clone the repo

```bash
git clone https://github.com/jncmtam/Churn-Prediction.git
cd Churn-Predction
```

2. Create Python virtual environment

```bash
python -m venv venv
```

3. Activate venv

```bash
# for MacOS/ Linux
source venv/bin/activate
# for Window
venv/Script/activate
```

4. Install Dependencies

```bash
pip install -r requirements.txt
```

5. Run the notebook

```bash
jupiter notebook churn_analysis.ipynb
```

### 6. File structure

```bash
churn-prediction
├── data
│   ├── input
│   │   └── churn-bigml-80.csv
│   └── output
│       └── feature_importance.csv
│
├── docs
│   └── features_insights.md
│
├── models
│   ├── churn_model.pkl
│   └── scaler.pkl
│
├── venv
│
├── .gitignore
├── churn_analysis.ipynb
├── prediction_output.csv
├── README.md
└── requirements.txt
```

## Author : `Chu Minh Tam` - ML/NLP Researcher

## Contact :

- jn.cmtam@gmail.com
- tam.chu2213009cs@hcmut.edu.vn
- +84 327628468
