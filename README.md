# Importing packages and libraries
- Some useful packages and libraries:
    import numpy as np
    import pandas as pd
    import random
    import matplotlib.pyplot as plt
    import seaborn as sns
    from sklearn.preprocessing import RobustScaler
    from sklearn.linear_model import LogisticRegression
    from sklearn.model_selection import train_test_split
    from sklearn import metrics
    from sklearn.metrics import confusion_matrix, classification_report

# Importing Dataset
- Filename: 'titanic_raw.csv'

# Explanatory
### Missing Data
- Check missing data of each feature

### Heat map
- Check correlation between numerical features
  
### Visualization target based on feature
- **Survival Vs Demise**: It is clear that number of person survived is less than number of people demise.
- **Survival based on sex**: Most people who did not survive are much more likely to be male and people who survived are much likely to be female.
- **Survival based on Pclass**: People not survived belong to passenger class 3.
- **Survival based on Pclass and Sex**: PClass 3 - The Majority of male and half of female crowd could not make up to survive. PClass 2 and 1 - Almost all who did not survive are male.
- **Survival based on Embarked**
- **Survival based on Embarked and Pclass**: Embarked S - Majority of people died belong to PClass 3. Embarked C - Here Pclass 2 has less death compared to other 2 class, still Pclass 3 has majority of death. But when compared to Embarked C infact it is much much less. Embarked Q - Here Pclass 3 only have death rate.
- **Survival based on Fare**

### Statisticcal
- **Survival based on sex**: Out of total females traveled 74.2% of them could survive but only 18.9% of total male traveled could survive.
- **Survival based on Pclass**: 62.96% of PClass 1 could survive, and 47.28% of Pclass2 could survive and 24.24% of PClass3 could survive.
- **Survival based on Pclass and Sex**: PClass 3 - The Majority of male and half of female crowd could not make up to survive. PClass 2 and 1 - Almost all who did not survive are male.
- **Survival based on Embarked**: 55.36% of Embarked C could survive, and 38.96% of Embarked Q could survive and 33.7% of Embarked s could survive.

# Preprocessing
### Handling missing data
- **Age**: hanlde by median of each group Pclass.
- **Cabin**: Cabins are represented as C85, C123 etc. So we can drop this column.
- **Embarked**: Only two rows of Embarked is missing, so we can drop those two rows.

### Encoding categorical features
- Features Name and Ticket will have no significant meaning for determining target, so we can drop those two.
- For Embarked column, a dummy variable is to be assigned to each city. If our data does not belong to C and Q, it clearly means it will belong to S. This is called multicolinearity or dummy variable trap. That is by using one feature(s) we can predict another feature. To avoid this we will have to drop one dummy variable.
  
### Droping columns have any insignificant
- PassengerId is like index, it does have any significance for building model and also it will loose its meaning as index when we do feature scaling. So it can dropped.

# Train and Test split
- Split dataset into train_set and test_set with ratio 7:3.

# Features scaling
- Feature Scaling is scaling all features to make sure they all take values on the same scale. It prevents one feature to dominate over the other. Feature Scaling is done after we split the dataset into the training set and test set and it is applied to the training set.
  
# Logistic regression model
- Build the logistic regression

# Evaluation
### Confusion matrix
- True Positive : Positive outcome is correctly predicted as positive.
- True Negative : Negative outcome is correctly predicted as negative.
- False Positive: Negative outcome is wrongly predicted as positive.
- False Negative: Positive outcome is wrongly predicted as negative.

### Accuracy, Precision and Recall
- **Accuracy**: It is correctly predicted outcome to total outcomes.
- **Precision**: It tells us if we have predicted a positive outcome, how much we are sure it will be true positive. In mathematicaly we can say, it is the proportion of true positive on all positives predictions.
- **Recall**: It is the proportion of true positives on all actual positive elements. Recall is also known as true positive rate.

# Conclusion
- Survival is highly dependent on Pclass. This indicates the majority of people who could afford enough money to get in Pclass 1, were most likely to survive.
    * 62.96% of PClass 1 could survive
    * 47.28% of Pclass2 could survive
    * 24.24% of PClass3 could survive
- Majority of the passenger who could survive are females.
    * Out of total females traveled 74.2% of them could survive.
- Majority of the male passengers could not survive.
    * 18.9% of total male traveled could only survive
- Port from which the passengers have boarded also has a significant impact on the survival rate.
    * 55.36% of Embarked C could survive
    * 38.96% of Embarked Q could survive
    * 33.7% of Embarked s could survive