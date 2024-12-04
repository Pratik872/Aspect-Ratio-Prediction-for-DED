# Additive Manufacturing Aspect Ratio Prediction

## Overview
- The dataset consists of records for different powder materials, substrate materials, process parameters (spot size, power, mass flowrate, travel velocity) and geometric measurements (height, width).
- Target variable: Aspect Ratio (H/W)
- The dataset contains processing parameters and geometric measurements from additive manufacturing experiments.

## Project Structure
- Data preprocessing and feature engineering
- Exploratory Data Analysis (EDA)
- Feature Selection using Mutual Information
- Model Development and Comparison
- Hyperparameter Tuning
- Results and Analysis

## Methodology

### Data Preprocessing
1. Handling Missing Values:
   - Spot Size (21% missing), Width and Height(9.30 % missing), Contact Angle(31.52% missing) - Imputed using KNN imputation
   - Aspect Ratio (18% missing) - Removed rows with missing target values
   
2. Feature Engineering:
   - Grouped Powder Materials into categories:
     * Nickel-based alloys (Inconel 625, NiCr, NiCrAlY)
     * Steel-based alloys (316L, PH13-8)
     * Cobalt-based alloys (Cobalt, Colmonoy, WC-12Co)
     * Titanium-based alloys (Ti-6Al-4V)
     * Copper-based alloys (CuNiCo)
   
   - Grouped Substrate Materials:
     * Steel-based (316L, Stainless Steel, Steel)
     * Nickel-based (Inconel 738)
     * Titanium-based (Ti-6Al-4V)
![Grouping_Powder_Mat](https://github.com/Pratik872/Aspect-Ratio-Prediction-for-DED/blob/main/images/powder_material_grp.png)
![Grouping_Substrate_Mat](https://github.com/Pratik872/Aspect-Ratio-Prediction-for-DED/blob/main/images/substrate_material_grp.png)

3. Feature Transformation:
   - Applied Box-Cox transformation(due to data being positively skewed) to handle skewness in: Spot Size, Power, Mass Flowrate, Travel Velocity, Height, Width

   ![Trasform1](https://github.com/Pratik872/Aspect-Ratio-Prediction-for-DED/blob/main/images/box_cox_transformation.png)
   ![Trasform2](https://github.com/Pratik872/Aspect-Ratio-Prediction-for-DED/blob/main/images/box_cox_transformation.png)
   ![Trasform3](https://github.com/Pratik872/Aspect-Ratio-Prediction-for-DED/blob/main/images/box_cox_transformation.png)
    

### Feature Selection
- Used Mutual Information to identify important features
- [Include feature importance plot]
- Key features identified: [List top features]

### Model Development
Implemented and compared multiple models:
1. Linear Regression
2. Random Forest
3. AdaBoost
4. XGBoost

### Hyperparameter Tuning
- Used GridSearchCV for optimization
- Parameters tuned:
  * Random Forest: n_estimators, max_depth, min_samples_split, min_samples_leaf
  * AdaBoost: n_estimators, learning_rate, loss
  * XGBoost: n_estimators, max_depth, learning_rate, subsample, colsample_bytree

## Results
[Include results table showing model performance]
- Best performing model: [Model name]
- Test R² Score: [Score]
- RMSE: [Score]

### Model Performance Visualization
[Include actual vs predicted plots]

## Built with 🛠️
- Python
- Libraries: pandas, numpy, scikit-learn, xgboost, seaborn, matplotlib
- Development environment: [Your IDE]

## Future Improvements
- [List potential improvements]