# Project Title:
Feed Forward Neural Networks Clasiffication Model on Heart Dataset
#
---
# Project Description:
Binary classification with Feed Forward Neural Networks for predicting chances of stroke using parameters like: gender, age, heart disease, glucose level, bmi, smoking status etc. 
#
---
# Table of Contents:

  1. Exploratory data analysis
  2. Data Preprocessing 
  3. Model Training
  4. Model Hyperparameter Optimization
  5. Model Evaluation
  6. Conclusion and Results
---
#

---
# Dataset:
![image](https://github.com/VesnaPop-Dimitrijoska/FFNN_Clasiffication_Model_HeartData/assets/144008804/2232c394-ef02-4753-a194-54e7a19a28b4)
---

---
# Preliminary analysis of a dataset:
---
### Shape of a Dataset:     
Shape of the dataset is: 5110 rows x 11 columns (without index column).

### NaN values:  
There are 201 rows with NaN values in 'bmi' feature that should be imputed. I think that preferred method will be to impute them with Linear Regression. 

### Constant values:  
There are no constant value columns.  

### Non-informative and semantic irrelevant features
There are not such columns in the dataset. 

### Data types:  
Data types are correct but they should be converted in more efficient data types with smaller precision.  

### Duplicates:  
There are no duplicate rows in the dataset.

### Typos:       
There are no typos that need to be corrected.

### Descriptive statistics:
The summary statistics is showing that data are on a similar scale. 

#
---
# CONCLUSION from EDA:
## 

## Target Class - Univariate analysis
Target class is the 'stroke' column. It has two values 0 and 1, therefore this is BINARY CLASSIFICATION problem.
The class is highly unbalanced, so few methods and techiques will be applied to address this issue as well as using stratification when splitting the data.

## Key findings from Heatmap:
Heatmap shows high positive correlation between the following features: 'ever_married' and 'age'.
At this point I decided to leave them in the dataset.   

## Key findings from Histplots:  
Some of the features have similar to normal distribution and some are highly unbalanced. At this point I decided not to transform the features, but later on in some of the experiments I'm applying SMOTE oversampling method for for balancing data.

## Key findings from Boxplots:
Box plots shows few outliers in some of the features. At this point I decided to leave them in the dataset.

## Key findings from Pairplot:
2D Pairwise relationships between variables in a dataset shows that a positive target class (the minority class) is associated with higher values in the features: 'age', 'average glucose level', 'bmi', 'hypertension' and 'hearth disease'. 

---
# RESULTS

![image](https://github.com/VesnaPop-Dimitrijoska/FFNN_Clasiffication_Model_HeartData/assets/144008804/9bbc03dc-4e9d-4d37-93ce-792602ef4eb9)      
Overall, our model faces challenges with its performance due to the significant class imbalance. This disproportionately impacts the accuracy of predictions for the underrepresented class. Therefore few other experiments were done in order to maximize the performance.

---
## Experimentation with different threshold  
![image](https://github.com/VesnaPop-Dimitrijoska/FFNN_Clasiffication_Model_HeartData/assets/144008804/1d24e502-1cab-4d4e-9494-e6541322563a)     
A slight improvement is observed when reducing the threshold. However, it is important to note that this improvement comes at the cost of a slight increase in both False Negatives and False Positives within our Confusion Matrix.

---
## SMOTE V1
![image](https://github.com/VesnaPop-Dimitrijoska/FFNN_Clasiffication_Model_HeartData/assets/144008804/45742fd5-9741-421e-be38-d1dd44687399)      
Significant improvment was made using the SMOTE technique for  balancing the class distribution in a dataset. SMOTE generates synthetic samples in order to balance the classes, which can lead to better performance of a machine learning model, especially in cases where the minority class is important.

---
## SMOTE V2
![image](https://github.com/VesnaPop-Dimitrijoska/FFNN_Clasiffication_Model_HeartData/assets/144008804/f71333de-6102-472a-8da7-64c1dc9ac17e)     
Significant improvment was made using SMOTE + Random UnderSample for balancing the class distribution in a dataset. However Random UnderSampler may lead to a loss of information, especially if it discards important samples from the majority class.

---
## SMOTE V3
![image](https://github.com/VesnaPop-Dimitrijoska/FFNN_Clasiffication_Model_HeartData/assets/144008804/b34018fc-d099-4f20-b518-ebeb641f655b)     
Significant improvment was made using SMOTE + Random UnderSample for balancing the class distribution in a dataset. However Random UnderSampler may lead to a loss of information, especially if it discards important samples from the majority class.

---
#
# License
MIT License
#
