# EV Service Delay Prediction API

Predict service delay risk and wait time for electric vehicle (EV) service centers using machine learning models. Deployed as a Flask-based REST API for real-time inference.

---

## Table of Contents
- [Overview](#overview)  
- [Dataset](#dataset)  
- [Features](#features)  
- [Models](#models)  
- [Results](#results)  
- [API Usage](#api-usage)  
- [Setup & Run](#setup--run)  
- [Future Improvements - TBD](#future-improvements) 

---

## Overview
Efficient service scheduling is critical for EV centers. This project predicts:

1. **Delay risk** – whether a service appointment is likely to be delayed (classification)  
2. **Expected wait time** – estimated time customers will wait (regression)  

It uses historical service data, operational metrics, and customer appointments to improve planning and customer satisfaction.

---

## Dataset
- Source: Proprietary/synthetic EV service dataset  
- Features include: service type, appointments per day, number of technicians, backlog size, and demand-capacity ratio  
- Targets:  
  - `delay_risk` (classification)  
  - `wait_time` (regression)  

---

## Features
- `month` – month of service  
- `day_of_week` – day of the week of appointment  
- `is_weekend` – weekend indicator  
- `service_type` – encoded type of service  
- `avg_service_time` – average duration for this service type  
- `appointments_per_day` – total scheduled appointments  
- `service_slots` – available service slots  
- `num_technicians` – number of technicians available  
- `backlog_size` – number of pending appointments  
- `demand_capacity_ratio` – workload ratio of scheduled services vs available capacity  

---

## Models
### Classification: Delay Risk
- **Random Forest Classifier** (primary)  
- **Logistic Regression** (baseline)  
- Metrics: Accuracy, Precision, Recall, F1-score  
- Feature importance & partial dependence plots used for interpretability  

### Regression: Wait Time
- **Random Forest Regressor** (primary)  
- **Linear Regression** (baseline)  
- Metrics: Mean Absolute Error (MAE), R² score  
- Feature importance & partial dependence plots analyzed  

---

## Results
- **Classification Accuracy (Random Forest):** ~XX%  
- **Regression R² (Random Forest):** ~XX  
- Visualizations include confusion matrix, feature importance, and partial dependence plots for key variables like backlog size and demand-capacity ratio  

---

## API Usage
The project is deployed as a **Flask API**. Example endpoint:

```bash
POST /predict
Content-Type: application/json

{
    "month": 4,
    "day_of_week": 2,
    "is_weekend": 0,
    "service_type": 1,
    "avg_service_time": 45,
    "appointments_per_day": 10,
    "service_slots": 12,
    "num_technicians": 5,
    "backlog_size": 3,
    "demand_capacity_ratio": 0.83
}
```
---

## Setup & Run
```bash
git clone https://github.com/yourusername/ev-service-delay-prediction.git
cd ev-service-delay-prediction

pip install -r requirements.txt

python app.py

```
