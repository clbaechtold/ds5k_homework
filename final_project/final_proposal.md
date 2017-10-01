#Classification of Fraudulent Credit Card Purchases
---
My final project is an effort to train a model that can accurately identify fraudulent credit card purchases.  I plan on using a dataset of credit card transactions in September 2013 by European cardholders over a two-day period (284,807 transactions).  The data can be found on Kaggle at [https://www.kaggle.com/dalpozz/creditcardfraud](https://www.kaggle.com/dalpozz/creditcardfraud).

*There are two primary challenges in using this dataset to build a model that predicts fraudulent transactions:*
####Class Imbalance
Because this dataset includes all purchases from cardholders over the course of a two-day period, the classes (fraudulent/legitimate) are highly unbalanced in favor of legitimate purchases.  This should come as no surprise, given that the vast majority of credit purchases made are legitimate.  However, it means that I will have to use some creative techniques (such as under/oversampling) to bulid training sets that are more well balanced.  This imbalance also means that I will have to consider alternative measures of model performance besides just accuracy (such as Precision, AUROC, etc.).
####Feature Obfuscation
For confidentiality reasons, this dataset has been obfuscated so that the original data features are indiscernible.  In fact, the data has been PCA-transformed, with the only remaining original features being time and amount.  Because PCA transformation is a common pre-processing technique, this is not a problem for training a model.  It does, however, mean that our model will present very little qualitative insight (without knowing more about the original features that went into the PCA transformaton).


