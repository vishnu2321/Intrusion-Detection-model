# Ensemble model for Intrusion Detection

Problem: The intrusion on systems for its information is one of the biggest problems need to be stopped.

This can be done using Machine Learning Model.

Dataset URL: <https://www.kaggle.com/datasets/vishnumandala/kdddata>

The dataset columns are written in code file manually.

---------------------------------------------------------------------------------------------------------------------------------

### Preprocessing

The corelation matrix for all the columns is calculated and the columns with corelation coefficient > 0.95 are dropped.
According to corelation coefficients, the following columns are dropped:

    - num_root (Correlation = 0.9938277978738366)
    - srv_serror_rate (Correlation = 0.9983615072725952)
    - srv_rerror_rate (Correlation = 0.9947309539817937)
    - dst_host_srv_serror_rate (Correlation = 0.9993041091850098)
    - dst_host_serror_rate (Correlation = 0.9869947924956001)
    - dst_host_rerror_rate (Correlation = 0.9821663427308375)
    - dst_host_srv_rerror_rate (Correlation = 0.9851995540751249)

Converting the character columns to numerical columns using one-hot encoder.
Scaling the all columns using MinMax scaler.

---------------------------------------------------------------------------------------------------------------------------------

### Models

    - RandomForest
    - KNN (k-Nearest Neighbors)
    - SVC (Support Vector Classification)
    - Logistic Regression
    - Decision Tree with AdaBoost
    - Decision Tree

---------------------------------------------------------------------------------------------------------------------------------

### Ensemble model

Using above all models assigned weight based on their accuracy.
When a new record is tested using the model every model outputs a class label and based on this class label and weight, resultant of all models i.e; (weight*output of model), output of ensemble model is done.
The ensemble model is called as Voting Classifier.

---------------------------------------------------------------------------------------------------------------------------------
