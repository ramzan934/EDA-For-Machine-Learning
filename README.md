# ❤️ Heart Disease EDA — Exploratory Data Analysis with Python

A complete exploratory data analysis (EDA) project on the **Heart Disease dataset**, covering data loading, cleaning, univariate/bivariate analysis, correlation analysis, encoding, and feature scaling — built as a foundational step before applying machine learning models for heart disease prediction.

---

## 📌 Project Overview

This project performs a full EDA pipeline on the Heart Disease dataset to understand patterns, relationships, and data quality issues before model building. It's part of a broader machine learning self-study roadmap focused on building strong, demonstrable data analysis fundamentals.

**Goals:**
- Understand the structure and quality of the dataset
- Identify and handle missing values, duplicates, and outliers
- Explore relationships between features and the target variable (presence of heart disease)
- Prepare a clean, scaled dataset ready for machine learning models

---

## 📂 Dataset

- **Source:** [UCI Heart Disease Dataset](https://archive.ics.uci.edu/dataset/45/heart+disease) / [Kaggle version](https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset)
- **Rows:** ~300–1000+ (depending on version used)
- **Target variable:** `target` (0 = No Heart Disease, 1 = Heart Disease)

**Features include:**

| Column     | Description                                      |
|------------|---------------------------------------------------|
| `age`      | Age of the patient                                |
| `sex`      | Sex (1 = male, 0 = female)                        |
| `cp`       | Chest pain type (0–3)                             |
| `trestbps` | Resting blood pressure (mm Hg)                    |
| `chol`     | Serum cholesterol (mg/dl)                         |
| `fbs`      | Fasting blood sugar > 120 mg/dl (1 = true)        |
| `restecg`  | Resting electrocardiographic results              |
| `thalach`  | Maximum heart rate achieved                       |
| `exang`    | Exercise induced angina (1 = yes)                 |
| `oldpeak`  | ST depression induced by exercise                 |
| `slope`    | Slope of the peak exercise ST segment             |
| `ca`       | Number of major vessels colored by fluoroscopy    |
| `thal`     | Thalassemia (0 = normal, 1 = fixed defect, etc.)  |
| `target`   | Heart disease presence (0 = no, 1 = yes)           |

> ⚠️ Column names can vary slightly depending on the dataset source — check `df.columns.tolist()` after loading.

---

## 🛠️ Tech Stack

- **Python 3**
- **Pandas** — data manipulation
- **NumPy** — numerical operations
- **Matplotlib / Seaborn** — data visualization
- **SciPy** — statistical operations
- **Scikit-learn** — encoding & feature scaling

---

## 📁 Project Structure

```
heart-disease-eda/
│
├── heart.csv                              # Raw dataset (not included — download separately)
├── heart_disease_eda.py                   # Main EDA script
├── heart_disease_cleaned.csv              # Cleaned dataset (output)
├── heart_disease_cleaned_scaled.csv       # Cleaned + scaled dataset (output)
│
├── plots/
│   ├── missing_values_heatmap.png
│   ├── target_distribution.png
│   ├── histograms_numeric_features.png
│   ├── boxplots_numeric_features.png
│   ├── bivariate_boxplots_vs_target.png
│   ├── categorical_vs_target.png
│   ├── pairplot_key_features.png
│   └── correlation_heatmap.png
│
└── README.md
```

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/heart-disease-eda.git
   cd heart-disease-eda
   ```

2. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn scipy scikit-learn
   ```

3. **Add the dataset**
   Download `heart.csv` from [Kaggle](https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset) and place it in the project root.

4. **Run the EDA script**
   ```bash
   python heart_disease_eda.py
   ```

   This will print summary statistics to the console and save all plots + cleaned CSVs to the working directory.

---

## 🔍 EDA Workflow

### 1. Data Loading & Inspection
- Load dataset with `pandas.read_csv()`
- Check shape, data types, column names, and summary statistics (`.info()`, `.describe()`)

### 2. Data Cleaning
- Detect and impute missing values (median for numeric, mode for categorical)
- Remove duplicate rows
- Standardize column names
- Detect outliers using the **IQR method** and cap extreme values

### 3. Univariate Analysis
- Target variable distribution (class balance)
- Histograms for all numeric features
- Boxplots to visualize spread and outliers

### 4. Bivariate & Multivariate Analysis
- Feature-vs-target boxplots (e.g. cholesterol vs disease presence)
- Categorical feature counts split by target (e.g. chest pain type vs disease)
- Pairplot of key clinical features colored by target

### 5. Correlation Analysis
- Full correlation heatmap across numeric features
- Ranked correlation of each feature with the target variable

### 6. Encoding & Scaling
- Label encoding for any text-based categorical columns
- `StandardScaler` for standardization (mean = 0, std = 1)
- `MinMaxScaler` as an alternative normalization approach

---

## 📊 Key Insights (fill in after running on your data)

- Class balance between disease/no-disease patients: _e.g. 54% / 46%_
- Features most correlated with heart disease: _e.g. `cp`, `thalach`, `oldpeak`, `exang`_
- Notable outliers: _e.g. cholesterol and resting blood pressure have some extreme values_
- Any missing/duplicate data found and how it was handled

---

## 📌 Next Steps

- [ ] Feature selection based on correlation and importance scores
- [ ] Train baseline models (Logistic Regression, Random Forest, XGBoost)
- [ ] Model evaluation (accuracy, precision, recall, ROC-AUC)
- [ ] Hyperparameter tuning
- [ ] Model deployment / API for predictions

---

## 🙋 Author

**Ramzan**
AI/ML enthusiast | Building a portfolio of ML projects as part of a structured self-study roadmap
Connect on [LinkedIn](#) | [GitHub](#)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
