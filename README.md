# EDA_Capstone_Project3-Cardiovascular_risk_prediction-
<b>Problem Statement:</b>

The dataset is from an ongoing cardiovascular study on residents of the town of Framingham, Massachusetts. The classification goal is to predict whether the patient has a 10-year risk of future coronary heart disease (CHD). The dataset provides the patients’ information. It includes over 4,000 records and 15 attributes. Each attribute is a potential risk factor. There are both demographic, behavioural, and medical risk factors. Attributes includes various factors based on the mentioned three categories like sex, age, diabetes, TenYearCHD, is_smoking, etc. For this project, we have used various analysing techniques which includes Data acquisition, Data Description, Missing values imputation, Graphical Representation, Modelling, etc.

<b>Data gives us the following features:</b>

<b>Demographic:</b>

• Sex: male or female ("M" or "F")

• Age: Age of the patient;(Continuous - Although the recorded ages have been truncated to whole numbers, the concept of age is continuous)

<b>Behavioural </b>
• is smoking: whether or not the patient is a current smoker ("YES" or "NO")

• Cigs Per Day: the number of cigarettes that the person smoked on average in one day. (Can be considered continuous as one can have any number of cigarettes, even half a cigarette.)

<b>Medical(history)</b>

• BP Meds: whether or not the patient was on blood pressure medication (Nominal)

• Prevalent Stroke: whether or not the patient had previously had a stroke (Nominal)

• Prevalent Hyp: whether or not the patient was hypertensive (Nominal)

• Diabetes: whether or not the patient had diabetes (Nominal) Medical(current)

• Tot Chol: total cholesterol level (Continuous)

• Sys BP: systolic blood pressure (Continuous)

• Dia BP: diastolic blood pressure (Continuous)

• BMI: Body Mass Index (Continuous)

• Heart Rate: heart rate (Continuous - In medical research, variables such as heart rate though in fact discrete, yet are considered continuous because of large number of possible values.)

• Glucose: glucose level (Continuous)
Predict variable (desired target) • 10-year risk of coronary heart disease CHD (binary: “1”, means “Yes”, “0” means “No”) - DV

<b>Datasets:</b>
In this analysis we have used the following datasets.

Cardiovascular_risk_df: This dataframe is a created directly from the given file and since data was not very large all the attributes were included in this single dataframe and manipulated throughout the process.



<b>Steps involved:</b>

<b>Exploratory Data Analysis:</b>

After loading the datasets, various analysis was performed by comparing our target variable CHD with other independent variables. We performed various analysis like feature engineering, feature transformation, handling outliers, analyzing categorical and numerical data, Understanding important features, etc.

<b>Feature Engineering:</b>

1)Handling missing values:

While exploring our project we keep in mind to handle missing values and fill them with their respective mean and modes.

2)Duplicate values treatment:

There were no duplicate values in our dataset

3)Outliers:

 Outliers plays an important role for any machine learning project. In our project we had outliers at certain attributes. Instead of deleting them we imputed the outliers.
 
<b>EDA Visualization:</b>

EDA Visualization is performed by using seaborn libraries with various plots like histogram, violin plot, bar plot, etc. We have used these plots for describing correlations, for relationship of sex and person who is smoking or not, other attributes and their affect on target variable CHD. Visualizations comes in handy to do Univariate-variate and multi-variate analysis.

<b>Label Encoding:</b>

Machine Learning is performed only on numerical values, so there might be some column which do not have numerical values. Label Encoding is a popular encoding technique for handling categorical variables. In this technique, each label is assigned a unique integer based on alphabetical ordering. We performed this technique on attributes sex and is smoking.

<b>Feature Selection:</b>

Feature selection or variable selection is the process of selecting a subset of relevant features or variables from the total features of a level in a data set to build machine learning algorithms.

<b>Advantages of selecting features:</b>

There are various advantages of feature selection process. These are as follows: 

Improved accuracy

Simple models are easier to interpret.

Shorter training times

Enhanced generalization by reducing Overfitting

Easier to implement by software developers

Reduced risk of data errors by model use

Variable redundancy

Bad learning behaviour in high dimensional spaces

<b>Feature Splitting and Scaling</b>

Feature splitting and scaling were done using variance threshold and chi-square tests which gave us better idea of our attributes and helped eliminating additional features.

<b>Balancing target Variable</b>

Since our target variable CHD was unbalanced, we used SMOTE to balance it.

SMOTE (Synthetic Minority Oversampling Technique) consists of synthesizing elements for the minority class, based on those that already exist. It works randomly picking a point from the minority class and computing the k-nearest neighbors for this point. The synthetic points are added between the chosen point and its neighbors.

<b>ALGORITHMS:</b>


1) Logistic Regression Model

2)  k-nearest neighbor

3)Decision Tree 

4)Random Forest

1.Logistic Regression:(With and Without Hyper-parameter Tunning)

Logistic regression is a statistical model that in its basic form uses a logistic function to model a binary dependent variable, although many more complex extensions exist. In regression analysis, logistic regression (or logit regression) is estimating the parameters of a logistic model (a form of binary regression).

2.K-nearest Neighbour: (With and Without Hyper-parameter Tunning)

The k-nearest neighbors (KNN) algorithm is a simple, supervised machine learning algorithm that can be used to solve both classification and regression problems. It's easy to implement and understand, but has a major drawback of becoming significantly slows as the size of that data in use grows.

3.Decision Tree: (With and Without Hyper-parameter Tunning)

Decision trees help you to evaluate your options. Decision Trees are excellent tools for helping you to choose between several courses of action. They provide a highly effective structure within which you can lay out options and investigate the possible outcomes of choosing those options.

4.Random Forest Classifier:(Ensemble technique based on bagging)

A Random Forest is a reliable ensemble of multiple Decision Trees (or CARTs); though more popular for classification, than regression applications. Here, the individual trees are built via bagging (i.e., aggregation of bootstraps which are nothing but multiple train datasets created via sampling of records with replacement) and split using fewer features. The resulting diverse forest of uncorrelated trees exhibits reduced variance; therefore, is more robust towards change in data and carries its prediction accuracy to new data.
However, the algorithm does not work well for datasets having a lot of outliers, something which needs addressing prior to the model building.

<b>Model Performance:</b>

<b>Logistic Regression:</b>

For logistic regression the accuracy was 85.84 which increased to 85.98 after hyper parameter Tunning.

<b>K-nearest Neighbors:</b>

For K- nearest neighbors the accuracy was 84.36 which increased to 85.69 after hyper parameter Tunning.

<b>Decision Tree:</b>

For Decision Tree the accuracy was 74.92 which increased to 85.69 after hyper parameter Tunning.

<b>Random Forest Classifier:</b>

For Random Forest Classifier the accuracy was 84.80.

<b>Conclusion:</b>

 Features like BPmeds, prevalentStroke and diabetes are highly imbalanced.
 
The number of Smokers and non-Smokers in is smoking is almost the same.

Male’s smokes more compared to female.

Those who were smoking 20 Cigarettes per day above were having more risk of detecting CHD.

Education feature is irrelevant for our target variable which we came know after applying Chi-square test.

Features like Is_smoking and cigsPerDay were having multicollinearity so we chose we keep cigsPerDay out of these two as CigsPerDay is having more correlation with our target variable.

sysBp and diaBp they also have multicollinearity we chose diaBp feature to train our model.

Features like BPmeds, prevalentStroke and diabetes were not able to meet variance threshold of 99% so we discarded them.

females have more chances of getting CHD than males.

Chances of getting CHD are mostly among the age group 35-50. While age group below 35 has lowest chances of getting CHD. 

Logistic regression was easier to implement and interpret. While Random Forest Classifier takes lots of time to execute.

KNN and Decision tree took average time to execute and worked well. While tunning it with parameters was time consuming since each parameter change would affect on the results with variations.

<b>Challenges Faced:</b>

We have outliers in our dataset which accounts for 14% of data. So instead of discarding them we chose to impute them with median values of respective features.

We have 2 categorical features as string type which we labelled using label encoding.

We have so many features irrelevant for our model so we Adjust them like putting id feature as index and Those which have multicollinearity and values lower than variance threshold, we discarded them from our model.

Our target feature was highly Imbalanced. So, we use SMOTE to balance it before training. 

Some computations were complex and had to be done correctly since wrong computations would have led to loss of data. 

