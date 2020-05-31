
##  Executive Summary for Project4: West Nile Virus Kaggle Challenge

_Author: Jamie, Peggy, Russell, Sheng Jun, DSI 14_

---

### Introduction 

This README file provides the executive summary and insights, and recommendations pertaining to the strategy on deploying pesticides :skull: to effectively 1) control the mosquito population and prevent 2) outbreaks of West Nile Virus in Windy City. 

---

**Jupyter Notebook Organization**

The notebooks are located in folder 'assets' -> 'working'

Notebooks are arranged via following system: *1st digit . 2 digit . 3 digit*

- 1st digit: Project number

- 2nd digit: 

  - **Data Cleaning, EDA, Feature Engineering** and **save to csv file** : **0** , 
  - **Machine Learning model building** : **1**

- 3rd digit:  

  - **First** notebook: **1** 
- **Second** notebook : **2**, and so on.
  
  For example,
  
  - notebook 4.0.1 represents the first note book on Project 4, data cleaning, eda, etc.
  - notebook 4.1.1 represents the first notebook on Project 4, Machine learning model building

---

### Executive Summary
**<u>Context.</u>** Due to the recent epidemic of West Nile Virus in the Windy City :office:, the Department of Public Health has set up a surveillance and control system. The team at the Disease And Treatment Agency, division of Societal Cures In Epidemiology and New Creative Engineering (DATA-SCIENCE), will apply Data Science methods and techniques to uncover insights for recommendations on effective deployment of pesticides throughout the city.

**<u>Problem Statement.</u>** West Nile virus (WNV) is the leading cause of mosquito-borne disease in the United States. Approx. 1 out of 150 infected people develop a serious complications that may be fatal. There are no vaccines :syringe: ​to prevent nor medications :pill: to treat WNV in people. Pesticides can control mosquito population, but carries with it high costs and potential ecological impacts. Therefore, "just-in-time spraying" approach is proposed to keep mosquito population in check. Using the data collected from the Department of Public Health's mosquito population S&C (Surveillance and Control) system,  the DATA-SCIENCE team seeks to enhance the pesticide deployment plan through Machine Learning.  

**<u>Proposed Solution.</u>** The team decided to utilize exploratory data analysis (EDA) on spatial and time-series data to uncover potential trends :bar_chart: that could provide actionable insights towards the where :pushpin:, and when :clock12: to deploy pesticide for maximum effect:dart:.​ The team would also explore the development of classifier models to help forecast clusters of WNV for preemptive deployment of pesticides.

**<u>Findings.</u>**

Our investigation into the data collected reveals that:
- Mosquito trapped decreased between 2007 and 2009, due to the decreased number of traps deployed in 2009 and onwards.
- Spraying has some effect in decreasing mosquito quantity (between 2009 & 2011) captured in traps. We could infer that spraying in general, has an effect in controlling the general mosquito population. 

- The spike in mosquitos trapped and by extension, wnv instances is not due to
 - increased trap quantity
 - change in trap locations
 - increased collection from traps

The increase in mosquito quantity is due to
 - heavy rainfall from mid-June to mid-Jul, supported by relatively high temperatures (average) and windspeeds (less than 10mph).
 - No spraying in months prior to Jul.

We also note the spraying in 2013 has missed areas of traps with high wnv (more than 100). 

On the building of classifier models, several were explored and their performance measures were reported below:

| Metrics                 | LogReg | SVM   | KNN   | DecisionTree | RandForest* | GradientBoost | XGB   |
| ----------------------- | ------ | ----- | ----- | ------------ | ----------- | ------------- | ----- |
| **accuracy (validate)** | 0.945  | 0.918 | 0.934 | 0.814        | 0.852       | 0.909         | 0.906 |
| **sensitivity**         | 0      | 0.226 | 0.066 | 0.65         | 0.524       | 0.226         | 0.241 |
| **precision**           | 0      | 0.226 | 0.173 | 0.171        | 0.2         | 0.196         | 0.193 |
| **F1**                  | NaN    | 0.226 | 0.095 | 0.271        | 0.29        | 0.21          | 0.214 |
| **roc_auc**             | 0.791  | 0.795 | 0.721 | 0.804        | 0.698       | 0.847         | 0.848 |

*RandForest (undersampling + oversampling), other models (oversampling)

As the proportion of wnv  to none wnv is approx. 5%-95%, this is an imbalanced class problem. The team utilized resampling techniques (SMOTE) to mitigate imbalanced class for machine learning. F1 score and ROC_AUC are used to evaluate the best model. The team picked the XXX model as the production model.

**<u>Recommendations and Way Forward.</u>**

Pesticide deployment: To improve cost-effectiveness of pesticide deployment, the proposed recommendations relies on timing and coverage area:

1. Spraying should be focused in the months of Jun to Jul (periods of high rainfall), and targeted at region of traps (see presentation slides) with high wnv as a start.

2. Moving forwards, the deployment should be tailored accordingly to match rainfall patterns; mosquito population generally spike 2 weeks after heavy rainfall.

3. The classifier model could be used to provide insights to areas for targeted spraying in the longer term, as new data on wnv clusters, and weather data is available.

   

---

