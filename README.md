# WiDS_Datathon
# Members 
- Ana Sordo (https://github.com/megaDeathChav)
- Gianelli Lagos (https://github.com/GianelliL)
- Fatima Mora Garcia (https://github.com/fmora22)
- Aisha Ahmad (https://github.com/aishaahmadd)

# Purpose
Using fMRI data, we built a model to predict both an individual’s sex and their ADHD diagnosis.

In this year’s WiDS Datathon, participants were tasked with building a model to predict both an individual’s sex and their ADHD diagnosis using functional brain imaging data of children and adolescents and their socio-demographic, emotions, and parenting information. 

This relates to the Break Through Tech AI program since we have learned how to do regression model selection, regression model fitting/testing, data cleaning, and preprocessing for model development and analysis. Break Through Tech has taught us the building blocks needed to be successful in this kaggle competition. The Break Through Tech AI program has also given us the opportunity to participate in this kaggle competition with team members that are also part of the program. 

Tools of this nature can help identify individuals who may be at risk of ADHD, which can be difficult to diagnose particularly in females. Importantly, they help shed light on the parts of the brain relevant to ADHD in females and males, which in turn could lead to improvements in personalized medicine and therapies. Identifying ADHD early and designing therapies targeting specific brain mechanisms in a personalized way can greatly improve the mental health of affected individuals.

# Data Exploration
Describe the dataset(s) used (i.e., the data provided in Kaggle + any additional sources):
We were given the following datasets:

- Data Dicitonary.xlsx -(Helps us understand what the fields and data for each field mean)

- Sample Submission.xlsx - (This is an example of what our submission should look like)

- TRAIN_CATEGORICAL_METADATA.xlsx - (socio-demographic information, e.g., subject’s “handedness” or “parent’s education level”, emotions (“Strength and Difficulties Questionnaire”), and parenting information (“Alabama Parenting Questionnaire”).)

- TRAIN_FUNCTIONAL_CONNECTOME_MATRICES.csv - (functional MRI connectome matrices)

- TRAIN_QUANTITATIVE_METADATA.xlsx - (socio-demographic information, e.g., subject’s “handedness” or “parent’s education level”, emotions (“Strength and Difficulties Questionnaire”), and parenting information (“Alabama Parenting Questionnaire”).)

- TRAINING_SOLUTIONS.xlsx  - (the targets (ADHD diagnosis and sex))

- TEST_CATEGORICAL.xlsx - (socio-demographic, emotions, and parenting information)

- TEST_FUNCTIONAL_CONNECTOME_MATRICES.csv - (functional MRI connectome matrices)

- TEST_QUANTITATIVE_METADATA.xlsx - (socio-demographic, emotions, and parenting information)

Describe your data exploration and preprocessing approaches:
- We focused on exploring the data and finding missing values.
- We scaled the values so that they can be in closer range to each other. This is because we had various different ranges of data for each field.
- 


Include at least 2-3 visualizations from your Exploratory Data Analysis:

<img width="417" alt="Screenshot 2025-03-22 at 10 56 53 AM" src="https://github.com/user-attachments/assets/c8a5ed78-cfd8-4015-b94e-38a12527b79d" />

<img width="655" alt="Screenshot 2025-03-22 at 10 57 08 AM" src="https://github.com/user-attachments/assets/a31f1c83-dcca-443d-afa9-9a8d914aa648" />

<img width="655" alt="Screenshot 2025-03-22 at 10 57 21 AM" src="https://github.com/user-attachments/assets/246e00c1-ff76-4a1e-926d-cd9db81dce18" />

<img width="655" alt="Screenshot 2025-03-22 at 10 57 31 AM" src="https://github.com/user-attachments/assets/03c0ab5b-5e3e-445f-b47d-390d471ce21b" />


# Implementation
Data cleaning and Feature Engineering.
We used a Random Forest model at first. Then to improve the resutls we built a GNN model.

# Results
We achieved a score of 

