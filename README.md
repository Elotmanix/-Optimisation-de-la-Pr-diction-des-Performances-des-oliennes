# Wind Turbine Power Output Prediction and Analysis

## Project Overview
This project analyzes operational data from wind turbines to predict active power output (`TARGET`) and identify factors influencing performance. The workflow includes exploratory data analysis (EDA), data cleaning, and preparation for predictive modeling. The dataset contains **617,386 samples** across 79 features, including turbine operational metrics and environmental variables.

---

## Dataset
### Source
- **engie_X.csv**: Time-series sensor data (e.g., pitch angle, rotor speed, temperature).  
- **engie_Y.csv**: Active power output (`TARGET`) for each turbine.  
- Source: [Kaggle Datasets](https://www.kaggle.com/datasets) (Dataset IDs: 6833789, 6847447).  

### Key Features
- `MAC_CODE`: Turbine identifier (e.g., WT1, WT4).  
- `Date_time`: Timestamp of recordings.  
- `Pitch_angle`, `Rotor_speed`, `Hub_temperature`, `Wind_speed`, etc.  
- `TARGET`: Active power output (kW) [Target Variable].  

---

## Key Findings from EDA
1. **Data Overview**  
   - 617,386 samples × 79 features.  
   - `TARGET` ranges from **-19.48 kW** (potential sensor errors) to **2256.06 kW**, with a mean of **372.75 kW**.  

2. **Missing Values**  
   - Significant gaps in `Grid_voltage` (101,322 missing), `Generator_converter_speed` (8,064), and `Gearbox_inlet_temperature` (8,064).  

3. **Target Distribution**  
   - Right-skewed histogram: Most outputs cluster at lower values (<500 kW), with rare high-output outliers.  

4. **Turbine Variability**  
   - Boxplots reveal operational differences: `WT4` shows higher median output and variability compared to `WT3`.  

5. **Actionable Insights**  
   - Investigate negative `TARGET` values for data quality.  
   - Address missing data before modeling.  

---

## Methodology
### 1. Data Preparation
- Merged `engie_X.csv` and `engie_Y.csv` on `ID`.  
- Basic statistics, missing value checks, and data type validation.  

### 2. Exploratory Data Analysis (EDA)
- **Distribution Analysis**: Histogram of `TARGET` to identify skewness and outliers.  
- **Turbine Comparison**: Boxplots of `TARGET` by `MAC_CODE` to assess inter-turbine variability.  

### 3. Data Cleaning (Next Steps)
- Handle missing values (imputation or removal).  
- Address negative `TARGET` values (sensor errors or downtime).  

### 4. Predictive Modeling (Future Work)
- Build regression models (e.g., Random Forest, XGBoost) to predict `TARGET`.  
- Feature importance analysis to identify key performance drivers.  

---

## Repository Structure

wind-turbine-analysis/  
├── data/  
│   ├── engie_X.csv          # Sensor data  
│   └── engie_Y.csv          # Power output labels  
├── dlengie-final.ipynb      # Jupyter notebook with full analysis  
├── README.md                # Project documentation  
└── requirements.txt         # Python dependencies  
```

---

## Installation
1. Clone the repository:  
   ```bash
   git clone https://github.com/ELOTMANIX/Optimisation-de-la-Pr-diction-des-Performances-des-oliennes.git
   ```
2. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```
   Key libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`.


```
