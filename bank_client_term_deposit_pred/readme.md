```
## The classification goal is to predict if the client will subscribe (yes/no) a term deposit (variable y).
```

# Attribute Information:

## bank client data:
- 1 - age (numeric)
- 2 - job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
- 3 - marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
- 4 - education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
- 5 - default: has credit in default? (categorical: 'no','yes','unknown')
- 6 - housing: has housing loan? (categorical: 'no','yes','unknown')
- 7 - loan: has personal loan? (categorical: 'no','yes','unknown')
##### related with the last contact of the current campaign:
- 8 - contact: contact communication type (categorical: 'cellular','telephone') 
- 9 - month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')
- 10 - day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')
- 11 - duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.
- 12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
- 13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
- 14 - previous: number of contacts performed before this campaign and for this client (numeric)
- 15 - poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')

Steps taken for analysis 
----------------------------
1. **Data Preprocessing and Cleaning**:
   - Handle missing values (impute).
   - Normalize or standardize features.
   - Encode categorical variables -label encoder.

2. **Feature Engineering**:
   - Create new features from existing ones.
   - Feature scaling.

3. **Selecting the Right Machine Learning Model**:
   - Choose an appropriate algorithm -  classification 
   - Consider factors like interpretability, scalability, and performance.

4. **Training Machine Learning Model**:
   - Split data into training and validation sets.
   - Adjust hyperparameters (e.g., learning rate, regularization strength).

5. **Evaluating Model Performance**:
   - Evaluation metrics (accuracy, precision, recall, roc-auc, etc.).
   - Validate the model on unseen data (validation set).
   - Avoid overfitting (high performance on training data but poor generalization).

6. **Tuning and Optimizing Model**:
   - Fine-tune hyperparameters (grid search).
   - Consider techniques like cross-validation.

Key take aways
-------------------------
I have started with using tree based algorithms  -
- DecisionTreeClassifier (Accuracy -71.5%)
- RandomForestClassifier (AUC = 87.5% ) - fine tuned using GridSearchCV, oob_error
- AdaBoostClassifier (AUC =  86%) - fine tuned using GridSearchCV 
- GradientBoostingClassifier (AUC =  88.5% ) - fine tuned using GridSearchCV 
