# Enhancing Dementia Diagnosis with Machine Learning

## Project Overview
This research project, completed as part of the **Blackwell Summer Scholars Program**, explores how machine learning can be applied to improve the early detection and diagnosis of dementia and Alzheimer’s disease. Using MRI image datasets and observational patient data, the study combined **custom convolutional neural networks (CNNs)** with traditional statistical methods to evaluate predictive accuracy and significance.

The primary research question:  
**How can machine learning algorithms improve the early detection and diagnosis of dementia, and what impact does this have on patient outcomes?**

## Background and Motivation
- Dementia and Alzheimer’s disease significantly reduce quality of life.  
- Early detection allows for lifestyle changes and treatments that can delay severe symptoms.  
- Socioeconomic status, education level, and gender are strongly associated with dementia incidence.  
- The project aimed to support **nationwide scalability**, development of new treatments, and **decision support for medical professionals**.

## Dataset
- **Source**: [Kaggle Alzheimer’s MRI Dataset (4-class images)](https://www.kaggle.com/datasets/tourist55/alzheimers-dataset-4-class-of-images/data)  
- **Types**:  
  - **Cross-sectional dataset**: snapshot of patients at one point in time.  
  - **Longitudinal dataset**: multiple observations over time to track progression.  
- **Classes**:  
  - Mild Demented  
  - Moderate Demented  
  - Non Demented  
  - Very Mild Demented  

Additional patient features (for regression and classification):  
- MMSE (Mini-Mental State Examination)  
- nWBV (Normalized Whole Brain Volume)  
- ASF (Atlas Scaling Factor)  
- SES (Socioeconomic Status)  
- Education Level  

## Methods
### Observational Models
- **Logistic Regression**:  
  - Dependent variable: Demented (1) vs. Non-Demented (0)  
  - Independent variables: MMSE, nWBV, ASF, SES  
  - Evaluated with Accuracy, Precision, Recall, F1-score, Confusion Matrix  

- **K-Nearest Neighbor (KNN)**:  
  - Included MMSE, nWBV, ASF, Education Level  
  - Evaluated with Accuracy, Precision, Recall, F1-score, Confusion Matrix  

### Experimental Models
- **Custom Convolutional Neural Network (CNN)**:  
  - Architecture: 3 convolutional blocks + global average pooling  
  - Training: EarlyStopping, custom learning rate scheduler  
  - Metrics: Precision, Recall, BinaryAccuracy  
  - Evaluation: Classification reports and confusion matrices for each class  

## Results
### Logistic Regression
- Accuracy: **86.5%**  
- Best predictors: MMSE, nWBV, ASF  
- Class-level results: Demented class recall = 0.77, F1 = 0.82  

### KNN
- Accuracy: **87.5%**  
- High precision for Demented class (0.95), recall = 0.74  
- Non-demented class recall = 0.97  

### CNN
- Validation Accuracy: **74.8%**  
- Test Accuracy: **74.0%**  
- Class-level performance:  
  - NonDemented: Precision = 0.49, Recall = 0.47  
  - VeryMildDemented: Precision = 0.34, Recall = 0.35  
  - MildDemented: Precision = 0.17, Recall = 0.18  
  - ModerateDemented: Precision = 0.00 (class imbalance issue)  

## Key Findings
- **Best diagnostic predictors**: MMSE, nWBV, ASF.  
- **Dataset balance is critical**: Moderate Demented class performed poorly due to small sample size.  
- **CNNs show potential** for classifying dementia stages but require advanced architectures (e.g., ResNet, VGG16) and balanced datasets.  
- **Cross-sectional and longitudinal data alone are insufficient** — MRI imaging combined with ML provides better accuracy.  

## Research Significance
- Enables **early detection** for timely intervention.  
- Identifies **biomarkers and risk factors** from MRI data.  
- Supports integration with healthcare technologies such as **EHR systems** and telemedicine platforms.  
- Lays groundwork for **personalized treatment planning**.  

## Future Work
- Implement advanced CNNs such as **ResNet-101** or **VGG16** for improved accuracy.  
- Apply **Random Forest Classifier** to capture deeper dementia symptoms.  
- Correct for **class imbalance** by adjusting weights or augmenting data.  
- Investigate socioeconomic and educational impacts further.  

## Tools and Technologies
- **Languages**: Python, R  
- **Libraries**: TensorFlow/Keras, scikit-learn, Pandas, NumPy, Matplotlib, Seaborn  
- **Techniques**: Logistic Regression, KNN, CNNs, Correlation Analysis, Confusion Matrices  

## Author
**Trustan Gabriel Price**  
B.S. in Statistics, University of Illinois Urbana-Champaign  
Blackwell Summer Scholars Program (2024)  
