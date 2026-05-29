🚦 TrafficIQ — Traffic Demand Prediction

Predicting urban traffic demand using machine learning to help cities tackle congestion and improve mobility.


📌 Problem Statement
Given geographic, road, and weather data across various city locations, predict the traffic demand (a value between 0 and 1) at each location and timestamp.

0.0 → No traffic
1.0 → Maximum congestion

Evaluation Metric:
score = max(0, 100 * r2_score(actual, predicted))

📁 Project Structure
TrafficIQ/
│
├── data/
│   └── sample_submission.csv     # Submission format reference
│   # ⚠️ train.csv & test.csv are NOT in GitHub (too large)
│   # Download from Google Drive link below
│
├── notebooks/
│   └── baseline.ipynb            # Starter notebook (start here!)
│
├── submissions/
│   └── (your submission csv files go here)
│
├── outputs/
│   └── (saved model files go here)
│
├── .gitignore
├── requirements.txt
└── README.md

📊 Dataset
FileRowsColumnsDescriptiontrain.csv77,29911Training data with demand labelstest.csv41,77810Test data — predict demand for thesesample_submission.csv52Shows required submission format
Column Description
ColumnTypeDescriptionIndexintUnique row identifiergeohashstringEncoded geographic locationdayintDay number of the recordtimestampstringTime in hour:minute format (every 15 mins)RoadTypestringResidential / Street / HighwayNumberofLanesintNumber of lanes at the locationLargeVehiclesstringAllowed / Not AllowedLandmarksstringYes / NoTemperaturefloatTemperature at the locationWeatherstringSunny / Rainy / Foggy / Snowydemandfloat🎯 Target variable (0 to 1)

⚙️ Setup
1. Clone the repo
bashgit clone https://github.com/sayanmitra/TrafficIQ.git
cd TrafficIQ
2. Install dependencies
bashpip install -r requirements.txt
3. Download the data
Get train.csv and test.csv from our shared Google Drive:
🔗 [Google Drive Link] — replace this with actual link
Place both files inside the data/ folder.
4. Start working
Open the baseline notebook:
bashjupyter notebook notebooks/baseline.ipynb

🚀 Workflow
Explore data → Clean & engineer features → Train model → Validate locally → Submit

Explore — understand the data, spot missing values
Clean — handle nulls in RoadType, Temperature, Weather
Feature engineer — extract hour/minute from timestamp, decode geohash
Train — try XGBoost, LightGBM, Random Forest
Validate locally — use 80/20 split, check R² score
Submit only if local score improves ⚠️


🏆 Best Score
Score   : —
Model   : —
By      : —
Date    : —

📦 Dependencies
See requirements.txt for full list. Key libraries:

pandas, numpy — data handling
scikit-learn — ML models & evaluation
xgboost, lightgbm — gradient boosting models
matplotlib, seaborn — visualization


Competition hosted on Hackerearth | Team TrafficIQ
