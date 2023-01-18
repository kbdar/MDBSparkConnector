
Demo of data science using MongoDB spark connector and Databricks spark community version
<table><tr><td><img src=“application/public/images/vod.png” alt=“dashboard” height=“400”></td></tr></table>

## Test
With the connector, you have access to all Spark libraries for use with MongoDB datasets: Datasets for analysis with SQL (benefiting from automatic schema inference), streaming, machine learning, and graph APIs. You can also use the connector with the Spark Shell.

### --> H2
Clone this Repositorie to your local machine
```
Grey part
```

# MongoDB SparkConnector Demo

__Demo of data science using MongoDB spark connector and Databricks spark community version__


## What is Apache Spark?

Apache Spark is a data processing framework that can quickly perform processing tasks on very large data sets, and can also distribute data processing tasks across multiple computers, either on its own or in tandem with other distributed computing tools. Spark was released as an Apache open source project in 2014.

This proof shows how MongoDB can perform expressive queries using query criteria spanning a number of fields and how secondary indexes can be leveraged to greatly reduce query response time and minimise database overhead. Specifically, the proof will show that a collection of 1,000,000 randomly generated documents can be searched using a combination of elements, demonstrating the richness and flexibility of the query language. These elements will include:

* A date field
* A text field
* A boolean field
* A field that is in a sub document
* A field that is inside an array
* A range based filter

For the test 1,000,000 fictitious 'single view' insurance customer records are generated and loaded into a collection in a MongoDB Atlas cluster.

The expressive query that will be run will return all documents where the _"customer is Female, born in 1990, lives in Utah and has at least one Life insurance policy for which they are registered as a Smoker"_.


---
## Setup
__1. Configure Laptop__
* Ensure MongoDB version 3.6+ is installed on your laptop in order to access the MongoDB command line tools (a MongoDB Atlas cluster will be used to actually host the data)
* [Download](https://www.mongodb.com/download-center/compass) and install Compass on your laptop
* Ensure Node (version 6+) and NPM are installed your laptop
* Download and install the [mgeneratejs](https://www.npmjs.com/package/mgeneratejs) JSON generator tool on your laptop
  ```bash
  npm install -g mgeneratejs
  ```

__2. Configure Atlas Environment__
* __Note__: If using the Shared Demo Environment (https://docs.google.com/document/d/1cWyqMbJ_cQP3j7S4FJQhjRRiKq9WPfwPG6BmJL2bMvY/edit), please refer to the pre-existing collections for this PoV. (RICH-QUERY.customers & RICH-QUERY.customersIndexed)
* Log-on to your [Atlas account](http://cloud.mongodb.com) (using the MongoDB SA preallocated Atlas credits system) and navigate to your SA project
* In the project's Security tab, choose to add a new user, e.g. __main_user__, and for __User Privileges__ specify __Read and write to any database__ (make a note of the password you specify)
* In the Security tab, add a new __IP Whitelist__ for your laptop's current IP address
* Create an __M10__ based 3 node replica-set in a single cloud provider region of your choice with default settings
* In the Atlas console, for the database cluster you deployed, click the __Connect button__, select __Connect Your Application__, and for the __latest Node.js version__ copy the __Connection String Only__ - make a note of this MongoDB URL address to be used in the next step

__3. Load Data Into A Collection In The Atlas Cluster__
