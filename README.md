# Project_4
![image](https://www.houston-perio.com/wp-content/uploads/2019/07/STROKE.jpg)
# 1.1 Background
According to Mayo clinic **"An ischemic stroke occurs when the blood supply to part of the brain is interrupted or reduced, preventing brain tissue from getting oxygen and nutrients. Brain cells begin to die in minutes.A stroke is a medical emergency, and prompt treatment is crucial."**
The goal of this project is use machine learning to predict if a person will have stroke based on some features

**Data**  
1) id: unique identifier  
2) gender: "Male", "Female" or "Other"  
3) age: age of the patient  
4) hypertension: 0 if the patient doesn't have hypertension, 1 if the patient has hypertension  
5) heart_disease: 0 if the patient doesn't have any heart diseases, 1 if the patient has a heart disease  
6) ever_married: "No" or "Yes"  
7) work_type: "children", "Govt_jov", "Never_worked", "Private" or "Self-employed"  
8) Residence_type: "Rural" or "Urban"  
9) avg_glucose_level: average glucose level in blood  
10) bmi: body mass index  
11) smoking_status: "formerly smoked", "never smoked", "smokes" or "Unknown"*  
12) stroke: 1 if the patient had a stroke or 0 if not  

[Data source](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)
## 1.1.1 Import relevant libraries
1. The libraries used include:
    * Numpy
    * Panda
    * scikit-learn
    * Seaborn
    * Matplotlib
    * Imbalance-learn
    * scipy
    * Warnings
## 1.1.2 Load Datasets
The data was loaded using pd.read_csv('file_name')
## 1.2 Data Cleaning
* The Id column was dropped
* The missing values in BMI was replaced by average mean
* In gender column, Other gender type was dropped
* The data was split into train and test set
## 1.3 Exploratory Data analysis
* Age is partially normally distributed while avg_glucose_level and Bmi are rightly skewed
* Stroke is associated with the older population
* Stroke is higher in people with high average glucose level
* Stroke is more common in women
* Stroke is higher in people with high bmi.
* Married people are more susceptible to stroke
* Age, Hypertension, Heart disease and average glucose level are the most correlated to stroke
* Age is positively correlated to stroke, hence older people are associated with stroke
* Hypertension is positively correlated to stroke. Hypertension increase the likelihood of stroke
* Heart_disease is positively correlated to stroke. Presence of an heart_disease increase the likelihood of having stroke
* People living in Rural areas are less likely to have stroke
## 1.4 Data preprocessing
* The target and features were seperated
* Label Encoder was used on ever_married column
* pd.get_dummies was used on categorical variable
* MinMaxScaler was used on the numerical variable
* PCA was used to decorrelate the data
## 1.5 Model Fitting
* LogisticRegression was used as the base_line Model
* XGBClassifier was used to Train the data
## 1.6 Resampling
* The data was resampled because the model was inbalanced
## 1.7 Model Evaluation
![Confusion Matrix](https://github.com/issaissa2608/Stroke_prediction/assets/123243046/89f037aa-52f5-463e-b310-bdf92ecbb7e5)

## Feature Importance
![Feature Importance](https://github.com/issaissa2608/Stroke_prediction/assets/123243046/54d1e07d-b94b-471a-a4d5-fe02f1c6d417)



# References
https://scikit-learn.org/stable/modules/model_evaluation.html
https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html
https://xgboost.readthedocs.io/en/latest/python/python_api.html
