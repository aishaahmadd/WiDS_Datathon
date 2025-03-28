# WiDS_Datathon
## **👥 Team Members** 
- Ana Sordo (https://github.com/megaDeathChav)
- Gianelli Lagos (https://github.com/GianelliL)
- Fatima Mora Garcia (https://github.com/fmora22)
- Aisha Ahmad (https://github.com/aishaahmadd)
  
## **🎯 Project Highlights**
## **👩🏽‍💻 Setup & Execution**


### Local Copy
#### Clone the Repository
    git clone https://github.com/aishaahmadd/WiDS_Datathon.git
    cd WiDS_Datathon
Using Kaggle command:


    kaggle competitions download -c widsdatathon2025
Feel free to use the kaggle Interface here: https://www.kaggle.com/competitions/widsdatathon2025


- Click the blue plus sign in the lefthand navigation pane
- Click “New Notebook” 
- Upload file version “Sequential Neural Network” from gtihub repo
- Run all cells

## **🏗️ Project Overview**
Using fMRI data, we built a model to predict both an individual’s sex and their ADHD diagnosis.

In this year’s WiDS Datathon, participants were tasked with building a model to predict both an individual’s sex and their ADHD diagnosis using functional brain imaging data of children and adolescents and their socio-demographic, emotions, and parenting information. 

This relates to the Break Through Tech AI program since we have learned how to do regression model selection, regression model fitting/testing, data cleaning, and preprocessing for model development and analysis. Break Through Tech has taught us the building blocks needed to be successful in this kaggle competition. The Break Through Tech AI program has also given us the opportunity to participate in this kaggle competition with team members that are also part of the program. 

Tools of this nature can help identify individuals who may be at risk of ADHD, which can be difficult to diagnose particularly in females. Importantly, they help shed light on the parts of the brain relevant to ADHD in females and males, which in turn could lead to improvements in personalized medicine and therapies. Identifying ADHD early and designing therapies targeting specific brain mechanisms in a personalized way can greatly improve the mental health of affected individuals.

## **📊 Data Exploration**
Our dataset includes diagnostic, socio-demographic, emotions, and parenting data, and functional MRI data from the Healthy Brain Network (HBN) — the signature scientific initiative of the Child Mind Institute. For data preprocessing, we created frequency plots to understand the data distribution. We also evaluated the feature correlations with Sex_F. The main challenges we faced in this step was when handling the connectome data, since it's a large dataset.


Visualizations from our Exploratory Data Analysis:

<img width="417" alt="Screenshot 2025-03-22 at 10 56 53 AM" src="https://github.com/user-attachments/assets/c8a5ed78-cfd8-4015-b94e-38a12527b79d" />

<img width="655" alt="Screenshot 2025-03-22 at 10 57 08 AM" src="https://github.com/user-attachments/assets/a31f1c83-dcca-443d-afa9-9a8d914aa648" />

<img width="655" alt="Screenshot 2025-03-22 at 10 57 21 AM" src="https://github.com/user-attachments/assets/246e00c1-ff76-4a1e-926d-cd9db81dce18" />

<img width="655" alt="Screenshot 2025-03-22 at 10 57 31 AM" src="https://github.com/user-attachments/assets/03c0ab5b-5e3e-445f-b47d-390d471ce21b" />

## **🧠 Model Development/Implementation**

We decided to use a Multi-Layer Perceptron (MLP) neural network with 2 outputs, one for sex and one for ADHD Outcome. We selected this model due to its compatibility for multi-output binary classification problems, since we are predicting both ADHD outcome and Sex_F. An initial learning rate of 0.001 was set using the Adam optimizer, which performs well without manual adjustments. We used a batch size of 32 to balance computational efficiency and model complexity. Our training approach was to utilize the Adam optimizer for the learning rate, use Binary Cross-Entropy loss to minimize the difference between predicted and actual probabilities for both ADHD and Sex_F outcomes, and use Binary Accuracy as the primary evaluation metric. The predictions were obtained by converting probabilities to binary class predictions using a 0.5 threshold.

## **📈 Results & Key Findings**

### **Initial Model: Random Forest**
At the start, we implemented two separate Random Forest (RF) models: one for ADHD prediction and another for Sex classification. This approach allowed us to assess the effectiveness of tree-based methods for both tasks before committing to a more complex model.

#### **ADHD Model Performance**
- **Accuracy:** 80.59%  
- **F1-Score:** 86.68%  
- **Precision & Recall Breakdown:**
  - **Class 0 (No ADHD):** 69% precision, 60% recall, 64% F1-score
  - **Class 1 (ADHD):** 85% precision, 89% recall, 87% F1-score

#### **Sex Model Performance**
- **Accuracy:** 61.84%  
- **F1-Score:** 29.26%  
- **Precision & Recall Breakdown:**
  - **Class 0 (Male):** 65% precision, 85% recall, 74% F1-score
  - **Class 1 (Female):** 45% precision, 22% recall, 29% F1-score

While the ADHD model performed well, the Sex classification model struggled, likely due to class imbalance and a limited number of distinguishing features.

### **Final Model: Sequential Neural Network (MLP)**
After evaluating the RF results, we transitioned to a Multilayer Perceptron (MLP) model to improve predictive performance. Unlike RF, which lacks scalability for high-dimensional data, MLP allowed us to capture more complex relationships in the dataset.

- **Accuracy:** 94%  
- **Precision:** 94%  
- **Recall:** 88%

Despite this improvement, our actual Kaggle leaderboard score was approximately 0.59, suggesting that the model may have overfit the training data or that there were distributional differences between the training and test sets.

By consolidating ADHD and Sex classification into a single MLP model, we streamlined the training pipeline while leveraging the same feature set for both predictions. However, further improvements in feature selection and regularization would be necessary to bridge the gap between validation and leaderboard performance.


## **🖼️ Impact Narrative**
**WiDS challenge:**

1. What brain activity patterns are associated with ADHD; are they different between males and females, and, if so, how?
  - we believe that in the connectome data “0throw_103thcolumn” is highly correlated with ADHD. As well as “0throw_102thcolumn”, “1throw_149thcolumn”, “0throw_156thcolumn” and more. 
- We think that these columns in the other data:
    ["APQ_P_APQ_P_INV",
    "APQ_P_APQ_P_OPD",
    "SDQ_SDQ_Hyperactivity",
    "SDQ_SDQ_Externalizing",
    "SDQ_SDQ_Emotional_Problems",
    "SDQ_SDQ_Difficulties_Total"] is the most correlated to adhd. 
We were only given female data.
3. How could your work help contribute to ADHD research and/or clinical care?
  - Tools of this nature can help identify individuals who may be at risk of ADHD, which can be difficult to diagnose particularly in females. Importantly, they help shed light on the parts of the brain relevant to ADHD in females and males, which in turn could lead to improvements in personalized medicine and therapies. Identifying ADHD early and designing therapies targeting specific brain mechanisms in a personalized way can greatly improve the mental health of affected individuals.

## 🚀 Next Steps & Future Improvements

### Limitations of the Model
- While our MLP model achieved strong results (94% accuracy, 94% precision, and 88% recall), it lacks interpretability compared to Random Forest (RF), making it difficult to analyze feature importance.
- Our attempt to improve performance using Leaky ReLU and Batch Normalization led to a drop in validation accuracy from 94% to ~79%, suggesting potential over-normalization or added complexity.
- Due to time constraints, we did not explore feature selection techniques such as Recursive Feature Elimination (RFE) or SHAP, which could have refined the input features.

### What We Would Do Differently
- Our initial pipeline transitioned from RF to GNN, but we faced data format issues with the connectome (brain) data, particularly in converting 397-length connectivity vectors into valid adjacency matrices. This resulted in two weeks of debugging without significant progress.
- A more structured approach—RF to MLP to GCN to GNN—would have allowed us to incrementally assess performance trade-offs rather than getting stuck on GNN early.
- More extensive hyperparameter tuning (e.g., adjusting learning rates, dropout rates) could have further optimized MLP performance.

### Additional Datasets & Techniques to Explore
- **Ensemble Learning:** Combining RF, MLP, and XGBoost could improve model robustness.
- **Graph Neural Networks (GNNs)**: If time allowed, refining graph construction from connectome data and testing models like GraphSAGE or GAT could enhance learning.
- **Feature Engineering** Applying dimensionality reduction techniques like PCA or Autoencoders could improve performance by mitigating high-dimensional connectome data challenges to our final model.

Despite the challenges, our best MLP model (94% accuracy, 94% precision, 88% recall) provided a strong predictive baseline. However, our accuracy in the competition was approximately 0.59, indicating potential overfitting to the training data or a domain shift in the test set. With additional time, feature selection, ensemble methods, and a structured model progression could further optimize performance.



## **📄 References & Additional Resources**  

- [Understanding MLPs and Neural Networks](https://www.youtube.com/watch?si=u1q_45MKaRzue70d&v=OkE3776GfWU&feature=youtu.be)  
- [Graph Neural Networks (GNNs) Explained](https://www.youtube.com/watch?si=Q0FuLhRJAHxqRcPx&v=vtHBOBOcn6E&feature=youtu.be)  
- [Feature Selection Techniques for Machine Learning](https://youtu.be/jbIsfVxuMWM?si=BRxueH_vuGFBtTcd)  
- [Ensemble Methods in Machine Learning](https://www.youtube.com/watch?si=4n6Ghe9Eoh5lO1eL&v=jbIsfVxuMWM&feature=youtu.be)  





