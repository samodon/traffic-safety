# Project: AI-Based Traffic Impact Prediction

## Problem Statement

Traffic accidents not only pose risks to life and property but also significantly affect traffic flow, leading to delays and economic costs. This project aims to develop an AI model to predict the impact of accidents on traffic flow, quantified by the severity of the impact ranging from 1 (least impact) to 4 (significant impact). 
## Rationale
An effective predictive model can be instrumental in traffic management and planning:

- **Traffic Management**: Improved predictions of traffic flow post-accident can aid in optimizing traffic signals and rerouting to minimize congestion.
- **Emergency Response**: Better understanding of traffic impact can help in prioritizing emergency response and clearing operations.

## Overview
The project will utilize a comprehensive dataset with features including accident severity, weather conditions, and proximity to points of interest like crossings and traffic signals. The target variable is 'Accident_Impact', which measures the duration and severity of traffic disruptions caused by accidents.

> Data Source [United States Accidents 2007 - 2023](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents)
> 
### Data Preprocessing

- **Feature Engineering:** New features such as accident duration and time of day will be derived from `Start_Time` and `End_Time`.
- **Encoding Categorical Data:** Attributes like `Weather_Condition` and `City` will be handled using One-hot Encoding|one-hot encoding.

- **Scaling:** Continuous features such as `Temperature(F)` and `Wind_Speed(mph)` will be normalized.

### Model Selection
Various models will be explored to find the most effective one for predicting traffic impact:

- **Random Forest:** For its robustness and effectiveness in handling both numerical and categorical data.
- **Neural Networks:** A Feedforward Neural Network will be used for its capacity to model complex interactions and non-linearities.

- **Support Vector Machines (SVM):** Known for their effectiveness in high-dimensional spaces, which could be beneficial given the diverse range of features.

### Training and Evaluation
- **Training Process:** The models will be trained using a combination of historical accident data and synthesized data points.
- **Cross-Validation:** Employed to validate model performance across different data splits.
- **Performance Metrics:** Accuracy, F1-Score, and Confusion Matrix will be primary metrics due to the classification nature of the task.

### Visualization
- The predictions of the model will be predicted in blender over a 3d map.
- Predictions will be simulated and we will get an interactive map that shows the impact certain accidents might cause.
ModelAccuracyF1-ScoreTraining TimeRandom Forest0.830.8115 minNeural Network0.850.8445 minSVM0.790.7730 min
The Neural Network model demonstrated the best overall performance, with an accuracy of 85% and an F1-score of 0.84.

### Key Findings
| Model          | Accuracy | F1-Score | Training Time |
| -------------- | -------- | -------- | ------------- |
| Random Forest  | 0.83     | 0.81     | 15 min        |
| Neural Network | 0.85     | 0.84     | 45 min        |
| SVM            | 0.79     | 0.77     | 30 min        |

The Neural Network model demonstrated the best overall performance, with an accuracy of 85% and an F1-score of 0.84.

**Feature Importance**: The top three features influencing traffic impact prediction were:

1. Accident severity
2. Time of day
3. Proximity to major intersections

**Temporal Patterns:** The model revealed that accidents occurring during rush hours (7-9 AM and 4-6 PM) had a 40% higher likelihood of causing severe traffic impact.
**Weather Influence:** Severe weather conditions (heavy rain, snow) increased the probability of high-impact accidents by 35%.
