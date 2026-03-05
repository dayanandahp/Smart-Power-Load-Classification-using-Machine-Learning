# Smart Power Load Classification using Machine Learning

## Project Overview

This project builds a **machine learning model** that classifies the load type of an industrial power system using historical energy consumption data.

The model automatically categorizes system load into:

- **Light Load**
- **Medium Load**
- **Maximum Load**

by learning patterns from past energy usage.

The project demonstrates a complete **machine learning pipeline** including:

- Data preprocessing
- Exploratory Data Analysis (EDA)
- Feature engineering
- Model training
- Model evaluation

---

# Problem Statement

Industrial power systems experience different load levels depending on operational hours, equipment usage, and environmental conditions.

Identifying load types manually can be inefficient and time-consuming.

This project develops a **machine learning model that automatically predicts the load type** using historical energy consumption data.

---

# Project Objective

The main objective of this project is to build a machine learning model capable of predicting the **Load_Type** of a power system using historical data.

The system classifies the load into three categories:

- **Light_Load**
- **Medium_Load**
- **Maximum_Load**

The model is evaluated using the **most recent time period** to ensure it performs well on unseen data.

---

# Key Features

- Data preprocessing and cleaning
- Handling missing values using **median imputation**
- Feature engineering from time-based data
- Time-based dataset splitting to **avoid data leakage**
- Training a **Random Forest Classifier**
- Model evaluation using classification metrics
- Visualization using **confusion matrix**
- Feature importance analysis
- Saving trained models using **Joblib**

---

# Technologies Used

| Technology | Purpose |
|------------|--------|
| **Python** | Programming language |
| **Pandas** | Data processing and analysis |
| **NumPy** | Numerical computations |
| **Scikit-learn** | Machine learning algorithms |
| **Matplotlib** | Data visualization |
| **Seaborn** | Statistical visualization |
| **Joblib** | Model saving/loading |
| **Jupyter Notebook** | Development and experimentation |

---

# Project Workflow

## 1. Data Collection

Load the industrial energy consumption dataset.

---

## 2. Exploratory Data Analysis (EDA)

Analyze the dataset to understand:

- Feature distributions
- Relationships between variables
- Data quality issues
- Class distribution of load types

---

## 3. Data Preprocessing

- Convert **Date_Time** column to datetime format
- Handle missing values using **median imputation**
- Clean column names
- Remove duplicate records

---

## 4. Feature Engineering

Extract time-based features from the timestamp:

- **Year**
- **Month**
- **Day**
- **Weekday**
- **Hour (derived from NSM)**
- **Weekend indicator**

---

## 5. Label Encoding

Convert the categorical target variable **Load_Type** into numerical labels using **LabelEncoder**.

---

## 6. Dataset Splitting

To avoid **time leakage**:

- **Last month of data → Test set**
- **All previous data → Training set**

This simulates **real-world future predictions**.

---

## 7. Model Selection

A **Random Forest Classifier** is used because it performs well on **structured tabular datasets** and handles **non-linear relationships effectively**.

---

## 8. Model Training

Train the Random Forest model using the training dataset.

---

## 9. Model Evaluation

Evaluate the model using:

- **Accuracy**
- **Precision**
- **Recall**
- **F1-Score**
- **Confusion Matrix**

---

## 10. Model Saving

The trained model and label encoder are saved using **Joblib**:

```python
joblib.dump(rf, "rf_load_model.joblib")
joblib.dump(le, "label_encoder.joblib")

**Dataset Information**

The dataset contains historical energy usage measurements from an industrial power system
| Feature                                  | Description                                   |
| ---------------------------------------- | --------------------------------------------- |
| **Date_Time**                            | Timestamp of energy measurement               |
| **Usage_kWh**                            | Energy consumption in kilowatt-hours          |
| **Lagging_Current_Reactive.Power_kVarh** | Lagging reactive power                        |
| **Leading_Current_Reactive_Power_kVarh** | Leading reactive power                        |
| **CO2**                                  | CO2 emission measurement                      |
| **NSM**                                  | Number of seconds from midnight               |
| **Load_Type**                            | Target variable (Light, Medium, Maximum Load) |

Model Used
Random Forest Classifier

Random Forest was selected because it:

Works well on tabular structured datasets

Captures non-linear relationships

Is robust to outliers and noisy data

Provides feature importance insights

Reduces overfitting through ensemble learning

The model was trained using 200 decision trees.

**Model Performance**

The model achieved the following performance on the test dataset:
| Metric                | Score    |
| --------------------- | -------- |
| **Accuracy**          | **89%**  |
| **Macro F1-score**    | **0.86** |
| **Weighted F1-score** | **0.89** |

**Classification Report
**
| Class            | Precision | Recall | F1-Score |
| ---------------- | --------- | ------ | -------- |
| **Light_Load**   | 0.99      | 0.90   | 0.94     |
| **Maximum_Load** | 0.84      | 0.78   | 0.81     |
| **Medium_Load**  | 0.74      | 0.95   | 0.83     |

**How the Project Solves the Problem
**
This system learns patterns from historical energy consumption data and automatically classifies power system load levels.

This can assist with:

Power system monitoring

Energy management

Demand forecasting

Industrial power optimization



**Installation**

Clone the repository:

git clone https://github.com/dayanandahp/Smart-Power-Load-Classification-using-Machine-Learning.git
cd Smart-Power-Load-Classification-using-Machine-Learning

Install dependencies:

pip install -r requirements.txt
How to Run the Project

Run the Jupyter Notebook:

jupyter notebook

Open the notebook and run the cells sequentially.

**Project Structure**
power-load-classification/
│
├── data/
│   └── load_data.csv
│
├── notebooks/
│   └── load_classification.ipynb
│
├── models/
│   ├── rf_load_model.joblib
│   └── label_encoder.joblib
│
├── requirements.txt
├── README.md

**Author**

Dayananda H P

Computer Science Engineering Student
SDMIT Ujire

GitHub

https://github.com/dayanandahp/Smart-Power-Load-Classification-using-Machine-Learning

LinkedIn

https://www.linkedin.com/in/dayananda-h-p-/