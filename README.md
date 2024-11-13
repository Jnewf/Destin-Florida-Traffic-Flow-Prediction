# Destin Florida Traffic Flow Prediction

## Overview

This project predicts traffic flow and congestion in Destin, Florida, using publicly available traffic and weather data. By applying machine learning models, the project offers insights for city planners and autonomous vehicle systems. The project culminates in an interactive dashboard for real-time traffic predictions and analysis.

## Repository Structure

- **`Destin Traffic Data.pdf`**: Raw traffic volume data from FDOT.
- **`Destin Weather Data.csv`**: Historical weather data from OpenWeather.
- **`merged_traffic_weather_data.csv`**: Combined dataset after preprocessing.
- **`engineered_traffic_data.csv`**: Dataset with engineered features.
- **Model Artifacts**:
  - `decision_tree_model.joblib`: Trained classifier for traffic congestion levels.
  - `linear_regression_model.joblib`: Trained regressor for traffic volumes.
  - Scalers: `dt_scaler.joblib`, `lr_scaler.joblib`.
- **Analysis Outputs**:
  - `decision_tree_results.csv`: Congestion predictions.
  - `linear_regression_results.csv`: Traffic volume predictions.
  - Visuals: `correlation_heatmap.png`, `feature_importance.png`, `confusion_matrix.png`, `regression_scatter.png`, `error_distribution.png`.
  - Error statistics: `error_statistics.csv`.
- **Jupyter Notebooks**:
  - `Step 1 - Merge Datasets.ipynb`: Data collection and preparation.
  - `Step 2 - Feature Engineering and Selection.ipynb`: Feature generation and selection.
  - `Step 3 - Model Development.ipynb`: Model training and saving.
  - `Step 4 - Model Evaluation and Analysis.ipynb`: Model performance evaluation.
  - `Step 5 - Traffic Prediction Dashboard.ipynb`: Dashboard implementation.

## Project Workflow

### Step 1: Data Collection and Preparation
- **Traffic Data**: Extracted hourly counts from FDOT traffic station reports.
- **Weather Data**: Processed historical weather conditions via OpenWeather API.
- **Output**: `merged_traffic_weather_data.csv`, a synchronized dataset with cleaned traffic and weather data.

### Step 2: Feature Engineering and Selection
- **Engineered Features**:
  - Time-based: Hour, day of the week, weekend/holiday flags.
  - Weather-based: Temperature categories, precipitation levels.
  - Traffic-based: Rolling averages, congestion levels.
- **Analysis**:
  - Correlation heatmap to identify influential features.
  - Feature importance evaluation.
- **Output**: `engineered_traffic_data.csv`.

### Step 3: Model Development
- **Models**:
  - Decision Tree Classifier: Predicts congestion levels (accuracy ~92%).
  - Linear Regression: Predicts traffic volume (R² ~0.976).
- **Training**:
  - Train/test split (80/20).
  - Hyperparameter tuning.
- **Artifacts**: Models saved as `.joblib` files.

### Step 4: Model Evaluation and Analysis
- **Metrics**:
  - Classification: Accuracy, precision, recall, F1-score.
  - Regression: Mean Absolute Error, R².
- **Outputs**:
  - Confusion matrix and scatter plots.
  - Feature importance chart: `feature_importance.png`.
  - Error distribution: `error_distribution.png`.
  - Result files (`decision_tree_results.csv`, `linear_regression_results.csv`).
  - Error statistics: `error_statistics.csv`.

### Step 5: Traffic Prediction Dashboard
- **Implementation**:
  - Built using Python libraries (Matplotlib, Pandas, ipywidgets).
  - Displays real-time predictions and a 24-hour forecast.
- **Features**:
  - Inputs for weather and time adjustments.
  - Visual comparison of predictions vs. actual traffic data.

## How to Use

1. **Setup**:
   - Clone the repository.
   - Install dependencies: `pip install pandas numpy matplotlib ipywidgets scikit-learn`.

2. **Run Jupyter Notebooks**:
   - Sequentially execute the provided notebooks for data preparation, modeling, and evaluation.
   - To launch the dashboard, run `Step 5 - Traffic Prediction Dashboard.ipynb`.

3. **Dashboard**:
   - Adjust weather and time inputs to view real-time predictions.
   - Analyze forecasted traffic patterns for planning or decision-making.

## Limitations and Future Work
- **Current Focus**: Single traffic station in Destin, Florida.
- **Improvements**:
  - Expand to multiple locations.
  - Integrate live traffic data.
  - Incorporate seasonal trends.

## Acknowledgments
- FDOT for traffic data.
- OpenWeather for weather data.
- scikit-learn for machine learning tools.

---
For questions or collaboration, please contact Joey Newfield at joey.newfield@gmail.com.
