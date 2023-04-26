# Titanic

Jupyter Notebook
Readme.md
2 minutes ago
GitHub Flavored Markdown
File
Edit
View
Language
1
Trough data processing and analyzing as well as model building and evaluating, I chose models and made a better prediction of survival probability of people who were on Titanic. My steps are as follows:
2
​
3
Feature analysis
4
1. I analyzed features and made a classification:
5
1) numerical features
6
a. continuous features: age, fare. 
7
b. discrete features: sibsp, parch.
8
2) categorical features:
9
a. categorical features: survived, sex, embarked. 
10
b. ordinal features: pclass.
11
3) mixed features:
12
a. alphanumeric: cabin
13
b. alphanumeric and numeric: ticket
14
​
15
2. I analyzed features and found features that contain null value:
16
At a glance of parts of training data and test data, I found cabin, age, embarked features have empty value. I used .info( ) and .describe( ) functions to check statistical information and distribution, and confirmed my opinion.
17
​
18
3. I made assumption of features’ correlation with survival:
19
1) high correlation: age, embarked
20
2) low correlation (may be dropped): ticket, cabin, id
21
​
22
4. I made more assumptions based on common sense:
23
1) women (sex=female) had higher survival rate than men
24
2) children (age<x) had higher survival rate than adults
25
3) upper-class passengers (pclass=1) had higher survival rate 
26
​
27
Data analysis
28
1. I analyzed data to confirm my assumptions above
29
I analyzed a feature’s correlation with survival through analyzing data between them. I used .groupby( ) function to check data between features below:
30
1) pclass and survival
31
2) age and survival
32
3) sibsp and survival
33
4) parch and survival
34
​
35
2. I visualized survival data with age, and I found
36
1) children (age <5) had high survival rate.
37
2) many (15< age <30) year old people had low survival rate.
38
​
39
3. I visualized survival data with pclass and age, and I found:
40
1) children in pclass=2 and pclass=3 had high survival rate. 
41
2) people in Pclass=1 had high survival rate. 
42
​
43
4. I visualized survival data with pclass, sex, embarked, and I found:
44
if Embarked=C, mens had higher survival rate. There is a correlation between embarked and pclass as well as pclass and survived.
45
​
46
5. I visualized survival data with fare, sex, embarked, and I found:
47
People paid high fare had high survival rate
48
​
49
Data processing
