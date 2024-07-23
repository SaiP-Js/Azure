
## Azure Synapse analytics:

Azure it is one of the analytical service it will be brought data warehouse analytics and big data to one stop.

ADF-- is a service to perform etl operations using ETL pipelines

ADB -- azure data bricks it processes to load the data into bigdata.

ADLS -- Azure data lake storage, which is one type of storage for bigdata.

SQL DW -- and finally  it will load the data into data warehouse.

ETL -- Extract transform load.

ELT -- Extract load transform.

from SQL DW we take it and use those for data visualization using power BI etc., to showcase before leadership and all the above process is called as the Azure synapse analytics.

Azure Synapse analytics has the deep integration with Power BI, Cosmos DB and Azure ML.

 ![Azure Architecture](Azure_SynapseAnalytics.png?raw-true)

Azure Synapse is a limit less analytics service that brings together enterprise data warehousing and big data analytics It gives you the freedom to query 
data on your terms using either serverless or dedicated resources -- at scale.

Azure Synapse analytics bring best of the below components together as single service 

    SQL technologies used in data warehousing (Synapse SQL).

    Spark technologies used in Big data (Apache Spark).

    Pipelines for data integration and ETL/ELT(ADF).

Synapse SQL:
	
#How to create Azure Synapse Analytics workspace.

    portal.azure.com to login and create the Dl.

    Synapse analytics can also login via web.azuresynapse.net and then navigate to the right synapse account and load it.

Basic concepts of Azure Synapse Analytics:

    - Synapse Workspace:

        - Is a collaboration place where we can perform cloud based enterprise analytics in azure.

        - Single workspace where all the data engineers and data scientists work as well.

        - It will be associated with ADLS gen2 and file system.

        - perform analytics with sql and apache spark.

        - Resource available for SQL and Spark analytics are organized into sql and Spark pools.

    - Linked Services:

        - It is a connection strings where synapse analytics can work with external storage account.

    - Synapse SQL :

        - Ability to run tSQL 

    - Apache Spark for Synapse :

    - Pipelines

Normalization:
    - it is easier to understand. 

    - it is enhanced and extend.

    — protect from 

        - inserting anomalies.

        - update anomalies.

        - deletion anomalies.

1st normal form

    - using row order to convey information is not permitted

    - Mixing data types within the same column is not permitted.

    - Having a table without a primary key is not permitted.

    - repeating groups are not permitted.

2nd Normal form.

    - partial dependency is not permitted. ex: if a table is made up with a composite key 

    - (primary key made up of more than one column) non non key attributes should depend on just a part of this composite key.
    - below is the example of 2NF as it ha two tables with one table having composite primary key as (courseID and IInstructor ID) and other table has Instructor ID as a primary key 

| CourseID	  | InstructorID  |
|------------|---------------|
|101	|1
|102	|2
|103	|1

Table 2: 

Instructor

|InstructorID	| InstructorName	 |Department|
|------------|-----------------|------------|
|1	| Dr. Smith       |	Math|
|2| 	Dr. Jones      |	Physics|

3rd NF: also called as boyce-codd normal form:

    - every attribute in a table should depend on the key, the whole key and noting but the key.

4NF: 
    - Multivalued dependencies in a table must be multivalued dependencies on the key.

5th Normal form

    - the table which must be in 4NF cannot be describable as the logical result of joining some other tables together.











    

1NF, 2NF, 3rdNF
DBMS
primary 
grain 
foreign 
storage

    
    

