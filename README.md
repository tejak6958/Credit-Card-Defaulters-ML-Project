# Credit-Card-Defaulters-ML-Project

due to file constraint the files are upload through the google drive

Google drive:- https://drive.google.com/drive/u/0/folders/1ZhqL1qAUXiJMTTmnpWgsL5RAfc9B-WpV

(due to the free tier it is unable to keep the terminal file as it, to check it drop an email to tejame050@gmail.com

Problem Statement:-
Whether customer is going to default the credit card payment or not, it is necessary to bank such that it can generate much interest if  credit card  payment is done on time. It is a classification methodology whether they are defaulters or non-defaulters. Based on the forecast it will try to come up with strategics to both payers and non-payers to cope with such situation and limit it is risk taking ability. Such that with the help of this model building the bank can know the actual defaulters.

Aim:-
Whether the person is going to default the credit card payment or not.

DATA SHARING AGREEMENT:-

Before starting any project there will be an data sharing agreement between both the parties such that it need to include all the details and it carry according in that specific manner it follows:-

Name validation:- try to validate the name in particular file name if that criteria does not satisfy, we will try to drop that file.

Number of columns:- As per DSA we will try to check whether we are getting same set of columns even if the client try to send the new dataset.

Name of column: it should contain the same name as per the schema file.

Null values in columns:-  if it contains null values in particular it need to be mentioned in that DSA itself, otherwise we will notify the client and dump that file as it not mentioned in DSA.

Pipeline:-
1)Try to build an system from one end it is going to inject an data on the first layer it will try to check the file name is good or not. It is just rough pipeline to understand it we have drawn it into our convince.

2)Suppose while building the model we will try to send the data to respective cluster or model. maybe perform clustering or grouping operation over there.

3)Similar for the test data we need to perform the same pipeline.

4)this pipeline need to perform on single click with an everything need to be generated (not looking for manual intervention just looking for automation.

Data Description:-
Client will send data in multiple sets of data in batches at a given location. The data has been extracted from census bureau.

Data contains 32561 instances with following attributes:-
      
features:-
Limit_bal:- continuous credit limit of the person.

Sex:- categorical: 1= male , 2= female

Education:- categorical: 1= graduate school, 2=university, 3=high school , 4= others.

Marriage: 1= married , 2= single, 3= others.

Age: num= continuous

Pay_0 to Pay_6:- history of past payment. We tracked the past monthly payments records (from April to septmember,2009)

Bill_amt1 to Bill_amt6:- amount of bill statements.

Pay_amt1 to Pay_amt6:- amount of previous payments.

Data insertion into Database:-

1) Database Creation and connection - Create a database with the given name passed. If the database is already created, open the connection to the database.

2) Table creation in the database - Table with name - "Good_Data", is created in the database for inserting the files in the "Good_Data_Folder" based on given column names and datatype in the schema file. If the table is already present, then the new table is not created and new files are inserted in the already present table as we want training to be done on new as well as old training files.   

3) Insertion of files in the table - All the files in the "Good_Data_Folder" are inserted in the above-created table. If any file has invalid data type in any of the columns, the file is not loaded in the table and is moved to "Bad_Data_Folder  

Model Training:-

Before proceeding to the model training we must do data validation it contains of two types mainly validation and actual training.

In validation we do the following steps:-

Whether the number of columns are same or not.

File name format

Replacing the Na values with null.

Replacing the single code to double code.

Once this steps are performed then it will try to do the actual training.

In actual training the following steps are taken place:-

Data pre-processing:-

Feature selection/column

Missing values.

Categorical to numerical

We will  try to pull all the data from database where it will insert all the good data folder and the bad data folder it will automatically pull out.

data pre-processing with do the following steps:-

We will try to find the missing values, there is no missing values in these datasets

Convert the categorical to numerical values, but here there is no need to do all these since all the values in numerical itself.

Convert imbalanced to balanced dataset.

Since there is high correlation in certain  features among themselves but we will try to keep those values as it since they might incur certain loss of data.

Then we are going to select clustering part for these features suppose we divided into 3 sets, here we are going to use k-means clustering to find the way to do it. Here 

we need to find the k-value. It can be find it out with elbow plot or knee locater.

Prediction:-

it will go through the entire pipeline such that Name of the files, Length of Date value in Filename, Length of Time value in Filename, Number of Columns, Name of the Columns and their datatype.

we also require a "schema" file from client which contains all the relevant information about the training files.

Based on the cluster number, the respective model is loaded and is used to predict the data for that cluster.

Once the prediction is made for all the clusters, the predictions along with the defaulters names are saved in a CSV file at a given location and the location is returned to the client


Deployment:-

We will be deploying the model to the Pivotal Cloud Foundry platform. 







