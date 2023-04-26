# Titanic
Trough data processing and analyzing as well as model building and evaluating, I chose models and made a better prediction of survival probability of people who were on Titanic. My steps are as follows:

Feature analysis
1. I analyzed features and made a classification:
1) numerical features
a. continuous features: age, fare. 
b. discrete features: sibsp, parch.
2) categorical features:
a. categorical features: survived, sex, embarked. 
b. ordinal features: pclass.
3) mixed features:
a. alphanumeric: cabin
b. alphanumeric and numeric: ticket

2. I analyzed features and found features that contain null value:
At a glance of parts of training data and test data, I found cabin, age, embarked features have empty value. I used .info( ) and .describe( ) functions to check statistical information and distribution, and confirmed my opinion.

3. I made assumption of features’ correlation with survival:
1) high correlation: age, embarked
2) low correlation (may be dropped): ticket, cabin, id

4. I made more assumptions based on common sense:
1) women (sex=female) had higher survival rate than men
2) children (age<x) had higher survival rate than adults
3) upper-class passengers (pclass=1) had higher survival rate 

Data analysis
1. I analyzed data to confirm my assumptions above
I analyzed a feature’s correlation with survival through analyzing data between them. I used .groupby( ) function to check data between features below:
1) pclass and survival
2) age and survival
3) sibsp and survival
4) parch and survival

2. I visualized survival data with age, and I found
1) children (age <5) had high survival rate.
2) many (15< age <30) year old people had low survival rate.

3. I visualized survival data with pclass and age, and I found:
1) children in pclass=2 and pclass=3 had high survival rate. 
2) people in Pclass=1 had high survival rate. 

4. I visualized survival data with pclass, sex, embarked, and I found:
if Embarked=C, mens had higher survival rate. There is a correlation between embarked and pclass as well as pclass and survived.

5. I visualized survival data with fare, sex, embarked, and I found:
People paid high fare had high survival rate

Data processing
1. I dropped features (cabin, ticket, id) that have low correlation with survival.

2. I converted categorical features to numerical ones. 
1) sex: female = 1, male=0
2) embarked: 'C': 0, 'Q': 1, 'S': 2

3. I completed numerical feature age by guessing with correlated features
Due to correlation among age, sex, and pclass. I used median values for age across sets of pclass and sex feature combinations. Say, median age for pclass=1 and sex=0, pclass=1 and sex=1, etc.
I did not use the way that using random numbers between mean and standard deviation, because I did not wan to introduce random noise. 

4. I created new features that might have correlation with survival:
1) agegroup: a few (5) numerical sections (based on age), then convert age feature to 0-4 ordinal 
2) familysize: total number of family members on board (based on sibsp and parch)
3) alone: equals to 1 if number of familysize is 1, equals to 0 otherwise, then convert family feature to 0 and 1
4) fareclass: a few (4) numerical sections (based on fare), then convert fare to 0-3

5. I completed a fare value by a median. I completed a embarked value by a most frequent value.

Model selection and evaluation
I ran three models: Support Vector Machines, Perceptron, and Stochastic Gradient Descent. I got the comparsion result. This is easy to choose the best model: SVM

I analyzed correlation factor of each feature in Stochastic Gradient Descent and Perceptron.

Reference: 
https://www.kaggle.com/startupsci/titanic-data-science-solutions
