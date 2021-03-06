# Supervised Learning
## Project: Finding Donors for CharityML


### Data

The modified census dataset consists of approximately 42,000 data points, with each datapoint having 13 features. This dataset is a modified version of the dataset published in the paper *"Scaling Up the Accuracy of Naive-Bayes Classifiers: a Decision-Tree Hybrid",* by Ron Kohavi. Find the related paper [online](https://www.aaai.org/Papers/KDD/1996/KDD96-033.pdf), with the original dataset hosted on [UCI](https://archive.ics.uci.edu/ml/datasets/Census+Income).

**Features**
- `age`: Age
- `workclass`: Working Class (Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked)
- `education_level`: Level of Education (Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool)
- `education-num`: Number of educational years completed
- `marital-status`: Marital status (Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse)
- `occupation`: Work Occupation (Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces)
- `relationship`: Relationship Status (Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried)
- `race`: Race (White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black)
- `sex`: Sex (Female, Male)
- `capital-gain`: Monetary Capital Gains
- `capital-loss`: Monetary Capital Losses
- `hours-per-week`: Average Hours Per Week Worked
- `native-country`: Native Country (United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands)

**Target Variable**
- `income`: Income Class (<=50K, >50K)

### Steps taken:
**1. Importing datasets( 'census.csv' and 'test_census.csv')**
![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/data.PNG)

![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/test.PNG)

**2. Explore datasets**
![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/data_info.PNG)

![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/train_info.PNG)

**3. Explore target variable**
![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/Data_exploration.PNG)

**4. Split dataframe into features and target variable(income)**
![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/Split_data_features.PNG)

![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/split_data_income.PNG)

**5. Explore continuous(skewed and non-skewed) and categorical features in dataset**
![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/Unique_val_categorical.PNG)

![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/cont_categ_features.PNG)

**6. Visualization continuous features**
![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/visualise_contin_1.PNG)

![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/visualise_contin_2.PNG)

- Skewed(Skewed is the one, where, 2 halves of the visualisation does not appears as mirror images of each other), (or)
![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/Skewed_distr_cont_1.PNG)

- Non-Skewed( Non-skewed or Symmetric features is one, where 2 halves appear as mirror images of each other.) 

**7.Transforming features-**
- Skewed Continuous features-(via Log Tranformation)

![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/Skewed_distr_cont_2.PNG)

- Continuous Features- (Normalization)

![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/Normalize_features.PNG)

![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/features_after_normalize.PNG)

- Categorical Features- (One Hot Encoding)
![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/one_hot_categ.PNG)

**8. Visualisation- Correlation Matrix**

Correlation Matrix of Continuous Features in dataset-

![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/corelation_cont.PNG)

-It can be seen from the below data of continuous features, that, there are ouliers present in them, but, won't affect much on non-linear models.

Correlation Matrix of All Features in dataset-

![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/corelation_all.PNG)
- It can be seen from the below correlation graph that, there is not much correlation between the features, except for the few outliers.
- In the income column, it can be easily observed that except for the few features such as- age, education_num, marital-status-married,
 all the other features don't have that much higher (of >0.2 ) correlation with income column.

**9. Data Modeling**
-   Split Dataset 'census' into 'train' and 'Validation'
-   Base Model Metric Calculation
-   Apply machine learning models- 
      Random Forest Classifier
      Gradient Boosting Classifier
      AdaBoost Classifier
      Logistic Regression
      XGBoost Classifier
-   Comparison of models based upon ROC-AUC Score Metrics-
![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/metrics_calc_All_models.PNG)
-   Hyperparameter Tuning for AdaBoost Classifier
-   Hyperparameter Tuning for Gradient Boosting Classifier
-   Hyperparameter Tuning for XGBoost Classifier
-   Hyperparameter Tuning for Random Forest Classifier
-   Hyperparameter Tuning for Logistic Regression
-   Look for reduced dataset(with most important features) against full dataset
-   Comparison of all combination of models to choose the best optimized model(Top3 models- AdaBoost, XGBoost and Gradient Boosting).

**10. Test dataset**
-   Handle missing Values in test dataset
      - Continuous features with gaussian disctribution(Mean values from train dataset)
     -  Continuous features with skewed distribution (Median values from train dataset)
     -  Catogorical features(fill values with most frequent value- Mode in train set)
-   Data Preprocessing and EDA steps, same as 'census'- training dataset
-   Predict model, based upon best optimized model
-   Save models and Upload results from best optimized model on Kaggle.

**11.Results**

![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/result-1.PNG)
![alt text](https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/images/result-2.PNG)

#     Best model:  0.9325 (score for 3 models)

Code in Python File-

https://github.com/rickhagwal/KaggleCompetitions/blob/master/Donors_for_Charity_ML/Charity_ML_competition.ipynb

