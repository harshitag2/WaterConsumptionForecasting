# WaterConsumptionForecasting
# IIT Kanpur Residential Water Consumption Forecasting

## Project Overview

This project predicts **8-hourly water consumption** for residential buildings at IIT Kanpur (such as Hall 12, Hall 10, Hall 6, etc.). The objective is to develop accurate regression models to forecast water usage, leveraging meteorological, calendar, and engineered time-series features. The results can support campus water resource management and planning.

---

## Data Description

- **Target Variable:**  
  - 8-hourly water consumption (liters) for each residential building.

- **Features Used:**
  - **Meteorological:**  
    - Precipitation
  - **Calendar & Time-of-Day:**  
    - `isday` (daytime indicator)
    - `isnight` (nighttime indicator)
    - `isnormalweekday` (regular weekday flag)
    - `isfest` (festival day flag)
    - `isholiday` (holiday flag)
  - **Engineered Time-Series:**  
    - Lag features (previous consumption values)
    - Rolling window statistics (mean, std, etc.)
  - **Other:**  
    - Building identifier (categorical, one-hot encoded)

---

## Workflow

1. **Data Loading & Preprocessing**
    - Loaded raw water consumption and meteorological/calendar data.
    - Merged datasets and handled missing values.
    - Converted categorical features to numerical form.
    - Generated lag and rolling features to capture temporal patterns.

2. **Exploratory Data Analysis (EDA)**
    - Visualized consumption trends by building and time.
    - Analyzed correlation between features and the target variable.
    - Checked for outliers and data distribution.

3. **Feature Engineering**
    - Created lag features (e.g., previous 8h, 16h, 24h consumption).
    - Computed rolling statistics for various window sizes.
    - Incorporated calendar and meteorological variables.

4. **Modeling**
    - Split data into training and validation sets.
    - Trained and evaluated several regression models:
        - XGBoost Regressor
        - Decision Tree Regressor
        - Random Forest Regressor
        - Polynomial Regression (degree 2, "poly2lin")
    - Used cross-validation and grid search for hyperparameter tuning.

5. **Evaluation**
    - Assessed models using Mean Absolute Percentage Error (MAPE) and other metrics.
    - **Best performance:** Achieved MAPE of **6%** with Polynomial Regression (degree 2).

6. **Visualization & Interpretation**
    - Plotted predicted vs. actual consumption.
    - Visualized feature importances and residuals.

---

## Getting Started

1. **Clone the repository:**
    ```
    git clone <repository-url>
    cd <repository-directory>
    ```

2. **Install dependencies:**
    ```
    pip install -r requirements.txt
    ```

3. **Run the main notebook:**
    - Open `Copy_of_W_Work-1.ipynb` in Jupyter Notebook or Google Colab.
    - Execute cells sequentially to reproduce preprocessing, feature engineering, modeling, and evaluation.

---

## Repository Structure

- `data/` — Raw and processed datasets
- `notebooks/` — Jupyter notebooks for EDA and modeling
- `src/` — Python scripts for feature engineering and utilities (optional)
- `README.md` — Project documentation

---

## Results

- **Best Model:** Polynomial Regression (degree 2, "poly2lin")
- **Best MAPE:** 6% on validation data

---

## Contact

For questions or collaboration, please contact [Your Name] at [your-email@domain.com].

---

## Acknowledgements

- Data provided by IIT Kanpur campus utilities.
- Project inspired by sustainable water management initiatives.

