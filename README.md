# Abstract
This study tackles the problem of classifying breast tumors as malignant (M) or benign (B) using data mining approach. The dataset used in this research comprises variables retrieved from breast biopsy samples. Principal component analysis (PCA) is used in my methodology to reduce dimensionality, while support vector machine (SVM) and logistic regression models are used for classification. We explore two scenarios: one with seven principal components and another with fifteen principal components. High accuracies ranging from 97.37% to 98.25%, are revealed by key findings, indicating how well the suggested method separates benign from malignant tumors. The models including fifteen principal components perform marginally better, demonstrating the importance of feature selection in improving predictive power. This work advances the categorization of breast cancer by demonstrating the value of PCA and supervised learning techniques in medical diagnostics.

# Dataset
The Breast Cancer Wisconsin (Diagnostic) dataset is a well-known dataset in the field of machine learning, particularly for classification tasks related to the diagnosis of breast cancer. 
Here are some key details about the dataset:
Dataset Information: Source: UCI Machine Learning Repository Donation Date: 10/31/1995 Subject Area: Health and Medicine Associated Tasks: Classification Feature Type: Real Number of Instances: 569 Number of Features: 30 Features: ID: Categorical (identification number) Diagnosis: Target variable (Malignant - M, Benign - B) 3-32. Features 1-30: Various real-valued features computed from digitized images of fine needle aspirates (FNA) of breast masses. These features describe characteristics of cell nuclei present in the images. Additional Information: Missing Values: No Feature Details: The features include measures related to radius, texture, perimeter, area, smoothness, compactness, concavity, concave points, symmetry, and fractal dimension. Features are computed for each cell nucleus, and there are ten real-valued features for each nucleus. Variable Information: ID Number: Categorical Diagnosis: Target variable (Malignant or Benign) 3-32. Features 1-30: Various continuous features representing different characteristics of cell nuclei.
Dataset is publicly available “UCI Machine Learning Repository,” archive.ics.uci.edu. https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic 

# Data Exploration
To comprehend the properties of the dataset and acquire insights into its features, data exploration is an essential first step. This crucial phase involved several steps aimed at identifying patterns and potential problems in the data.

![image](https://github.com/user-attachments/assets/fb0966c8-313b-4496-a4bb-fe258cac2c59)

# Data Pre-processing 
The following were performed on the dataset in preparation for modelling. First was normalization. I applied Min-Max scaler for normalization of all features. The values of each feature are transformed to a range of values between and 0 and 1. This ensures consistency in the scale of all features as inconsistent scale could produce biased models. Each feature contributes equally to learning, and enhancing the general effectiveness of machine learning models. 
The normalized dataset is split into train and test using an 80:20 split. This resulted in 455 observations for training and 113 for testing. After the split, we then proceed to apply Synthetic Minority Over-sampling Technique (SMOTE) on the train data. This brought the target class to equal proportion of 286 Benign and 286 Malignant. Smote is a sampling technique that combines over-sampling of the minority class and under sampling of the majority class to address imbalance. 
Principal Component Analysis (PCA) is applied on the test and train data. PCA is a feature selection method that chooses a collection of features from a dataset that are more valuable than all of the features combined. PCA chooses the best features based on the dataset’s covariance matrix. When dealing high dimensional data, and data that posses’ linear relationships, PCA helps to overcome the curse of dimensionality.  
In this research, we compared different number of principal components to get the optimal number of PC’s. Using a scree plot, we were able to visualize the cumulative explained variance for each principal component and identify the point where more principal components do not increase the explained variance significantly. 

![image](https://github.com/user-attachments/assets/8aea5f54-6da8-4214-8bca-33f87cb0394d)
![image](https://github.com/user-attachments/assets/f521644c-5103-4e2c-bb81-28900a6b14eb)

# Modelling 
In this research, two classification models were tested on the breast cancer dataset: Logistic Regression and Support Vector Machine. (SVM). These machine learning techniques have been chosen because of their history of performance in medical research. 

# Results
Model performance using 7 principal components

![image](https://github.com/user-attachments/assets/ecafbdcd-3fef-42c2-97a8-b37ae436cf01)
![image](https://github.com/user-attachments/assets/87aec743-8fcd-4b41-8c8c-4aee51602184)

Model Performance using 15 principal components:

![image](https://github.com/user-attachments/assets/9289ac3c-2a5c-40d7-abea-0d3a136ff1b3)
![image](https://github.com/user-attachments/assets/daeb4d4e-a71d-423d-92de-7421b25e29cf)

# CONCLUSION & Recommendation
The utilisation of principal component analysis for dimensionality reduction greatly enhances the precision and effectiveness of breast cancer diagnosis. The study emphasises the potential of sophisticated machine learning models in supporting diagnostic procedures and offers insightful information for researchers and medical professionals. 

As the false negative count did not reduce, it appears the model has difficulty in completely identifying cases of the positive class which is malignant. For future work, domain experts should be consulted to gain insights into the reasons behind false negatives. Also, more classification algorithms like Decision tree, random forest and K nearest neighbour can be experimented with different number of principal components
