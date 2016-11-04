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
#### Event Stream
  An event stream is logical representation of real-time collection of data, which are identified based on user defined filter expressions, and represent a "Type" of data. For example, an application generates data related to user creation event, and emits payloads of user related information, which is identified by a certain data tag in the payload, it can be identified as an event stream of User Creation.
   
#### Contexts
   Context is a user defined combination of event data, which provides a unified business process view of event data by accumulating, transforming and processing event streams. Each context is a logical representation of a type of business process, and stores three major types of data:
 -	Data fields from event streams
 - Transformed and calculated fields derived from event stream data
 - Identifiers

#### Mappings 
   Once we have definition of events and the target contexts that we need to populate, we can then define the various transformations, joins and calculations to be persisted, and also use context as the common entity which allows users to configure relationships between multiple event streams. Mapping is defined as a stream-centric relationship between one event stream and multiple contexts
   
## Features

#### Computed Fields
   Additional fields to be persisted/enriched in the context. <br>
   Example:
   ```
   {
      "stateName": "masked_password",
      "conditions": "var str = $.payload.password; (str != null) ? (str.substr(0,3)) + '****'  : '';"
   }
   ```
   
#### Persisted Fields
   Fields from Event Stream to be persisted/enriched in the context. <br>
   Example:
   ```
   {
       "streamFieldName": "$.payload.user.emailAddress",
       "contextFieldName": "EmailID"
   }
   ```
   
#### Revised Fields
   Field values to be edited inline in the Event Stream. <br> 
   Example:
   ```
   
   ```
   
#### External Lookup
   Series of external URL's to be invoked to retrieve additional data and enrich the stream. <br>
   Example:
   ```
   "externalLookUp": {
            "urlTag": [{
                "url": "https://HOST:PORT/service_context/:1",
                "methodType": "get",
                "contentTypeHeader": "application/x-www-form-urlencoded",
                "tag": "$.data.accounts",
                "queryParam": "$.data.AccountId"
            }]
        }
   ```
   
   
#### Traps & Actions
#### Enrichment Completion

## Configuration
