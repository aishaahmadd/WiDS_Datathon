# WiDS_Datathon
## **👥 Team Members** 
- Ana Sordo (https://github.com/megaDeathChav)
- Gianelli Lagos (https://github.com/GianelliL)
- Fatima Mora Garcia (https://github.com/fmora22)
- Aisha Ahmad (https://github.com/aishaahmadd)
  
## **🎯 Project Highlights**
## **👩🏽‍💻 Setup & Execution**

## **🏗️ Project Overview**
Using fMRI data, we built a model to predict both an individual’s sex and their ADHD diagnosis.

In this year’s WiDS Datathon, participants were tasked with building a model to predict both an individual’s sex and their ADHD diagnosis using functional brain imaging data of children and adolescents and their socio-demographic, emotions, and parenting information. 

This relates to the Break Through Tech AI program since we have learned how to do regression model selection, regression model fitting/testing, data cleaning, and preprocessing for model development and analysis. Break Through Tech has taught us the building blocks needed to be successful in this kaggle competition. The Break Through Tech AI program has also given us the opportunity to participate in this kaggle competition with team members that are also part of the program. 

Tools of this nature can help identify individuals who may be at risk of ADHD, which can be difficult to diagnose particularly in females. Importantly, they help shed light on the parts of the brain relevant to ADHD in females and males, which in turn could lead to improvements in personalized medicine and therapies. Identifying ADHD early and designing therapies targeting specific brain mechanisms in a personalized way can greatly improve the mental health of affected individuals.

## **Data Exploration**
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

## **🧠 Model Development/Implementation**
1. Data Cleaning and Feature Engineering

Initial preprocessing involved cleaning the dataset and selecting relevant features. 

Feature engineering techniques were applied to enhance data representation.

2. Baseline Model: Random Forest

A Random Forest model was trained as the initial baseline.

The model was evaluated using accuracy and F1-score.

While it provided decent results, improvements were sought through deep learning techniques.

3. Transition to Graph Neural Networks (GNN)

To improve classification performance, a GNN model was implemented using PyTorch Geometric.

The connectivity matrix was converted into a graph representation where nodes represented brain regions and edges reflected connectivity strengths.

Graph objects (data_list) were created for training the model.

4. GNN Model Training and Evaluation

A GNN was trained to predict ADHD outcomes and other classifications.

Performance metrics such as accuracy and F1-score were computed.

The results were compared with the Random Forest classifier to assess improvements.

## **📈 Results & Key Findings**
In our first Kaggle submission we used a RandomForest model and achieved a score of:
In our second Kaggle submission we used a Sequential Nueral Network model and achieved a score of:


## **🖼️ Impact Narrative**
**WiDS challenge:**

1. What brain activity patterns are associated with ADHD; are they different between males and females, and, if so, how?
2. How could your work help contribute to ADHD research and/or clinical care?
Tools of this nature can help identify individuals who may be at risk of ADHD, which can be difficult to diagnose particularly in females. Importantly, they help shed light on the parts of the brain relevant to ADHD in females and males, which in turn could lead to improvements in personalized medicine and therapies. Identifying ADHD early and designing therapies targeting specific brain mechanisms in a personalized way can greatly improve the mental health of affected individuals.

## **Next Steps and Future Improvements**
* What are some of the limitations of your model?
* What would you do differently with more time/resources?
* What additional datasets or techniques would you explore?

## **📄 References & Additional Resources**



