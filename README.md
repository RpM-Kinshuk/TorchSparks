# TorchSparks
Jupyter Notebook containing code for analysis and visualization of transactional data and chosen algorithms for the proposed **Ensemble**.

![WhatsApp Image 2024-03-17 at 16 23 00_55055858](https://github.com/RpM-Kinshuk/TorchSparks/assets/103813028/0861fd5c-e9fd-4311-9436-8f37824eaec0)

## Overview of anomaly detection algorithms on transaction dataset:

* Multivariate Gaussian probability, Auto Encoders, Local Outlier Factor LOF, Robust Covariance (Elliptic Envelope), Isolation Forest

* Anomaly detection systems should NOT prefer supervised ML algorithms as they're highly reliant on labelled training data.
* As the data is very skewed - there are **only 0.17%** fraudulent transactions in the 280k samples -  accuracy is not a good metric: any "model" predicting ALL are normal transactions will have a 99.83% accuracy. 
* Hence, we need to use Recall, Precision and thus their combination, the **F1 score**.
* The models below do not take into account the time sequences for redundancy.
* The training set does NOT include any Fraud, so when the model is exposed to one in Test, it will stand out from the normal transactions. We divided the Frauds into a Validation and Test subsets - F1 score being lower.
* PCA was used only for visualization. PCA is a necessary component of data preprocessing as F1 score turns out very low without it.

* And thus comparison has been drawn between the following on F1 score on **Test**:


### **Multivariate Gaussian prob distribution F1= 0.71** optimizing Epsilon 

### **Auto-encoders F1= 0.53** optimizing Reconstruction Error

### **LOF Local Outlier Factor F1= 0.57** optimizing number of neighbors

### **Robust Covariance (Elliptic Envelope) *F1= 0.80*** optimizing support fraction

### **Isolation Forest F1= 0.47** optimizing num estimators
