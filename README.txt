#  EV Service Delay Prediction API

![Python](https://img.shields.io/badge/Python-3.9-blue)
![ML](https://img.shields.io/badge/Machine%20Learning-Random%20Forest-green)
![API](https://img.shields.io/badge/API-Flask-red)
![Deployment](https://img.shields.io/badge/Deployment-Render-purple)

Predict **service delay risk** and **customer wait time** for EV service centers using machine learning.  
Built as an end-to-end ML system and deployed via a Flask REST API.

---

##  Overview

Efficient scheduling is critical in EV service operations. This project predicts:

-  **Delay Risk** (classification)  
-  **Expected Wait Time** (regression)  

Using operational and service data, this system helps simulate real-world service center decision-making.

---

##  Dataset

- Source: Synthetic / structured EV service dataset  
- Includes operational and scheduling variables  

**Targets:**
- `delay_risk` → classification  
- `wait_time` → regression  

---

## ⚙️ Features

| Feature | Description |
|--------|------------|
| month | Month of service |
| day_of_week | Day of appointment |
| is_weekend | Weekend indicator |
| service_type | Encoded service category |
| avg_service_time | Average service duration |
| appointments_per_day | Daily workload |
| service_slots | Available capacity |
| num_technicians | Workforce size |
| backlog_size | Pending jobs |
| demand_capacity_ratio | System load indicator |

---

##  Models

###  Classification (Delay Risk)
- Random Forest Classifier (primary)
- Logistic Regression (baseline)

**Metrics:**
- Accuracy
- Precision / Recall
- F1 Score

---

###  Regression (Wait Time)
- Random Forest Regressor (primary)
- Linear Regression (baseline)

**Metrics:**
- Mean Absolute Error (MAE)
- R² Score

---

##  Results

-  Classification Accuracy: **~XX%**  
-  Regression Performance (R²): **~XX**  

### Key Insights:
- Demand-capacity ratio strongly influences delay probability  
- Backlog size is a major driver of wait time  
- Feature importance and partial dependence plots improve interpretability  

---

##  API Usage

### Endpoint
