# Newland
Final project for Machine Learning Subject in the [Master Degree Program in Data Science and Advanced Analytics](https://www.novaims.unl.pt/mdsaa) in [Nova IMS (Universidade Nova de Lisboa)](https://www.novaims.unl.pt/default). This project took part on a Kaggle competition obtaining the [2nd position](https://www.kaggle.com/c/newland/leaderboard). The exact guidelines for the project can be found [here](https://www.kaggle.com/c/newland).

**Only Machine learning models imported from [scikit-learn](https://scikit-learn.org/stable/supervised_learning.html#supervised-learning) library were allowed.**

This project was motivated by a fictional mission called “Newland”. After the discovery of a
habitable planet about 120.000 people were sent to populate the new world. With an emerging
economy and a second fleet arriving to the new planet, the Newland government decided that
residents should start paying taxes in order to increase the financial sustainability.

The purpose of this work was to aid the government forecast the impact of tax programs. The
exposed plan consisted in the application of a binary tax plan that depended on the income level
as above or below the average. In consequence, the initial stage of the project consisted in the
development of a predictive model to accurately classify the income of citizens in said two levels.

The provided dataset contained information on several features regarding each citizen’s general
demographic characteristics, including name, birthday, native continent, marital status, current
residency, education data, role, and employment sector. Additionally, it included information
regarding the selection process for the “Newland” mission (Money Received, and Ticket Price).


This project was develop by [Tiago Jose Isidoro Ramos](https://github.com/Exileus) and [myself](https://github.com/Farkites).

# Table of Contents
* [Technologies](#technologies)
* [Motivation](#motivation)
* [Data Collection](#data-collection)
* [Data Understanding](#data-understanding)
* [Data Preparation](#data-preparation)
* [Outliers](#outliers)
* [Data Standarization](#data-standarization)
* [Feature Selection](#feature-selection)
* [Modeling](#modeling)
* [Evaluation](#evaluation)
* [Deployment](#deployment)
* [Results & Interpretation](#results)
* [Conclusion](#conclusion)

Further information may be found on the [report](https://github.com/Farkites/Newland/blob/master/ML_report_group42.pdf).

# Technologies

* Python 3.8
* pandas v 1.1.3
* numpy v 1.19.2
* seaborn v 0.11.0
* scikit-klearn

# Motivation

The purpose of this work was to aid the government forecast the impact of tax programs. The
exposed plan consisted in the application of a binary tax plan that depended on the income level
as above or below the average. In consequence, the initial stage of the project consisted in the
development of a predictive model to accurately classify the income of citizens in said two levels.

# Data Collection
The dataset was provided to us, so no active collection was needed. It can be accessed [here](https://www.kaggle.com/c/newland/data)
or as using Kaggle API:
```
kaggle competitions download -c newland
```

# Data Understanding
The data was explored by the creation of tables and visualizations
of distributions, using the Python libraries pandas, matplotlib, and seaborn. For a clearer insight,
in this analysis different subsets of data organizations were pre-defined, as a distinction between
metric and categorical features.

The dataset is imbalanced, i.e., it has a disproportionate number of records
that belong to the class *Income* (below average) is the 76%.

# Data Preparation
Several feature transformation techniques were applied, but the ones that are important to
highlight, as they impacted positively the performance of the models, might be the following:
metric feature’s discretization, scaling, conversion of multi-class categorical features into binary,
merging sparse categories for some categorical features, and categorical to ordinal
transformation.

# Outliers
No significant outliers or missing values were found in the dataset; therefore, no data cleansing
techniques (e.g., record deletion or replacing data with central tendency measures) were applied
in the project.

# Feature Selection
![Selected features](https://github.com/Farkites/Newland/blob/master/res/features_table.png?raw=true)
All original features of the dataset were either kept, transformed, or engineered into a new feature,
except for Education Level. Features signaled as “least relevant” from applied decision trees and
feature importance metrics were still relevant enough that their exclusion decreased the
performance of all models.

# Modelling
Several models from the scikit-learn were tried:
* Logistic Regressor
* Naive Bayes
* K-Nearest Neighbors (KNN)
* Multilayer Perceptron (MLP)
* Support Vector Machine (SVM)
* Decision Tree
* Random Forest
* Gradient Boosting
* Adaboost Classifier
* Stacking

The last three models' hyper-parameters were tuned with special attention, as they delivered the most promising results.

# Evaluation
The evaluation metric for this project was Mean F1-Score. All models were trained in an iterative K-Fold process with stratification, given that the dataset is umbalanced.

# Results

Best results were obtained for the Gradient Boosting model, followed by the AdaBoost Classifier, and the Stacking. This last one shouldn't be considered as the it was composed by some non-weak models such as Gradient Boosting or AdaBoost, so it was just replicating the outputs of those models.

The project finally got the [second](https://www.kaggle.com/c/newland/leaderboard) best score of the competition and was [first](https://www.kaggle.com/c/newland/leaderboard) before the final test dataset was released 







