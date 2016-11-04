# Data In Motion (DIM)
Popular approaches to harness Big Data are based on architectures that store huge amount of data and has distributed routines that crawl on partitions of this stored data.  Data at Rest approaches apply analytics after the data is persisted to secondary storage and the insights provided are reactionary in nature.  On the other hand, the traditional approach to real-time analytics is through Business Activity Monitoring (BAM) that captures Key Performance Indicators (KPI(s)) on the fly and publishes them to analytics engine.  Inheriting the best capabilities of both these approaches can help create a framework for Data in Motions Analytics that supports configurable data streams correlated and combined with other streams in order to derive insights. 

DIM is a distributed real-time messaging architecture that can enable configuration driven data in motion analytics. The architecture acquires unstructured and heterogeneous data generated from system interactions on the fly and leverages a distributed Messaging, Processing and Caching system for downstream analytics processing. 

Some of the key features of the architecture are Configurable data streams, Chucking, Data Anonymization, Correlation based on Expressions and Caching.

## Architecture

## Supported Pluggable Input Sources
- RabbitMQ 
- Kafka 
- Salesforce SOQL
- Salesfore Streaming Topic 
- TCP Socket

## Supported Pluggable Output Targets
- Elasticsearch
- MongoDB
- HDFS
- RabbitMQ
- Kafka
- JDBC
- TCP Socket

## Logical Entities
- Event Stream
- Contexts
- Mappings 

## Features
- Computed Fields
   
- Persisted Fields
- Revised Fields
- External Lookup
- Traps & Actions
- Enrichment Completion

## Configuration
