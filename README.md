# MongoDB SparkConnector Demo

__Demo of data science using MongoDB spark connector and Databricks spark community version__


## Apache Spark

Apache Spark is a data processing framework that can quickly perform processing tasks on very large data sets, and can also distribute data processing tasks across multiple computers, either on its own or in tandem with other distributed computing tools. Spark was released as an Apache open source project in 2014.

# MongoDB connector for Apache Spark

The MongoDB Connector for Spark provides integration between MongoDB and Apache Spark. With this connector, you can access all Spark libraries for use with MongoDB datasets: Datasets for analysis with SQL (benefiting from automatic schema inference), streaming, machine learning, and graph APIs. 

This proof shows how you can connect MongoDB Atlas database to Apache spark and perform queries and do a few calculations on your data that a data scientist may require. I will add an example of machine learning algorithm later on:


For the test 500 fictitious documents representing the data about customers who visited a certain e-commerce website and used the mobile app. Here is the description of what the data contains:
* A date field
* A text field
* A boolean field
* A field that is in a sub document
* A field that is inside an array
* A range based filter

---
## Setup

__1. Configure Atlas Environment__
* Log-on to your [Atlas account](http://cloud.mongodb.com) (using the MongoDB SA preallocated Atlas credits system) and navigate to your SA project
* In the project's Security tab, choose to add a new user, e.g. __main_user__, and for __User Privileges__ specify __Read and write to any database__ (make a note of the password you specify)
* In the Security tab, add a new __IP Whitelist__ and allow access from everywhere.
* Create an __M10__ based 3 node replica-set in a single cloud provider region of your choice with default settings
* In the Atlas console, for the database cluster you deployed, click the __Connect button__, select __Connect Your Application__, and for the __latest Node.js version__ copy the __Connection String Only__ - make a note of this MongoDB URL address to be used in the next step

__2. Create and Configure Spark cluster on Databricks__
* Goto https://community.cloud.databricks.com
* At the login screen click on Sign Up if you do not have a databricks communnity account yet
* Once you are on the signup screen and you have entered your details, make sure to click on the "Use Community" link to be able to use the free community version of databricks(see creen shot).

<table><tr><td><img src='/images/dbricks0.png' alt=“” height="400"></td></tr></table>

* Copy and paste the below code in your Jupyter notebook
  ```bash
 code here
  ```
__3. Load Data Into A Collection In The Atlas Cluster__
