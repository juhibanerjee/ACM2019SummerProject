# Analyze Customer Churn Data - IBM Project 2019

## Introduction
Imagine you are a bank with client retention issues — your customers are leaving the bank (churning). Using Jupyter Notebooks with IBM Open Data Analytics for 
z/OS (IzODA) to look at credit card transactional data, with the various Python libraries and the optimized data layer provided by IzODA, you can create robust
data visualizations that allow you to look for key features as to why a customer may want to leave your bank.

Input: Client information table with 6,001 records
          Credit card transaction table with about 1.5 million records. 


## What is IzODA?
Various types of data stores and databases are used in Mainframe. IzODA is nothing but a data virtualization layer. 
* It can access VSAM, IMS, DB2, Spark and other mainframe data.
* It can access non-Mainframe data like Oracle, MySQL, Spark.


## Code Components
* Data Pre-processing
  * Importing client and transaction datasets.
  * Merging the transaction datasets.
  * Adding new features to client dataset upon initial analysis of transaction dataset.
* Data Visualization
  * Plotting techniques using matplotlib and seaborn.
* Churn Prediction
  * Applying 5 different classification models to predict customer churn but using the one given by IBM Code Patterns to calculate the overall loss.
  * Calculate overall business loss based on the predicted churn.
  
  
 ## Data Pre-processing for CSV file
  * The client dataset has 6001 rows and 7 columns and the transaction dataset has 1497299 rows and 14 columns.
  * For csv file, we initially had group based on customer ID. Then we found certain fields to process the data and for initial analysis.
  * Different columns are made to store various transaction details of the customer, such as total transaction, total transaction amount, etc.
  
  
 ## Data Pre-processing for DB2 and VSAM file
  * The SSID of DB2 and VSAM is set. The username and password is also set to access them.
  * dsdbc is imported so that the files can be accessed.
  * The data is then converted from EBCDIC to ASCII.
  * The DB2 data is accessed easily through SQL and the VSAM file is accessed through MDS.
  
  
 ## Data Visualization
  Using matplotlib and seaborn, various plots have been made. From these plots, age analysis and churn prediction has been done using the data received 
  from RandomForestClassifier.
  
 ## Churn Prediction
  The data is splitted into train and test sets to avoid overfitting. Five different classification models have been used :
  * Random Forest Classifier
  * K-Neighbors Classifier
  * AdaBoost Classifier
  * SVC
  * Decision Tree Classifier
  RandonForestClassifier has been used to calculate the churn loss as that was used in IBM Code Patterns.


 ## Conclusion
 * Analytics allows business to focus resources to retain profitable customers. 
 * Due to data gravity and data security, the latency and risk is reduced.
 * Insights from analytics can be plugged into transactional processing to provide customized and differentiated service to the customers.
 * Mainframe analytics requires no special Mainframe skill other than knowing how to connect to the data tables via IzODA


 ## References
 * https://developer.ibm.com/patterns/
 * https://www.ibm.com/support/knowledgecenter/zosbasics/com.ibm.zos.zconcepts/zconcepts_169.htm
