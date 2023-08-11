Dataset Description:
The bank_train dataset is a sample taken from a large financial services firm's accounts. It represents consumers of home equity lines of credit, automobile loans, and other types of short-term to medium-term credit instruments. The dataset is used to analyze the latest campaign conducted by the firm, which aims to promote the purchase of insurance products from the bank.

The dataset contains the following fields:

AccountID: The unique identifier for each customer's account.
Activity_Status: Categorizes the customer's activity level or engagement with the bank's financial services.
AvgSale3Yr: The average sales amount over the past three years.
AvgSale3Yr_DP: Average sales amount over the past three years attributed to direct promotional response.(Has missing values)
AvgSaleLife: The average sales amount over the customer's lifetime.
Cnt1Yr_DP: The count of direct promotional responses made by the customer in the past year.
CntPur3Yr: The number of products purchased by the customer in the past three years.
CntPur3Yr_DP: The number of products purchased by the customer in the past three years attributed to direct promotional response.
CntPurLife: The total number of products purchased by the customer over their lifetime.
CntPurLife_DP: The count of products purchased by the customer over their lifetime attributed to direct promotional response.
CntTotPromo: The total count of all promotions the customer received in the past year.
CustTenure: The tenure or duration of the customer's relationship with the bank.
Customer_Value: A level indicating the customer's value to the bank.
Demog_Age: The demographic age of the customer.(Has missing values)
Demog_Homeval: The average home value of the customer based on demographics.
Home_Flag: A binary flag indicating if the customer is a homeowner.
LastProdAmt: The amount of the customer's most recent product purchase.
MnthsLastPur: The number of months since the customer's last purchase.
Status: Denotes the contracted status of the customer.(Target variable)
demog_inc: The average demographic income of the customer.
demog_pr: The percentage of the customer's demographic group that is retired.




Understanding the Problem:

On reading the given problem statement and the available dataset, the task is to predict if a customer will purchase an insurance product from the bank for the current campaign. This is a binary classification problem- having only two types of answers-yes(1) or no(0).
ML models for classification problems are:

1. Logistic Regression: Logistic regression is a simple yet effective model for binary classification problems. It can provide interpretable results and handle both numerical and categorical features. Logistic regression assumes a linear relationship between the features and the log-odds of the target variable.

2. Random Forest: Random Forest is an ensemble learning method that combines multiple decision trees. It can handle both numerical and categorical features, and it's robust against overfitting. Random Forest models can capture complex relationships between the features and the target variable.

3. Gradient Boosting Models: Gradient Boosting models, such as XGBoost or LightGBM, are powerful ensemble methods that iteratively build weak models and combine them to create a strong predictive model. These models often provide high accuracy and can handle various types of features.

4. Support Vector Machines (SVM): SVMs are effective for binary classification tasks, especially when the data is not linearly separable. SVMs find an optimal hyperplane that separates the two classes with the largest margin. SVMs can handle numerical features, but for categorical features, appropriate encoding techniques may be required.

5. Neural Networks: Neural networks, such as feedforward networks or deep learning models, can capture complex patterns and relationships in the data. They are suitable when there is a large amount of data and potentially intricate interactions between features. Neural networks can handle both numerical and categorical features but might require more computational resources and longer training times.

6. Ensemble method: train logistic regression, random forest, and gradient boosting models using the SAS platform 




Steps to solve the problem using SAS platform:

Step1: Uploading the data on SAS platform and saving it. Before that box plots of the data were made to identify the outliers in the attached outliers csv.

Step2: Prepare Data and do transforms
2.1 preparing the data for visual analysis-
a) not removing account ID column as it can be a category
b) imputing with median for column AvgSale3Yr_DP which has missing values

2.2 preparing the data for models
a)done in the build model platform

Step3: Build Model
3.1 A combination of both SVM and Gradient Boost was used. The maximum accuracy yielded from their ensemble model.
The model was registered under the name kgl_fin. The ensemble model was built after doing imputation to replace missing values with median and after clustering.

Step4: Model Manager
The registered model was scored and the output table was opened in the Prepare data section and saved as csv in my SASDrive.


----------------------------------------------------------end----------------------------------------------------------------------------