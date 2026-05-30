# 🚗 Car Price Prediction — Linear Regression & Lasso

A machine learning project that predicts the **selling price of used cars** based on features like year, present price, kilometers driven, fuel type, and more — using **Linear Regression** and **Lasso Regression** models.

> 📦 Dataset: [Vehicle Dataset from CarDekho — Kaggle](https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho?select=CAR+DETAILS+FROM+CAR+DEKHO.csv)

---

## 📁 Dataset

**File:** `car data.csv`

| Column | Description |
|---|---|
| `Car_Name` | Name of the car |
| `Year` | Year of manufacture |
| `Selling_Price` | Target — price the car was sold for (in Lakhs) |
| `Present_Price` | Current ex-showroom price |
| `Kms_Driven` | Total kilometers driven |
| `Fuel_Type` | Fuel type (Petrol / Diesel / CNG) |
| `Seller_Type` | Dealer or Individual |
| `Transmission` | Manual or Automatic |
| `Owner` | Number of previous owners |

---

## 🔧 Data Preprocessing

Categorical columns are **label-encoded** to numeric values:

| Column | Encoding |
|---|---|
| `Fuel_Type` | Diesel → 1, Petrol → 2, CNG → 3 |
| `Transmission` | Manual → 1, Automatic → 2 |
| `Seller_Type` | Dealer → 1, Individual → 2 |

---

## 📊 Exploratory Data Analysis (EDA)

- **Distribution plots** — Histogram for each feature using Seaborn
- **Correlation Heatmap** — Visualizes relationships between all numerical features

---

## 🤖 Models

### 1. Linear Regression
Standard ordinary least squares regression trained on 90% of the data.

### 2. Lasso Regression
L1-regularized regression that penalizes less important features, effectively performing feature selection.

---

## 🔁 Training & Evaluation

Data is split **90% training / 10% testing** (`random_state=42`).

Each model is evaluated using:

| Metric | Description |
|---|---|
| **R² Score** | How well the model explains variance in the data |
| **MAE** | Mean Absolute Error (average prediction error in Lakhs) |

Results are printed for both **training** and **test** sets, with scatter plots comparing actual vs. predicted prices.

---

## 🚀 How to Run

### 1. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 2. Run the Notebook

```bash
jupyter notebook n1.ipynb
```

### 3. Predict a Custom Car Price

At the end of the notebook, enter your car details interactively:

```
Year: 2015
Present_Price: 7.5
Kms_Driven: 45000
Fuel_Type: 2        # 1=Diesel, 2=Petrol, 3=CNG
Seller_Type: 1      # 1=Dealer, 2=Individual
Transmission: 1     # 1=Manual, 2=Automatic
Owner: 0
```

The predicted selling price is calculated using the trained Lasso model weights and bias:

```
yprediction = sum(input × weights) + bias
```

---

## 🏗️ Project Structure

```
├── n1.ipynb        # Main notebook
├── car data.csv    # Dataset
└── README.md       # Project documentation
```

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4c72b0)

- **NumPy** — Numerical operations & manual prediction
- **Pandas** — Data loading and preprocessing
- **Matplotlib / Seaborn** — EDA visualizations
- **scikit-learn** — Train/test split, Linear Regression, Lasso, and metrics
