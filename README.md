# Predicting Patient Length of Stay: Hospital Resource Allocation
<i> Machine Learning Project for DSC540: Advanced Machine Learning at DePaul University </i><br>
<i> Highlights: Encoding for Target and Features, Tree Based Classifiers, Boosting Classifers, Optimization Models, Multi-class Learning Models, Voting Ensemble Models </i><br>

Analysis explores classification models for predicting patient length of stay (LOS), a multi-class categorical target, using various hospital related predictor features without patient demographics except patients’ age range. Extensive data preprocessing was explored including data encoding, outlier removal, and feature transformations to off set data imbalance. Tree, boosting, and histogram models were most effective for classification and optimized models using multi-class ensembles and voting ensembles were implemented.

The <a href="https://www.kaggle.com/datasets/arashnic/covid19-hospital-treatment">dataset</a> was obtained from Kaggle. A version of the dataset was originally used for Analytics Vidhya Healthcare Analytics Hackathon.

The approach and methology for the analysis begins with exploratory data analysis, data cleaning, removal of outliers for numeric features, and transformations for categorical features. Dummy variables were created for categorical features and label encoding used for target variable. Target variable was transformed from 9 categories to 5, encoded as as 0-10 days: 0, 11-20 days: 1, 21-30 days: 2, 31-40 days: 3, and 41+ days: 4. Data is split into training, testing, and validation at 70-20-10 split and normalized using min-max normalization. Baseline models were built for classification with strongest models being optimized using hyperparameter tuning. Additional optimization models were implemented using multi-class ensembles: OvR (One-vs-Rest) and OvO (One-vs-One) as well as voting ensembles using the most optimized models. 

Methodology:
1. Exploratory Data Analysis 
2. Preprocessing: Data cleaning and transformations
3. Train Test Split and Normalizations 
4. Baseline Models 
5. Extended/Additional Models 
6. Optimized Models 
7. Multi-class Models (OvR and OvO) 
8. Voting Ensemble Models 
9. Final model comparsion and results

Summary of Results:<br>
The Voting Ensemble model with OvR (Random Forest, Histogram-Based Gradient Boost, and AdaBoost) with soft voting achieved the highest accuracy score on the test set at 0.4784. This accuracy score is slightly higher than the validation accuracy score of 0.4728. Moreover, the voting ensemble approach sucessfully took three tree models and outputted a model that performed better than all other models. The runner up model goes to the optimized Histogram Gradient Boosting Classifier model which achieved a testing accuracy of 0.4781. This model is faster, more efficient and is a more simplied model than the voting ensemble model. There are several reasons that may be preventing the models from achieving higher performance. First, the dataset contains mostly categorical features with very few numeric features. Second, the data is also skewed in terms of distribution of features, with many of the features not following a normal distribution. Lastly, the target and predictor features are highlyn imbalanced, which becomes more challenging for the algorithm to learn and predict.
