# 🚗 Traffic Flow Forecasting using Machine Learning

A machine learning project that forecasts future traffic flow using historical traffic data from multiple traffic locations.

## 📌 Project Overview

Traffic forecasting can help understand traffic patterns and estimate future traffic conditions.

In this project, historical traffic data from 36 locations was processed and aggregated into an overall traffic-flow time series. A Linear Regression model was trained using the previous 10 time points to predict the next traffic-flow value.

## 🎯 Objectives

- Load and inspect historical traffic data.
- Process traffic data from multiple locations.
- Create a time-series traffic-flow dataset.
- Generate forecasting features using previous observations.
- Train a Linear Regression model.
- Evaluate forecasting performance.
- Compare actual and predicted traffic flow.
- Predict the next traffic-flow value.
- Save the trained model for future use.

## 📊 Dataset

The dataset contains traffic-flow observations from **36 locations**.

### Dataset Information

- Training locations: **36**
- Training time points: **1,260**
- Testing time points: **839**
- Forecasting window: **10 time points**
- Target: **Next traffic-flow value**
- Data values: Normalized traffic measurements

The dataset also includes an adjacency matrix describing relationships between traffic locations.

## 🔄 Data Processing

The following steps were performed:

1. Loaded the training and testing datasets.
2. Removed the CSV index column.
3. Calculated the average traffic across all 36 locations.
4. Created a single overall traffic-flow time series.
5. Used a sliding window of 10 previous observations.
6. Used these observations to predict the next traffic value.

### Forecasting Structure

```text
Previous 10 Traffic Values
          ↓
   Machine Learning Model
          ↓
   Next Traffic Value
```
## 🤖 Machine Learning Model
### Algorithm: Linear Regression
The model uses the previous 10 traffic-flow observations as input features and predicts the next traffic-flow value.
Linear Regression was selected as a fast and interpretable baseline forecasting model.

## 📈 Model Performance
The model was evaluated on the unseen testing data.

### Metric     Result
 MAE        0.01007
 RMSE       0.01311
 R² Score   0.99174
    
The model achieved an R² score of approximately 99.17% on the test data.

Because the traffic values are normalized, MAE and RMSE are reported on the normalized scale.

## 📊 Visualizations
The notebook contains visualizations for:
▪️Traffic flow over time
▪️Actual vs predicted traffic flow
These visualizations help evaluate how closely the model follows the actual traffic pattern.

## 🔮 Future Traffic Prediction
The trained model was tested using the most recent 10 traffic observations.
### Recent Traffic Values
0.24148

0.22800

0.19883

0.16856

0.15029

0.14443

0.12207

0.11362

0.09353

0.09139

### Predicted Next Traffic Value
### 0.08322
The prediction indicates a continued decrease in the normalized traffic-flow value based on the recent trend.

## 🛠️ Technologies Used
▪️Python

▪️Pandas

▪️NumPy

▪️Matplotlib

▪️Scikit-learn

▪️Joblib

▪️Jupyter Notebook

## 📁 Project Structure
Traffic-Flow-Forecasting/
│
├── Traffic Flow Forecasting.ipynb
├── traffic_forecasting_model.pkl
└── README.md

## ▶️ How to Run

1. Clone the repository
git clone https://github.com/hifzaabid458-cloud/Traffic-Flow-Forecasting.git

2. Install dependencies
pip install pandas numpy matplotlib scikit-learn joblib jupyter

3. Open the notebook
jupyter notebook
Open:
Traffic Flow Forecasting.ipynb

4. Run the notebook cells sequentially
The notebook contains the complete workflow from data loading and preprocessing to model training, evaluation, visualization, and future prediction.

## 💾 Trained Model
The trained Linear Regression model is provided as:
traffic_forecasting_model.pkl
The model can be loaded using Joblib:
import joblib

model = joblib.load("traffic_forecasting_model.pkl")

## 🚀 Future Improvements
Possible improvements include:
▪️Testing Random Forest and other regression models.

▪️Using individual traffic locations instead of averaging them.

▪️Incorporating the traffic adjacency matrix.

▪️Exploring advanced time-series models.

▪️Experimenting with LSTM or other deep learning architectures.

▪️Building a real-time traffic prediction application.

▪️Deploying the model as a web or mobile application.

## 👩‍💻 Author
### Hifza Abid
Computer Science Student | Data Science & Machine Learning Enthusiast
