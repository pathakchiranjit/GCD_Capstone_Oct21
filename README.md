# GCD_Capstone_Oct21

Group project work for collaboration

Our observation excel link: https://docs.google.com/spreadsheets/d/19R8Q97o2LflUFxKcLMHxMrBY74ZZN3Bw/edit?usp=sharing&ouid=101218510265072520044&rtpof=true&sd=true

==================================================================================================================================

### Capstone Group Project (GCD) - **Consulting Assignments**

<img src="https://github.com/pathakchiranjit/GCD_Capstone_Oct21/blob/main/Picture/Pic_2.jpg?raw=true" align='left'><br/>

The rapidly transforming business landscape means that there are currently many challenges faced by Human Resource (HR) departments / partners. Due to the fluctuating economy as well as local and global advancements, there are many changes occurring rapidly that affect HR in a wide range of issues. Current practice includes majorly below processes,
- Once an employee leaves, he or she is taken an interview with the name **“exit interview”** and shares reasons for leaving. 
- The **HR Department** then tries and learns insights from the interview and makes changes accordingly.

This suffers from the following problems:

- **This approach is too haphazard. The quality of insight gained from an interview depends heavily on the skill of the interviewer.**
- **These insights can't be aggregated and interlaced across all employees who have left.**
- **It is too late by the time the proposed policy changes take effect**.

With the advancement of technologies, most HR departments are now using **analytic tools** to predict whether an employee is likely to **leave** leveraging out their **historical data** and subsequently making more proactive steps in reaching out them before it's too late.

According to **McKinsey, artificial intelligence and other advanced analytics will unlock 9.5 trillion to 15.4 trillion** annually. Data-driven decision-making in HR is not only part of this trend - it is central to the future of HR. 

As a part of these **digital approach**, one of the big tech giants hires **INSAIDians** as a consultant in order to understand the behaviour of their parmanent employee.

<img src="https://github.com/pathakchiranjit/GCD_Capstone_Oct21/blob/main/Picture/Pic_5.JPG?raw=true" align='left'><br/>

### **Weekly Goals for the team?**:
The DS consultant team will follow the below week-wise goals,

<img src="https://github.com/pathakchiranjit/GCD_Capstone_Oct21/blob/main/Picture/Pic_6.png?raw=true" align='left'><br/>

## Table of Contents

1. [Objective: Problem Statement](#section1)<br>
2. [2. Tools : Importing Packages, Libraries & Defining Functions:](#section2)<br>
  - 2.1 [Import Packages and Libraries:](#section201)<br>
  - 2.2 [Defining Functions :](#section202)<br>
    - 2.2.1 [missing_data : To find all the missing data in the data set](#section2021)<br>
    - 2.2.2 [Standardize_data : To standardize all the data fit with train and transform the test splitted data set.](#section2022)<br>
    - 2.2.3 [Standardize_data_only : To standardize all the data fit and transform the whole data set.](#section2023)<br>
    - 2.2.4 [Classification models : base model](#section2024)<br>
    - 2.2.5 [Classification models : cross validation](#section2025)<br>
    - 2.2.6 [Classification models : Hypertuning using GridSearchCV](#section2026)<br>
3. [Collecting & Loading Data](#section3)<br>
  - 3.1 [Collect data from MySQL Instances:](#section301)<br>
    - 3.1.1 [Import User details from "department_data" database](#section3011)<br>
    - 3.1.2 [Import User details from "employee_details_data" database](#section3012)<br>
    - 3.1.3 [Import User details from "employee_data" database](#section3013)<br>
  - 3.2 [ Import unseen dataset from downloaded csv file (import from G-Drive):](#section302)<br>
4. [Data Preprocessing](#section4)<br>
  - 4.1 [Basic checks:](#section401)<br>
    - 4.1.1 [Data types and Info](#section4011)<br>
    - 4.1.2 [Missing value info](#section4012)<br>
  - 4.2 [Checking the occurance of the missing and unrealistic data:](#section402)<br>
    - 4.2.1 [Employee ID missing values:](#section4021)<br>
    - 4.2.2 [Department missing values:](#section4022)<br>
    - 4.2.3 [Tenure and statisfaction missing values:](#section4023)<br>
    - 4.2.4 [ "last_evaluation" missing values:](#section4024)<br>
    - 4.2.5 [Checking any duplicate:](#section4025)<br>
5. [Data processing and Imputing methodologies:](#section5)<br>
  - 5.1 [Imputation of the missing values:](#section501)<br>
    - 5.1.1 [Handling strategy for missing data for 'tenure' and 'satisfaction:](#section5011)<br>
    - 5.1.2 [Imputation of the missing 'department':](#section5012)<br>
    - 5.1.3 [Imputation of the missing values : 'last_evaluation', 'tenure' and 'satisfaction' score for training set:](#section5013)<br>
    - 5.1.4 [Imputation of the missing values : 'last_evaluation', 'tenure' and 'satisfaction' score for unseen-test set:](#section5014)<br>
    - 5.1.5 [Merging the employee and employee_details dataset based on 'employee_id':](#section5015)<br>
  - 5.2 [Statistical checking of columns:](#section502)<br>
    - 5.2.1 [Skew ness and transformation checking of train dataset:](#section5021)<br>
    - 5.2.2 [Skew ness and transformation checking of test dataset:](#section5022)<br>
  - 5.3 [Feature study:](#section503)<br>
    - 5.3.1 [Exploratory Data Analysis:](#section5031)<br>
        - 5.3.1.1 [EDA: Avg_monthly_hrs with other factors](#section50311)<br>
        - 5.3.1.2 [EDA: last_evaluation with other factors](#section50312)<br>
        - 5.3.1.3 [EDA: satisfaction with other factors](#section50313)<br>
        - 5.3.1.4 [EDA: tenure with other factors](#section50314)<br>
        - 5.3.1.5 [EDA: Department wise study](#section50315)<br>
        - 5.3.1.6 [EDA: "Status" wise study : Categorical variables](#section50316)<br>
        - 5.3.1.7 [EDA: "Status" wise study : Continuous variables](#section50317)<br>
    - 5.3.2 [Feature engineering and selection based on Correlation and Feature Importance study:](#section5032)<br>
6. [Machine Learning Model building:](#section6)<br>
  - 6.1 [Models with all features:](#section601)<br>
  - 6.2 [Models with Important features:](#section602)<br>
  - 6.3 [Models with Important features and Cross validation:](#section603)<br>
  - 6.4 [Models with Important features and Hypertuning:](#section604)<br>
  - 6.5 [Predicted Probability and AUC study using top 3 model:](#section605)<br>
  - 6.6 [Precision-Recall Curve and Classification Report:](#section606)<br>
  - 6.7 [ROC-AUC Curve and compare against no skill model:](#section607)<br>
  - 6.8 [Probability Value comparison of splitted test dataset among all models:](#section608)<br>
  - 6.9 [Prediction on Probability of 'Left' classes for unseen dataset using selected Top-3 Models:](#section609)<br>
  - 6.10 [Final submission of predicted Probability of 'Left' classe for unseen dataset using RandomForest with tuning Model:](#section6010)<br>
7. [Conclusions](#section7)
8. [Limitation of the study:](#section8)


<a id=section1></a>
## 1. Problem Statement


Based on **department data** and **employee data** regarding **administrative, work-load and mutual evaluation score** **Predict whether an employee will stay or leave** and subsequently **plan any proactive steps** in order **to retain employees** in the future.
