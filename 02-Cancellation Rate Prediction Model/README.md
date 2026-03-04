# 🏨 Hotel Booking Cancellation Prediction

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-red)

## 📌 Project Overview
This project aims to predict the likelihood of hotel booking cancellations using historical data. High cancellation rates lead to revenue loss and inventory management challenges. By leveraging **Machine Learning** , this model identifies high-risk bookings, allowing hotel management to optimize their overbooking strategies and improve revenue efficiency.

## 🗂️ Dataset Description
The dataset contains booking information for a city hotel and a resort hotel, including features such as:
- **Lead Time**: Number of days between booking and arrival.
- **ADR**: Average Daily Rate.
- **Deposit Type**: Whether a deposit was made (No Deposit, Non-Refundable, Refundable).
- **Customer History**: Previous cancellations and stays.
- **Booking Channels**: Distribution channels and segments.



## 🛠️ Data Pipeline & Methodology
1. **Data Preprocessing**: 
   - Handled missing values (e.g., `children`, `country`).
   - Feature encoding for categorical variables (One-Hot Encoding / Label Encoding).
   - Removed outliers in `ADR` and `adults` counts.
2. **Exploratory Data Analysis (EDA)**:
   - Analyzed the impact of **Lead Time** on cancellation probability.
   - Visualized the distribution of cancellations across different months and hotel types.
3. **Model Selection**:
   - Compared multiple classifiers: **Logistic Regression**, **Random Forest**, and **XGBoost**.
   - Evaluated models based on **Accuracy**, **Precision**, **Recall**, and **F1-Score**.
4. **Hyperparameter Tuning**: 
   - Utilized `GridSearchCV` to optimize model performance.



## 📈 Key Insights
- **Lead Time**: Bookings made far in advance (e.g., >150 days) are significantly more likely to be canceled.
- **Deposit Type**: "Non-refundable" deposits, counter-intuitively, often correlate with specific segments that have high cancellation records in this dataset.
- **Parking**: Customers requesting parking spaces almost never cancel their bookings.

## 📊 Results
| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :--- | :--- | :--- | :--- |
| Logistic Regression | 0.XX | 0.XX | 0.XX | 0.XX |
| Random Forest | 0.XX | 0.XX | 0.XX | 0.XX |
| **XGBoost (Best)** | **0.XX** | **0.XX** | **0.XX** | **0.XX** |

*(Note: Please update the table above with the specific metrics from your Colab output.)*

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone [https://github.com/yourusername/hotel-cancellation-prediction.git](https://github.com/yourusername/hotel-cancellation-prediction.git)
