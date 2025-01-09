# Customer-Segmentation-Lead-Scoring-System-for-Predicting-Lead-Conversion-Using-Logistic-Regression

## Project Overview:

An Education institution, an online platform providing courses to industry professionals, is experiencing low lead conversion rates. Despite generating a large number of leads, only a small fraction are converted into paying customers. The company wishes to identify potential leads with a higher likelihood of conversion in order to optimize the sales process. In response to this need, a logistic regression model was developed to assign a "lead score" to each lead based on their likelihood of conversion. This scoring system helps the sales team focus on the most promising leads, enhancing overall sales efficiency and increasing the conversion rate.

## Problem Statement:
X Education faces a typical lead conversion funnel where a large number of leads are generated, but only a small percentage convert into paying customers. Currently, the company has a conversion rate of approximately 30%, which could be improved by prioritizing leads that are more likely to convert. To solve this, a predictive model was required that can score leads based on their probability of conversion, allowing the sales team to focus on the most promising leads (also called "Hot Leads").

## Business Objective:
The primary goal was to build a model that predicts which leads are more likely to convert into paying customers. The model needed to generate a lead score between 0 and 100, where a higher score indicates a greater likelihood of conversion. By targeting leads with higher scores, X Education can focus their resources on more valuable leads, thereby increasing their conversion rate. The company's CEO set an ambitious target of achieving an 80% conversion rate using this lead scoring system.

## Data Description:
The dataset provided by X Education consists of approximately 9,000 records of past leads with various attributes, including:

- **Lead Source:** The source through which the lead was acquired (e.g., Google, Referral).
- **Total Time Spent on Website:** The amount of time the lead spent browsing the website.
- **Total Visits:** The total number of times the lead visited the website.
- **Last Activity:** The last activity performed by the lead on the website.
- **Converted:** The target variable, indicating whether the lead was converted (1) or not (0).
- 
Additionally, the dataset contains categorical variables, some of which need to be handled appropriately (e.g., "Select" levels treated as null values).

## Key Challenges:
**Handling Missing Values:**
- Some categorical variables contain a 'Select' level, which acts as a placeholder for missing values and needs to be treated appropriately.

**Feature Selection:** 
- Identifying which features are most important for predicting lead conversion.
  
**Imbalanced Dataset:**
- The dataset contains more non-converted leads than converted leads, which could cause the model to be biased towards predicting "no conversion."
- Techniques like oversampling or undersampling were considered to handle this imbalance.
  
## Solution Approach:
**1. Data Preprocessing:**

- **Handling Missing Data:** Categorical variables with the 'Select' level were identified and treated as null values. These values were either imputed with the most frequent category or dropped based on their significance.
- **One-Hot Encoding:** Categorical variables were encoded into numeric features using One-Hot Encoding to ensure compatibility with machine learning models.
- **Feature Scaling:** Numerical features such as "Total Time Spent on Website" and "Total Visits" were scaled using StandardScaler to standardize the data and avoid the model being biased towards variables with higher numerical values.
- 
**2. Feature Engineering:**
  
- **Correlation Analysis:** The correlation between numerical features and the target variable was analyzed using Pearson’s correlation coefficient to identify the most influential features.
- **Interaction Terms:** Additional features were created by combining variables (e.g., the product of "Total Time Spent on Website" and "Total Visits") to capture potential relationships between features.
  
**3. Model Building:**

- **Logistic Regression:** A logistic regression model was selected due to its effectiveness in binary classification problems, where the target variable is a binary outcome (converted or not converted).
- **Model Evaluation:** The model was evaluated using several metrics:
- **Accuracy:** To check the overall performance.
- **AUC-ROC Curve:** To evaluate the model's ability to distinguish between converted and non-converted leads.
- **Confusion Matrix:** To analyze the model’s classification performance by examining false positives and false negatives.
- **Lead Scoring:** The model’s output probability was scaled between 0 and 100 to generate a lead score. The higher the score, the higher the likelihood of conversion.
  
**4. Results and Model Performance:**
- **Model Accuracy:** The logistic regression model achieved an accuracy of approximately 80%, meeting the CEO’s target lead conversion rate.
- **Lead Scoring:** Leads were assigned scores between 0 and 100, with higher scores indicating a higher chance of conversion. These scores were used by the sales team to prioritize leads.
- **Business Impact:** By focusing on high-scoring leads, X Education was able to allocate its sales resources more effectively, leading to higher conversion rates.
  
**5. Evaluation and Adjustments:**
- **Fine-tuning the Model:** After the initial implementation, the model was fine-tuned by adjusting hyperparameters such as the regularization parameter in logistic regression to optimize performance.
- **Handling Imbalanced Data:** Techniques such as SMOTE (Synthetic Minority Over-sampling Technique) were explored to balance the classes in the training dataset, improving model performance for the minority class (converted leads).
  
## Technologies and Tools Used:
**Programming Language:** Python

**Libraries:** pandas, numpy, scikit-learn, matplotlib, seaborn

**Techniques:**

- Logistic Regression for binary classification
- One-Hot Encoding for categorical variables
- Feature Scaling with StandardScaler
- Model Evaluation with accuracy, AUC-ROC, confusion matrix
  
## Outcome and Business Impact:
The lead scoring system significantly improved the sales team's ability to identify "Hot Leads," leading to a more efficient sales process. By focusing on high-conversion leads, X Education was able to increase the overall lead conversion rate, meeting the CEO's target of 80%. The model also provides a scalable solution, allowing the company to adapt as new data is collected or business requirements evolve.
