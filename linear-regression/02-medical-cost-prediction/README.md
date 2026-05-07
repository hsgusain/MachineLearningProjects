# 🏥 Medical Cost Prediction — Linear Regression

## 📌 Project Overview

This project performs a detailed **Exploratory Data Analysis (EDA)** and builds a **Linear Regression model** to predict **individual medical treatment costs** based on patient attributes such as age, BMI, smoking status, and more.

The analysis goes beyond just modelling — it tells a story about **how lifestyle factors, especially smoking, drive up healthcare costs.**

---

## 📂 Dataset

- **Source:** [Kaggle — Medical Cost Personal Dataset](https://www.kaggle.com/datasets/mirichoi0218/insurance)
- **File:** `insurance.csv`
- **Size:** 1,338 records

| Feature | Type | Description |
|---|---|---|
| age | Numerical | Age of the patient |
| sex | Categorical | Gender (male/female) |
| bmi | Numerical | Body Mass Index |
| children | Numerical | Number of dependents |
| smoker | Categorical | Smoking status (yes/no) |
| region | Categorical | Residential region in the US |
| **charges** | **Target** | **Individual medical costs (USD)** |

---

## 🧪 Project Workflow

```
1. Data Loading & Exploration
2. Label Encoding of Categorical Features
3. Correlation Analysis
4. Detailed EDA (Charges, Smoking, Age, BMI, Children)
5. Model Training (Linear Regression)
6. Predictions & Evaluation (MAE, MSE, RMSE, R²)
7. Residual Analysis
```

---

## 📊 Exploratory Data Analysis

### 🔥 Correlation Analysis
- **Smoking status** has by far the strongest correlation with medical charges
- BMI showed a lower correlation than expected on its own — but its effect amplifies significantly when combined with smoking

### 💰 Charges Distribution
- Right-skewed distribution — most patients have moderate costs, with a long tail of high spenders
- Smokers' charges are spread across a much higher range; non-smokers cluster at the lower end

### 🚬 Smoking Analysis
- Smokers pay **significantly more** than non-smokers across all ages and both genders
- Male smokers slightly outnumber female smokers in the dataset
- Even **18-year-old smokers** already pay substantially more than their non-smoking peers — an early signal of smoking's financial impact on healthcare

### 👴 Age Analysis
- Patient ages range from **18 to 64**
- For **non-smokers**, charges increase steadily with age — a logical, expected trend
- For **smokers**, the age-charge relationship is less defined — attributed to dataset size and the overwhelming dominance of smoking as a cost driver

### ⚖️ BMI Analysis
- Average BMI is **~30** — right at the clinical obesity threshold
- Patients with BMI ≥ 30 have higher and more spread-out charges
- The **worst-case combination** is being a smoker with a high BMI — highest charges observed in this group

### 👶 Children Analysis
- Most patients have 0 children; maximum is 5
- A notable portion of smokers are also parents

---

## 🤖 Model

- **Algorithm:** `sklearn.linear_model.LinearRegression`
- **Preprocessing:** Label Encoding on `sex`, `smoker`, `region`
- **Train/Test Split:** 80% / 20% (`random_state=42`)
- **Features used:** All 6 — `age`, `sex`, `bmi`, `children`, `smoker`, `region`

---

## 📈 Results

| Metric | Value |
|---|---|
| MAE (Mean Absolute Error) | 4,186.51 |
| MSE (Mean Squared Error) | 33,635,210.43 |
| RMSE (Root Mean Squared Error) | 5,799.59 |
| R² Score | 0.7833 |

> The model explains **~78.3% of the variance** in medical charges. The high RMSE relative to MAE suggests some patients have charges that are harder to predict — likely edge cases involving serious illness or accidents.

---

## ✅ Residual Diagnostics

- **Distribution plot** of residuals — approximately normal, validating linear regression assumptions
- **Q-Q Plot** — points largely follow the straight line, confirming normality of residuals with some deviation at the tails

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.x | Core language |
| Pandas | Data manipulation |
| Matplotlib / Seaborn | Visualization |
| Scikit-learn | Preprocessing, model building & evaluation |
| SciPy / Pylab | Residual normality checks |

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/hsgusain/ml-projects.git
   cd ml-projects/linear-regression/02-medical-cost-prediction
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/mirichoi0218/insurance) and place it in a `/data` folder.

4. Update the dataset path in the notebook:
   ```python
   df = pd.read_csv('data/insurance.csv')
   ```

5. Open and run the notebook:
   ```bash
   jupyter notebook medical-cost-personal-datasets.ipynb
   ```

---

## 📁 Repository Structure

```
02-medical-cost-prediction/
│
├── medical-cost-personal-datasets.ipynb   # Main notebook
├── requirements.txt                        # Dependencies
├── README.md                               # Project documentation
└── data/
    └── insurance.csv                       # Dataset (download from Kaggle)
```

---

## 🔗 References

- Dataset: [Kaggle — Medical Cost Personal Dataset](https://www.kaggle.com/datasets/mirichoi0218/insurance)
- Scikit-learn Documentation: https://scikit-learn.org/

---

## 👤 Author

**Hardik Singh Gusain**
- GitHub: [@hsgusain](https://github.com/hsgusain)
- Kaggle: [@haruhero](https://www.kaggle.com/haruhero)
- Email: hardik.gusain25b@gmail.com
