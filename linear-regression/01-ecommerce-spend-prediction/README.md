# 🛒 E-Commerce Customer Spend Prediction — Linear Regression

## 📌 Project Overview

This project builds a **Linear Regression model** to predict the **Yearly Amount Spent** by e-commerce customers based on their behaviour metrics such as time spent on the app/website, average session length, and membership duration.

The goal is to help the business answer: **Should we focus more on the Mobile App or the Website?**

---

## 📂 Dataset

- **Source:** [Kaggle — Focusing on Mobile App or Website](https://www.kaggle.com/datasets/kolawale/focusing-on-mobile-app-or-website)
- **File:** `Ecommerce Customers.csv`
- **Features used:**
  | Feature | Description |
  |---|---|
  | Avg. Session Length | Average length of in-store style advice sessions |
  | Time on App | Time spent on mobile app (minutes) |
  | Time on Website | Time spent on website (minutes) |
  | Length of Membership | Number of years as a member |
- **Target:** `Yearly Amount Spent` (USD)

---

## 🧪 Project Workflow

```
1. Data Loading & Exploration
2. Exploratory Data Analysis (EDA)
3. Correlation Analysis
4. Model Training (Linear Regression)
5. Predictions & Evaluation
6. Residual Analysis
```

---

## 📊 Exploratory Data Analysis

- **Joint plots** to visualize relationships between individual features and the target variable.
- **Pair plot** for a full pairwise scatter matrix.
- **Correlation heatmap** to identify the most influential features.
- **Linear model plot** between `Length of Membership` and `Yearly Amount Spent` — showing the strongest linear relationship.

---

## 🤖 Model

- **Algorithm:** `sklearn.linear_model.LinearRegression`
- **Train/Test Split:** 70% / 30% (`random_state=42`)
- **Features:** `Avg. Session Length`, `Time on App`, `Time on Website`, `Length of Membership`

---

## 📈 Results

| Metric | Value |
|---|---|
| MAE (Mean Absolute Error) | 8.43 |
| MSE (Mean Squared Error) | 103.92 |
| RMSE (Root Mean Squared Error) | 10.19 |

> The model predictions are off by ~$8.43 on average (MAE). RMSE of 10.19 > MAE indicates a few larger errors exist, but overall the model performs well.

### Key Finding from Coefficients

`Length of Membership` has the **highest coefficient**, meaning it is the most important predictor of yearly spending. `Time on App` also shows strong influence, suggesting the business should **prioritize improving the mobile app experience**.

---

## ✅ Residual Diagnostics

- **Distribution plot** of residuals — approximately normal, validating model assumptions.
- **Q-Q Plot** — points follow the straight line closely, confirming normality of residuals.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.x | Core language |
| Pandas | Data manipulation |
| Matplotlib / Seaborn | Visualization |
| Scikit-learn | Model building & evaluation |
| SciPy / Pylab | Residual normality checks |

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/ecommerce-linear-regression.git
   cd ecommerce-linear-regression
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/kolawale/focusing-on-mobile-app-or-website) and place it in a `/data` folder.

4. Update the dataset path in the notebook:
   ```python
   df = pd.read_csv('data/Ecommerce Customers')
   ```

5. Open and run the notebook:
   ```bash
   jupyter notebook linear-regression-e-commerce.ipynb
   ```

---

## 📁 Repository Structure

```
ecommerce-linear-regression/
│
├── linear-regression-e-commerce.ipynb   # Main notebook
├── requirements.txt                      # Dependencies
├── README.md                             # Project documentation
└── data/
    └── Ecommerce Customers.csv           # Dataset (download from Kaggle)
```

---

## 🔗 References

- Dataset: [Kaggle — Focusing on Mobile App or Website](https://www.kaggle.com/datasets/kolawale/focusing-on-mobile-app-or-website)
- Scikit-learn Documentation: https://scikit-learn.org/

---

## 👤 Author

**Hardik Singh Gusain**
- GitHub: [@hsgusain](https://github.com/hsgusain)
- Kaggle: [@haruhero](https://www.kaggle.com/haruhero)
- Email: hardik.gusain25b@gmail.com
