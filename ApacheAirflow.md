
# Apache Airflow (Scheduling Tool).

IN today's data-driven environment, efficiently managing complex data pipelines is critical for any organization. apache airflow has emerged as a widely adopted tool, deleted for its flexibility and robustness. however, a common question often arises is apache airflow, an orchestration toll ot ETL tool, we will look in this blog and also dive deep into Apache airflow's core functionalities, highlight its strength and clarify its role within data workflows.

## what is Apache Airflow?

Apache Airflow is an open-source platform designed to programmatically author schedule and monitor workflows. Initially developed by Airbnb, it has evolved into a highly flexible and powerful tool supported by a vibrant community. Airflow uses its Directed Acyclic Graphs to manage task execution, dependencies, and scheduling.

## Awareness on orchestration vs. ETL.

WorkFlow Orchestration:

WorkFlow orchestration refers to the management of executing multiple tasks in a specific sequence, handling dependencies and managing failures and retries. Orchestration tools typically offer the following capabilities:

- Scheduling tasks based on time or external triggers.
- Managing dependencies between tasks.
- Monitoring Tasks execution and handling errors or retries.
- Providing a visual interface to tract workflow status.

## ETL :

 ETL is a process used to integrate data from various sources into a single, unified data store, usually a data warehouse. it consists of three primary steps:

- Extract: Retrieving data from sources systems
- TTransform: Converting Data into a suitable format for analysis, which includes cleaning aggregating and enriching the data.
- Load: Loading the transformed daa into the target system, such as a database or data warehouse.


## Airflow as a coordination Tool.

Key Features:

### DAG-Based Workflow Management:

Airflow Defines Workflows using Directed Acyclic Graphs(DAGs). Each Node in a DAG represents a task and the edges define dependencies between tasks. This structure ensures that tasks are executed in the correct Order, respect to all dependencies.

Flexible Scheduling Capabilities: Airflow provides robust scheduling features, allowing tasks to be triggered based on time or external events. We can configure schedules using cron expressions or airflow's flexible `time delta` syntax

Extensibility:

Airflow is highly extensive, supporting the creating of custom operators, sensors, and hooks. This flexibility enables seam less integration with a broad range of systems and services allowing users to build workflows that incorporate various technologies.

Robust Monitoring and logging:

Airflow provides a comprehensive web interface for monitoring workflow execution. Users can visualize DAG's track task progress and access logs for debugging. The web UI also allows for managing takes retries and dependency efficiency.

### Example: Coordinating a Workflow

Imagine a scenario where you need to coordinate a workflow that involves extracting data from an API, processing the data and then storing the results in a database. Using Airflow, you can define this entire process as a DAG:


-- below are the required imports for this 
`from airflow import DAG // to define the workflow from DAG 
from airflow.operators.python_operator import PythonOperator // to run Python functions as tasks
from datetime import datetime, time delta //module to manage time and date 

//below are the default arguments
default_args = {
'owner': 'airflow,' //the Owner of the DAG.
'depends_on_past': False, // the task doesn't depend on previous tasks
'email_on_failure': False, //No email is sent if failed.
'retries': 1, //Number of retries if the task fails.
'retry_delay': time delta(minutes=5), //delay between retries.
}

def extract_data(): //this functions would contain the code to extract the data from API.
# Code to extract data from API
pass

def process_data(): //this functions would contain the code to process the extracted data.
# Code to process data
pass

def load_data(): //this Function would contain the code to load the processed data.
# Code to load data into database
pass

dag = DAG('example_workflow,' // the DAG is started here with name example_workflow.
default_args=default_args, //applies all the default arguments to all the tasks.
description='An example DAG', //Description of the DAG 
schedule_interval=time delta(days=1), //Scheduled to run this task Daily.
start_date=datetime(2023, 1, 1), // sets the Start date for the DAG 
catchup=False, it prevents the backfilling of the DAG between start_date and the current_date.
)

//Below are the tasks whcih we execute one by one 
task1 = PythonOperator(
task_id='extract_data',
python_callable=extract_data,
dag=dag,
)

task2 = PythonOperator(
task_id='process_data',
python_callable=process_data,
dag=dag,
)

task3 = PythonOperator(
task_id='load_data',
python_callable=load_data,
dag=dag,
)

below is the sequence that tasks will be executed as of this DAG.
task1 >> task2 >> task3`

