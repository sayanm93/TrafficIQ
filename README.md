```
# 🚦 TrafficIQ — Traffic Demand Prediction

> Predicting urban traffic demand using machine learning to help cities tackle congestion and improve mobility.

## 📌 Problem Statement

Given geographic, road, and weather data across various city locations, predict the **traffic demand** (a value between 0 and 1) at each location and timestamp.

- `0.0` → No traffic
- `1.0` → Maximum congestion

**Evaluation Metric:**
```
score = max(0, 100 * r2_score(actual, predicted))
```
## 📁 Project Structure
```
<img width="514" height="398" alt="image" src="https://github.com/user-attachments/assets/342720e8-30f9-4073-8d00-47764fd9995c" />
```

## 📊 Dataset

| File | Rows | Columns | Description |
|------|------|---------|-------------|
| `train.csv` | 77,299 | 11 | Training data with demand labels |
| `test.csv` | 41,778 | 10 | Test data — predict demand for these |
| `sample_submission.csv` | 5 | 2 | Shows required submission format |

### Column Description

| Column | Type | Description |
|--------|------|-------------|
| `Index` | int | Unique row identifier |
| `geohash` | string | Encoded geographic location |
| `day` | int | Day number of the record |
| `timestamp` | string | Time in hour:minute format (every 15 mins) |
| `RoadType` | string | Residential / Street / Highway |
| `NumberofLanes` | int | Number of lanes at the location |
| `LargeVehicles` | string | Allowed / Not Allowed |
| `Landmarks` | string | Yes / No |
| `Temperature` | float | Temperature at the location |
| `Weather` | string | Sunny / Rainy / Foggy / Snowy |
| `demand` | float | 🎯 Target variable (0 to 1) |

## ⚙️ Setup

### 1. Clone the repo
```
git clone https://github.com/sayanmitra/TrafficIQ.git
cd TrafficIQ
```

### 2. Install dependencies
```
pip install -r requirements.txt
```

### 3. Download the data
Get train.csv and test.csv from our shared Google Drive:
🔗 [Google Drive Link] — replace this with actual link
Place both files inside the data/ folder.

### 4. Start working
Open the baseline notebook:
```
jupyter notebook notebooks/baseline.ipynb
```

## 🚀 Workflow

```
Explore data → Clean & engineer features → Train model → Validate locally → Submit
```

1. **Explore** — understand the data, spot missing values
2. **Clean** — handle nulls in RoadType, Temperature, Weather
3. **Feature engineer** — extract hour/minute from timestamp, decode geohash
4. **Train** — try XGBoost, LightGBM, Random Forest
5. **Validate locally** — use 80/20 split, check R² score
6. **Submit only if local score improves** ⚠️


## 📋 Submission Rules

- ⚠️ Total submissions allowed: 50 (shared across all 4 members)
- Always validate locally before submitting
- Log every submission in the tracker below
- Submission format: CSV with columns Index and demand
- File size must be 41,778 × 2

## 👥 Team

| Member | GitHub | Focus Area |
|--------|--------|------------|
| Sayan | @sayanmitra | - |
| Ankit | @username | - |
| Devashish | @username | - |
| Adit | @username | - |


## 🏆 Best Score

Score   : —
Model   : —
By      : —
Date    : —


## 📦 Dependencies

See requirements.txt for full list. Key libraries:
- pandas, numpy — data handling
- scikit-learn — ML models & evaluation
- xgboost, lightgbm — gradient boosting models
- matplotlib, seaborn — visualization


*Competition hosted on Hackerearth | Team TrafficIQ*
```
