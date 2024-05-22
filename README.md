# NASA C-MAPSS Turbofan Engine Degradation Simulation Dataset

## Description
The NASA C-MAPSS dataset is a well-known public dataset for asset degradation modeling, focusing on predicting the remaining useful life (RUL) of turbofan jet engines. This dataset, provided by the Prognostics CoE at NASA Ames, contains Run-to-Failure simulated data from turbo fan jet engines under various operational conditions and fault modes.

### Prediction Goal
The primary objective of using this dataset is to predict the remaining useful life (RUL) of each engine in the test dataset. The RUL indicates the number of operational cycles left for the engine after the last data point in the test dataset.

### Experimental Scenario
- **Training Data**: Each time series represents the operational history of a different engine, with multiple multivariate time series datasets available.
- **Test Data**: Time series data that ends some time before system failure.
- **Objective**: Predict the number of remaining operational cycles before failure for the engines in the test set.

### Data Characteristics
- **Operational Settings**: Three settings significantly affecting engine performance.
- **Sensor Data**: Data from 26 sensor channels to characterize fault evolution.
- **Sensor Noise**: The dataset includes noise to simulate real-world conditions.

## Data Set Organization
Four different datasets (FD001, FD002, FD003, and FD004) are available, each varying in the number of train and test trajectories, operational conditions, and fault modes.

| Data Set | Train Trajectories | Test Trajectories | Conditions | Fault Modes                        |
|----------|--------------------|-------------------|------------|------------------------------------|
| FD001    | 100                | 100               | ONE        | ONE (HPC Degradation)              |
| FD002    | 260                | 259               | SIX        | ONE (HPC Degradation)              |
| FD003    | 100                | 100               | ONE        | TWO (HPC and Fan Degradation)      |
| FD004    | 248                | 249               | SIX        | TWO (HPC and Fan Degradation)      |

### Data Format
The data is provided as a zip-compressed text file with 26 columns:
1. Unit number
2. Time (cycles)
3. Operational setting 1
4. Operational setting 2
5. Operational setting 3
6. Sensor measurement 1
7. Sensor measurement 2
8. ...
26. Sensor measurement 26

## Reference
A. Saxena, K. Goebel, D. Simon, and N. Eklund, "Damage Propagation Modeling for Aircraft Engine Run-to-Failure Simulation," Proceedings of the 1st International Conference on Prognostics and Health Management (PHM08), Denver CO, Oct 2008.

## Analysis Workflow

### 1. Data Analysis
#### 1.1 Info about data
- Load and explore the dataset to understand its structure and contents.
- Visualize data distributions and identify any patterns or anomalies.

### 2. Noise Removal and Normalization
- Implement techniques to clean the data by removing noise and normalizing sensor readings.
- Ensure that the data is suitable for model training and testing.

### 3. Training and Validation
#### 3.1 Training Performance of Different Models
- Train various models to predict RUL, including Random Forest, Linear Regression, and Logistic Regression.
- Evaluate and compare their performances.

#### 3.2 Random Forest
##### 3.2.1 Random Forest Validation Performance
- Assess the performance of the Random Forest model on validation data.
##### 3.2.2 Random Forest Validation Prediction vs Actual
- Compare the predictions made by the Random Forest model against actual RUL values.

#### 3.3 Linear Regression
##### 3.3.1 Linear Regression Validation Performance
- Evaluate the Linear Regression model on validation data.
##### 3.3.2 Linear Regression Validation Prediction vs Actual
- Compare Linear Regression model predictions with actual RUL values.

#### 3.4 Logistic Regression
##### 3.4.1 Logistic Regression Validation Performance
- Assess the Logistic Regression model's performance.
##### 3.4.2 Logistic Regression Validation Prediction vs Actual
- Compare Logistic Regression predictions with true RUL values.

### 4. Testing
#### 4.1 Random Forest Testing
- Test the Random Forest model on unseen data and evaluate its performance.
#### 4.2 Linear Regression Testing
- Test the Linear Regression model and assess its accuracy.
#### 4.3 Logistic Regression Testing
- Test the Logistic Regression model and evaluate the results.

## Conclusion
This dataset provides a comprehensive foundation for developing and testing prognostic models for predicting the remaining useful life of turbofan engines. By following the outlined workflow, you can explore various modeling techniques and their effectiveness in predicting RUL, ultimately contributing to improved maintenance and reliability in aerospace applications.
