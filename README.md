# Allergy Medication Response Classification

## Business Context

In the pharmaceutical and healthcare industries, understanding how patients respond to allergy medications is critical
for improving treatment outcomes and minimizing adverse effects. Allergies affect millions of people globally, and treat-
ments often involve antihistamines, corticosteroids, or immunotherapy. However, not all patients respond the same way
to these medications due to factors such as age, genetics, comorbidities, and environmental exposure. By leveraging
machine learning to classify patient responses—such as effective, partially effective, or ineffective—healthcare providers
and pharmaceutical companies can personalize treatment plans, reduce trial-and-error prescribing, and enhance patient
satisfaction. This approach also supports pharmacovigilance efforts by identifying patterns of poor response or side effects
early in the treatment cycle.

From a business perspective, this classification model can be integrated into digital health platforms, electronic health
records (EHRs), or mobile health apps to provide real-time decision support for clinicians. Pharmaceutical companies
can use the insights to refine drug development strategies, target specific patient segments, and improve post-market
surveillance. Insurance providers may also benefit by aligning reimbursement policies with evidence-based outcomes. Ul-
timately, this solution contributes to a more data-driven, patient-centric healthcare ecosystem, where treatment decisions
are informed by predictive analytics rather than generalized assumptions. For students, this exercise offers a practical
application of supervised learning techniques in a high-impact domain, combining structured medical data with real-world
business value.

## Problem Statement

The goal of this exercise is to develop a machine learning classification model that predicts whether a patient will respond
positively to a given allergy medication. Allergic conditions such as hay fever, asthma, and skin reactions are commonly
treated with various medications, but individual responses can vary significantly due to factors like age, medical history,
genetic predisposition, and environmental exposure. By analyzing patient data—including demographics, symptoms,
prior treatments, and clinical outcomes—students will build a model that classifies responses as effective, partially effec-
tive, or ineffective. This classification can help healthcare providers personalize treatment plans, reduce trial-and-error
prescribing, and improve patient outcomes. The exercise will also introduce students to key concepts in supervised
learning, feature engineering, model evaluation, and ethical considerations in medical AI. The final model should be
interpretable and suitable for integration into clinical decision support systems or digital health applications.

The dataset simulates real-world clinical and demographic data, capturing key factors that influence treatment outcomes.
Each row in the dataset represents a unique patient case, and the goal is to classify the response to medication as Effective,
Partially Effective, or Ineffective. The dataset includes a mix of numerical, categorical, and ordinal features that
reflect patient characteristics, treatment details, and environmental factors. The following attributes are included in the
dataset:

- `age`: Integer value representing the patient’s age in years.
- `gender`: Categorical variable indicating the patient’s gender (e.g., Male, Female, Other).
- `allergy type`: Categorical variable specifying the type of allergy (e.g., pollen, food, dust, pet dander).
- `symptom severity`: Ordinal variable describing the severity of symptoms before treatment (e.g., Mild, Moderate,
Severe).
- `medication type:` Categorical variable indicating the class of medication prescribed (e.g., Antihistamine, Corti-costeroid).
-  `dosage mg`: Numeric value representing the daily dosage of the medication in milligrams.
- `treatment duration days`: Integer value for the number of days the patient has been on the medication.
- `comorbid conditions`: Categorical variable listing any coexisting conditions (e.g., Asthma, Eczema, None).
- `previous response`: Categorical variable describing the patient’s response to similar medications in the past (e.g. Good, Poor, None).
- `environmental exposure`: Categorical variable indicating the level of allergen exposure (e.g., High, Medium, Low).

The target variable, `response class`, will be used to train and evaluate the classification mode.

## Delivery

Please upload the Jupyter Notebook containing the Python code you used to solve the exercise, and the Excel file with
the results of the 100 samples.

The files should follow this naming convention: wsi ani25 project {surname} {name}.ipynb and wsi ani25 project {surname}.

## Evaluation

The final score will be based on a combination of two components: the classification accuracy measured by the number
of correct predictions out of 100 samples, and a code review, which will assess the quality and sophistication of your
implementation.


  | Model               | Why I Tried                                                                                         |
  |---------------------|-----------------------------------------------------------------------------------------------------|
  | Logistic Regression | Simple baseline; with strong L2 regularization (C=0.001), resists overfitting on small data         |
  | SVM (RBF)           | Can capture non-linear patterns; small C prevents fitting noise                                     |
  | Decision Tree       | Interpretable; with depth limits, acts as simple rule learner                                       |
  | Random Forest       | Reduces variance through bagging; shallow trees prevent overfitting                                 |
  | XGBoost             | Gradient boosting with built-in L1/L2 regularization (reg_alpha, reg_lambda)                        |
  | LightGBM            | Faster than XGBoost; leaf-wise growth can be more efficient on small data                           |
  | CatBoost            | Native categorical handling (no encoding needed); strong regularization; often wins on tabular data |
  | Naive Bayes         | Works well on small datasets; assumes feature independence (good when features are weak)            |
  | AdaBoost            | Focuses on hard examples; weak learners ensemble reduces overfitting                                |
  | Bagging             | Reduces variance; good when individual models are unstable                                          |
  | Voting Ensemble     | Combines top models; reduces individual model variance                                              |
  | Stacking Ensemble   | Meta-learner can find optimal model combination                                                     |
