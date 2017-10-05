# Classification of Fraudulent Credit Card Purchases
---
My final project is an effort to train a model that can accurately identify fraudulent credit card purchases.  I plan on using a dataset of credit card transactions in September 2013 by European cardholders over a two-day period (284,807 transactions).  The data can be found on Kaggle at [https://www.kaggle.com/dalpozz/creditcardfraud](https://www.kaggle.com/dalpozz/creditcardfraud).

**There are two primary challenges in using this dataset to build a model that predicts fraudulent transactions:**
#### Class Imbalance
Because this dataset includes all purchases from cardholders over the course of a two-day period, the classes (fraudulent/legitimate) are highly unbalanced in favor of legitimate purchases.  This should come as no surprise, given that the vast majority of credit purchases made are legitimate.  However, it means that I will have to use some creative techniques (such as under/oversampling) to bulid training sets that are more well balanced.  This imbalance also means that I will have to consider alternative measures of model performance besides just accuracy (such as Precision, AUROC, etc.).
#### Feature Obfuscation
For confidentiality reasons, this dataset has been obfuscated so that the original data features are indiscernible.  In fact, the data has been PCA-transformed, with the only remaining original features being time and amount.  Because PCA transformation is a common pre-processing technique, this is not a problem for training a model.  It does, however, mean that our model will present very little qualitative insight (without knowing more about the original features that went into the PCA transformaton).

## Process
### Exploratory Data Analysis
As a result of the aforementioned feature obfuscation, the opportunities for effective exploratory data analysis were somewhat limited.  Fortunately, Principal Component Analysis is a very effective method for utilizating unsupervised learning in order to both perform dimensionality reduction, as well as to minimize covariance between iniput features.  For these reasons, the PCA-transformed dataset still proved to be very effective for building a model.  Ideally, an original raw dataset would be available to perform addiitonal EDA in order to best assess and infer the qualitative impact of certain raw data features on the likelihood of a purchase being fraudulent.
### Model Success Criteria
Due to the significant class imbalance in the target variable, a raw accuracy score will be ineffective for indicating a model's success at predicting purchase outcomes.  Instead, we will look at a maximizing True Positive classification rates, minimizing False Positive rates, and maximizing AUROC scores.  
### Model Techniques
I will focus on two primary techniques for classification:
* Logistic Regression

...Logistic regression is appealing because on non-transformed data, the coefficients returned by the model are actually interpretable and meaningful.  While this data is PCA transformed, I would like to assess how a Logistic Regression classifier performs, in the hopes that turning a similar model to un-transformed raw transaction data migth lead to insightful interpretation of coefficients.
* Random Forest

...Because the dataset has already been PCA-transformed, the covariance between input features should be maximized.  As a result, we are already presented with the ideal feature set for performing binary splitting on the data such as decision trees.  This, in combination with the class imbalance, indicates that ensembling decision trees using a Random Forest classifier is likely to lead to producing an effective model. 

