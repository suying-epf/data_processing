# Practices - Data engineering

## TP - Data processing with Apache Spark
To process a large amount of data partitioned on a data lake, you can use data processing frameworks such as Apache Spark :
1. Read : https://spark.apache.org/docs/latest/sql-programming-guide.html

Some questions :
* What is Spark RDD API ?
Spark RDD API: RDD stands for Resilient Distributed Datasets. RDD is a fundamental data structure in Apache Spark that represents an immutable distributed collection of objects. The RDD API provides a set of functions for creating, manipulating, and aggregating RDDs. It supports operations like transformations (e.g., map, filter, reduceByKey) and actions (e.g., count, collect, saveAsTextFile) on RDDs.
* What is Spark Dataset API ?
Spark Dataset API: The Dataset API is a type-safe and object-oriented API introduced in Spark 1.6 that provides the benefits of both RDD and DataFrame APIs. It is a distributed collection of data that is strongly typed, and it supports both SQL queries and functional programming constructs. The Dataset API enables Spark to provide compile-time type safety, while also retaining the benefits of the DataFrame API's optimizations.
* With which languages can you use Spark ? 
Spark can be used with several programming languages, including Java, Scala, Python, and R. Java and Scala are the primary languages used to develop Spark applications, while Python and R are popular for data analysis and machine learning tasks.
* Which data sources or data sinks can Spark work with ? 
Spark can work with various data sources and data sinks, including Hadoop Distributed File System (HDFS), Apache Cassandra, Apache HBase, Amazon S3, relational databases like MySQL, PostgreSQL, and Oracle, and message brokers like Apache Kafka. Spark also supports different file formats, such as Parquet, Avro, ORC, and CSV, among others. Additionally, Spark can work with real-time streaming data using technologies such as Apache Kafka and Apache Flume.



### Analyse data with Apache Spark and Scala 
One engineering team of your company created for you a TV News data stored as JSON inside the folder `data-news-json/`.

Your goal is to analyze it with your savoir-faire, enrich it with metadata, and store it as [a column-oriented format](https://parquet.apache.org/).

1. Look at `src/main/scala/com/github/polomarcus/main/Main.scala` and update the code 

**Important note:** As you work for a top-notch software company following world-class practices, and you care about your project quality, you'll write a test for every function you write.

You can see tests inside `src/test/scala/` and run them with `sbt test`

### How can you deploy your app to a cluster of machines ?
* https://spark.apache.org/docs/latest/cluster-overview.html

To deploy a Spark application to a cluster of machines, we can follow these steps:

Prepare our application: Make sure that our application is ready for deployment. Set up our cluster: Set up a cluster of machines that meet the system requirements for running Spark. Configure our application: Configure our Spark application to work with the cluster. This includes specifying the master node, setting up authentication and security, and configuring any other relevant properties. Submit our application: Use the spark-submit script to submit your application to the cluster. This script takes your packaged application as input and launches it on the cluster. Monitor our application: Monitor your application as it runs on the cluster. Use the Spark web UI and logs to track the progress of your application and troubleshoot any issues that arise. Scale our application: If necessary, scale oour application by adding more worker nodes to the cluster or adjusting the resources allocated to each node but be carefull with great processing power comes great electricity bills.

### Business Intelligence (BI)
How could use we Spark to display data on a BI tool such as [Metabase](https://www.metabase.com/) ?

Tips: https://github.com/polomarcus/television-news-analyser#spin-up-1-postgres-metabase-nginxand-load-data-to-pg
Here are the high-level steps to display Spark data on Metabase:

Use Spark to process and analyze the data and generate insights. Write the results to a data sink such as a PostgreSQL database or Apache Parquet file format. Connect Metabase to the data sink where the results are stored. Configure Metabase to visualize the data in the desired format, such as charts, tables, or dashboards.


### Continuous build and test
**Pro Tips** : https://www.scala-sbt.org/1.x/docs/Running.html#Continuous+build+and+test

Make a command run when one or more source files change by prefixing the command with ~. For example, in sbt shell try:
```bash
sbt
> ~ testQuick
```