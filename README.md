# Electric Vehicle Range Prediction using Support Vector Regression (SVR)

##  Project Overview
This project uses **Support Vector Regression (SVR)** to predict the **range (in kilometers)** of electric vehicles based on their technical specifications. It processes both numeric and categorical features, applies preprocessing pipelines, trains an SVR model, evaluates performance, and visualizes predicted vs. actual values.

##  Dataset
**File Name:** `electric_vehicles_spec_2025.csv.csv`

The dataset contains specifications of electric vehicles, including both numeric and categorical attributes.

### Example Columns:
| Column Name       | Type        | Description |
|-------------------|-------------|-------------|
| `make`            | Categorical | Manufacturer name |
| `battery_capacity_kWh` | Numeric     | Battery size in kWh |
| `top_speed_kmh`   | Numeric     | Maximum speed in km/h |
| `acceleration_0_100_kph` | Numeric     | Time to reach 100 kph from standstill |
| `drive`           | Categorical | Drivetrain type (FWD, RWD, AWD) |
| `range_km`        | Numeric     | **Target variable** - EV driving range in km |
| `source_url`      | Categorical | Reference link for the data |
| `model`           | Categorical | Model name |

**Note:** The dataset may have missing values and both numeric & categorical features.

## ⚙️ Project Steps
1. **Import Libraries**: Uses Pandas, Matplotlib, and Scikit-learn.
2. **Load Dataset**: Reads CSV into a DataFrame.
3. **Feature Selection**: Drops `range_km` (target), `source_url`, and `model`.
4. **Identify Columns**: Separate numeric and categorical columns.
5. **Preprocessing**:  
   - Numeric → Mean imputation → StandardScaler  
   - Categorical → Most frequent imputation → OneHotEncoder
6. **Combine Preprocessing**: ColumnTransformer merges numeric & categorical steps.
7. **Model Pipeline**: Pipeline with preprocessor + SVR.
8. **Train/Test Split**: 75% training, 25% testing.
9. **Train Model**: Fit SVR pipeline to training data.
10. **Predictions**: Predict on test set.
11. **Evaluation**: Compute MSE, MAE, and R² score.
12. **Visualization**: Scatter plot of actual vs. predicted range.
