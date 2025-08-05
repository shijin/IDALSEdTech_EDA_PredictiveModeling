# IDALS EdTech Subscription Prediction

## Project Overview
This project aims to predict the type of subscription plan a user is most likely to choose on the IDALS dance-based ed-tech platform. The prediction is based on user profile features such as dancer type, learning goals, interests, and historical behavior.

The insights and models developed here help the platform personalize offers, improve marketing strategies, and reduce churn.

---

## Business Problem

> **Can we predict a user’s subscription plan based on their profile, dancer type, learning goals, and genre interests?**

IDALS offers multiple subscription tiers:  
- Free  
- Weekly  
- Monthly  
- Half-Yearly  
- Yearly  

Understanding the drivers behind each subscription type can improve conversions and inform product decisions.

---

## Dataset Overview

- Source: Internal user data from the IDALS platform
- Total Records: 14,557 users
- Target Variable: `subscription_plan` (Multiclass - 5 categories)

**Key Features:**
- `type_of_dancer`
- `genres_of_interest`
- `purpose_of_learning`
- `future_aspirations`
- `repeated_subscriber`
- `signup_month`, `signup_day`, `signup_hour` (engineered from timestamp)

---

## Tools & Technologies Used

- **SQL (Snowflake)** – For data cleaning and preprocessing
- **Python** – For EDA, modeling, and evaluation
- **Pandas, NumPy, Matplotlib, Seaborn** – Data analysis and visualization
- **Scikit-learn, XGBoost** – Machine learning models
- **Power BI (Next phase)** – For interactive dashboards

---

## Exploratory Data Analysis (EDA) – Key Insights

- ~88% of users chose the **Free plan**
- Most users signed up during **late 2020 lockdown** and dropped off post-2021
- Advanced and career-oriented dancers were slightly more likely to choose paid plans
- Subscriptions were highest during **daytime hours (10 AM – 8 PM IST)**
- High class imbalance in the target variable

---

## Modeling Approach

**Models Implemented:**
1. Logistic Regression (Multiclass)
2. Random Forest Classifier
3. XGBoost Classifier

**Steps Followed:**
- One-hot encoding of categorical features
- Label encoding of the target variable
- Train-test split (80/20)
- Model training and evaluation using:
  - Accuracy
  - Classification Report
  - Confusion Matrix
- Hyperparameter tuning (for XGBoost)

---

## Model Performance Summary

| Model              | Accuracy | Notes                       |
|-------------------|----------|-----------------------------|
| Logistic Regression | ~46%     | Poor recall for minority classes |
| Random Forest      | ~88.5%   | Biased toward "Free" class  |
| XGBoost            | ~89.3%   | Best performance, but still biased due to class imbalance |

**Insight:** Despite improved accuracy, models were biased toward the dominant "Free" class. This highlights the need for richer and more predictive features.

---

## Feature Importance (XGBoost)

Top contributing features:
- `purpose_of_learning`
- `signup_month`
- `repeated_subscriber`
- `type_of_dancer`
- `signup_hour`

---

## Recommendations

- Focus on **Free-to-Paid conversion** campaigns
- Improve data collection: engagement time, course completion, user demographics
- Re-frame classification as **Free vs Paid** for better model performance
- Apply **SMOTE or resampling** to balance class distribution
- Continuously retrain model as new data becomes available

---


## Author

**Shijin Ramesh**  
_Data Analyst | edTech & Social Impact Enthusiast_

---

## License

This project is intended for educational and internal analytics use only. Please contact the author for any reuse or external publication.



## 📁 Project Structure

