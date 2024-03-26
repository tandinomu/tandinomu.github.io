---
Title: DBS101 Flipped Class 6
categories: [DBS101, Flipped_class6]
tags: [DBS101]
---

## Topic :  Non-Relational Databases

### Non-relational data and NoSQL

A non-relational database is a database that stores data in non-tabular form. These databases use a storage model that is optimized for the specific requirements of the type of data being stored. Non-relational databases tend to be more specific in the type of data they support and how data can be queried. For example, time series data stores are optimized for queries over time-based sequences of data. 

The term NoSQL refers to data stores that do not use SQL for queries. "NoSQL" means "non-relational database," and stands for not only SQL.

The following are the types of non-relational databases.

1. #### Document based database. 

A document-based database is a type of database management system that stores, retrieves, and manages data in the form of documents unlike other relational databases which stores data in the form of rows and columns. 
A document database stores data in JSON, BSON, or XML documents.

**Advantages**

- They can store and query data with different schemas, formats, and levels of complexity.
Enables high availability, fault tolerance, and the ability to handle large volumes of data and concurrent requests
- They can efficiently retrieve and manipulate entire documents, reducing the need for complex joins and improving query performance.

**Disadvantages**

- Many document databases sacrifice strong consistency. They may not provide transactional guarantees across multiple documents or collections. 
- They pose challenges related to ecosystem maturity that developers and organizations must consider when evaluating their suitability for specific use cases.

2. #### Key-Value based database.

It is the simplest form of a NoSQL database. The data is retrieved by using a unique key assigned to each element in the database. 

A key-value store has only two columns which is the key and the value.

**Advantages**

- have a simple data model, making them easy to understand, implement, and use.
- offer fast read and write operations.
- can scale horizontally to handle large volumes of data
  
**Disadvantages**

- They lack advanced querying features found in relational databases. 
- Data duplication is common in key-value databases to optimize performance. 

3. #### Graph Databases.

Type of database that uses graph model to represent or store data. Graph database is collection of nodes table. Whereby, nodes are entities and edges are relationships. 

Used to generate AI, network and IT operations, etc.. 

**Advantages**

- Clear and manageable representation of relationships. 
- Flexible structures. 
- Query speed only dependent on the number of concrete relationships and not amount of data.

**Disadvantages** 

- Difficult to scale. 
- No uniform query language. 

4. #### Vector Database. 

A vector database is a collection of data stored as mathematical representation. These are used in image recognition, chroma, vespa,etc…

**Advantages** 

- Flexible.
- Stores unstructured data.

**Disadvantages** 

- Datatype limitations.
- Latency issues 

5. #### Time-series database 

A time series database is a specialized database that efficiently stores and retrieves time-stamped data.  It is storage for rapidly changing data. The starting point or initial timestamp from which the time series data begins is called time stem. Time stems help establish the time frame over which data points are collected, enabling users to retrieve relevant information and perform analyses within specific time intervals.

It is useful for data that changes over time, such as sensor data, financial market data, server logs,etc..,

**Advantages** 
 
- enables fast data retrieval and cost-effective storage.
- offer built-in functions and features for time-centric operations such as aggregation, downsampling, and windowing.
- provide high-performance read and write operations

**Disadvantages** 

- lack the flexibility to handle complex data structures or relationships found in other types of databases.
- may be less suitable for complex relational queries that involve multiple datasets or join operations.

6. #### Column-oriented database. 

A column-oriented database is a database that stores the data in columns instead of rows. These databases can read those columns directly without consuming memory with the unwanted data and are designed to read data more efficiently and retrieve the data with greater speed. 

**Advantages** 

- column-based databases offer significant advantages for analytical workloads, including improved query performance, efficient storage, enhanced analytics capabilities, and scalability. 

**Disadvantages** 

- Designing and managing schema for a column-based database can be more complex. 
- Maintaining columnar indexes and optimizing queries for column-based storage can introduce overhead and complexity in database administration.

