# Project: AI-Based Traffic Impact Prediction

## Problem Statement

Traffic accidents not only pose risks to life and property but also significantly affect traffic flow, leading to delays and economic costs. This project aims to develop an AI model to predict the impact of accidents on traffic flow, quantified by the severity of the impact ranging from 1 (least impact) to 4 (significant impact). 
## Rationale
An effective predictive model can be instrumental in traffic management and planning:

- **Traffic Management**: Improved predictions of traffic flow post-accident can aid in optimizing traffic signals and rerouting to minimize congestion.
- **Emergency Response**: Better understanding of traffic impact can help in prioritizing emergency response and clearing operations.

## Overview
The project will utilize a comprehensive dataset with features including accident severity, weather conditions, and proximity to points of interest like crossings and traffic signals. The target variable is 'Accident_Impact', which measures the duration and severity of traffic disruptions caused by accidents.

> [!example] Data Source [United States Accidents 2007 - 2023](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents)
> 
### [[Data Preprocessing]]

- **Feature Engineering:** New features such as accident duration and time of day will be derived from `Start_Time` and `End_Time`.
- **Encoding Categorical Data:** Attributes like `Weather_Condition` and `City` will be handled using [[One-hot Encoding|one-hot encoding]].

> [!summary] One hot encoding transforms categorical variables into a format that can be provided to ML algorithms to do a better job in prediction.

- **Scaling:** Continuous features such as `Temperature(F)` and `Wind_Speed(mph)` will be normalized.

### Model Selection
Various models will be explored to find the most effective one for predicting traffic impact:

- **[[Random Forest]]:** For its robustness and effectiveness in handling both numerical and categorical data.
- **Neural Networks:** A [[Feedforward Neural Network]] will be used for its capacity to model complex interactions and non-linearities.

> [!todo] Explore advanced neural network architectures or ensemble models to enhance prediction accuracy.

- **Support Vector Machines (SVM):** Known for their effectiveness in high-dimensional spaces, which could be beneficial given the diverse range of features.

### [[Training and Evaluation]]
- **Training Process:** The models will be trained using a combination of historical accident data and synthesized data points.
- **Cross-Validation:** Employed to validate model performance across different data splits.
- **Performance Metrics:** Accuracy, F1-Score, and Confusion Matrix will be primary metrics due to the classification nature of the task.

### [[Visualization]]
- The predictions of the model will be predicted in blender over a 3d map.
- Predictions will be simulated and we will get an interactive map that shows the impact certain accidents might cause.

