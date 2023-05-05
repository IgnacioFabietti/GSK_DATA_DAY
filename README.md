# GSK_DATA_DAY

### Problem Statement
* Do patients that take the GSK drug respond more to treatment compared to those in the control group?

* Can the age, weight or protein concentration of patients predict whether they will respond better to treatment or not?


### Background
A new cancer treatment for solid tumours (Miraculon-B) is in development at GSK, data hasbeen collected in our recent clinical trial comparing Miraculon-B to the current standard of care (i.e., referred to as the ‘control’). The trial has completed, and we need your help to analyse the data and assess the effectiveness of Miraculon-B. To do this we need you to compare Miraculon-B to the standard of care, and explore how different patient sub-groups may benefit differently from treatment.

### Goal

Using advanced data modelling techniques, we want to predict if the GSK drug respond more to treatment compared to those in the control group. Ultimately, we want to find ways we can use these predictions to help a doctor so they can quickly and easily access the information they need to make informed decisions about patient care. This can improve patient outcomes.

### Methods

The dataset is fairly small, around 800 entries. RESPONSE seems to be the column one would like to predict using the remaining columns and is a binary variable, implying in a binary classification problem. Columns are numeric characteristic of the patients sample whose behaviour we want to predict (in Y for positive or N for negative). We also note that there are null values, outliers and duplicates.

We replaced the missing data with the mean of each class, removed ouliers and duplicates, and scale each variable via a MinMax normalisation (0,1). Subsequently, we did a train-test-split of 80-20 in order to train the ML models including:  Logstic Regression, Decision Tree-based,  Random Forest,  Gradient Boosting, K-Nearest Neighbors and Support Vector Machines. We judged our model based on Accuracy, Precision, Recall and F1 score.

### Results 

Using Logistic Regression we were able to achieve an F1 score of 75.59% which is considered a good score (the score ranges from 0.5, the equivalent of random guessing, to 1.0, always correct). To help understand the model, we utilised Shapley Values, where it was revealed that protein concentration was the most important variable in the classification. This means the protein is an important biomarker.

### Recommendation

The Model could be  improved with further patient data (omics, blood tests, ethnicity, etc.).
Also, the model can be incorporated into a web app for doctors so they can quickly and easily access the information they need to make informed decisions about patient care. This can improve patient outcomes. 

### Risks and Assumptions
The results of this study depend greatly on certain assumptions. The authors of the dataset have pointed out that this is not real GSK data, but it is similar to the type of data and the type of questions they explore every day. Thus, deploying this model should be done after testing with laboratory results of real life scenarios.

### Data Dictionaries

About clinical-study.csv file:

Column description:

```
subject_id: Patient ID
sex: Whether the patient is male or female
age: The age of the patient
weight: The weight of the patient
height: The height of the patient
trt_grp: Whether the patient is receiving the new drug or the standard of care (control)
Response: Whether the patient responded or not (Yes[Y]/No [N])
```

About protein-levels.csv file:

Column description:

```
participant_id: Patient ID
protein_concentration: Concentration of a blood protein (ug/L) that might be a potential predictive biomarker of response
```
