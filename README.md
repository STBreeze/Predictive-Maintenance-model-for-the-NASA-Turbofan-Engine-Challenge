# Predictive Maintenance Model for NASA Turbofan Engine Degradation Using a *RandomForest Regressor* with *Time-Series Features*

## Project Overview
This project focuses on developing a predictive maintenance model for the NASA Turbofan Engine Degradation Dataset. The goal is to predict the Remaining Useful Life (RUL) of turbofan engines, which is the number of operational cycles left before the engine fails. By accurately forecasting RUL, maintenance can be optimized, reducing costs and preventing unexpected failures.

The model uses a regressive approach with time-series features to predict RUL, avoiding the complexity of neural networks like CNNs or LSTMs. Traditional time-series models like ARIMA were not suitable due to the inconsistent lifecycle trends of the engines. Instead, a robust machine learning approach was adopted to handle the dataset's unique characteristics.

## Dataset Description
The dataset consists of three files:

- Training Data (train_FD001.txt): Contains run-to-failure data for 100 engines.
- Test Data (test_FD001.txt): Contains operational data for 100 engines, stopped before failure.
- RUL Data (RUL_FD001.txt): Contains the actual RUL values for the test engines at the point of failure.

Each engine is monitored using 21 sensors and 3 operational settings, recorded over multiple cycles. The dataset includes noise and anomalies, which were addressed during preprocessing.

## Methodology
The project follows these steps:

- Static columns (e.g., OpSet_3, Sensor_1, etc.) were removed to reduce dimensionality.
- Anomalies were detected and replaced using polynomial regression and percentile-based methods.
- Time-series features like moving averages and consecutive differences were introduced to capture trends.
- A Random Forest Regressor was used to predict RUL.
- The model was trained on the preprocessed training data and evaluated on the test set.
- Performance metrics like MSE, RMSE, MAE, MAPE, and R² were calculated.
- Predicted RUL values were compared against actual RUL values.

## Data Visuals
#### Subplot of *Sensors vs Cycles* for All Engines
![Sensors vs Cycles (All Engines)](https://github.com/STBreeze/Predictive-Maintenance-model-for-the-NASA-Turbofan-Engine-Challenge/blob/main/Images/SubPlot_All%20Sensors%20LifeCycle%20(Global%20Representation)_Train%20Set.png?raw=true)
#### Anomalies Present vs Anomalies Handled (Ex: Engine 12, Sensor 9)
![Anomalies Present](https://github.com/STBreeze/Predictive-Maintenance-model-for-the-NASA-Turbofan-Engine-Challenge/blob/main/Images/Engine%2012_Sensor%209_Anomaly%20Plot.png?raw=true)
![Anomaly Handled](https://github.com/STBreeze/Predictive-Maintenance-model-for-the-NASA-Turbofan-Engine-Challenge/blob/main/Images/Engine%2012_Sensor%209_Anomaly%20Handled%20Plot.png?raw=true)
#### Actual vs Predicted RULs (All Engines)
![Actual vs Predicted RULs](https://github.com/STBreeze/Predictive-Maintenance-model-for-the-NASA-Turbofan-Engine-Challenge/blob/main/Images/Actual%20vs%20Predicted%20RULs_Max%20LifeCycle.png?raw=true)

## Results
- Mean Squared Error (MSE): 661.31
- Root Mean Squared Error (RMSE): 25.72
- Mean Absolute Error (MAE): 19.41
- Mean Absolute Percentage Error (MAPE): 0.31
- R² Score: 0.62

## Conclusion
The predictive maintenance model successfully forecasts the RUL of turbofan engines with reasonable accuracy. The use of time-series features and robust anomaly handling improved the model's performance. However, there is room for improvement in handling noise and capturing complex trends.

## Future Work
- Advanced Models: Experiment with neural networks like LSTMs or CNNs to capture more complex patterns.
- Feature Engineering: Explore additional time-series features or domain-specific knowledge.
- Hyperparameter Tuning: Further optimize the Random Forest Regressor or test other regression models.
