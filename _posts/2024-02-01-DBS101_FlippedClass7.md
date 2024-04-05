---
Title: DBS101 Flipped Class 7
categories: [DBS101, Flipped_class7]
tags: [DBS101]
---

### Topic :  Database Storage Structures
---

Todays guided session focused on three main task on the storage and buffer management which are simulating disk blocks, RAID configuration and buffer pools.

### Disk Block Implementation 

Disk blocks implementation involves managing data storage and retrieval operations on physical storage devices. Disk blocks are the basic units of storage on a disk, typically consisting of fixed-size chunks of data. Allocation and deallocation mechanisms are employed to manage disk blocks efficiently.

Understanding disk block implementation is important for efficient data storage and retrieval in a database system. 

In the guided session:

- I created a DiskBlock instance with 10 blocks of size 512 bytes. 
- Allocated contiguous blocks for data1 and read data to those blocks.
- After deallocating data1, I allocated new blocks for data3.
- Finally, I defragmented the disk, which consolidates the allocated blocks for data3



### RAID Configuration:
 
 Redundant Array of Independent Disks configurations involves distributing data across multiple disks to improve performance, reliability, or both. Different RAID levels, such as RAID 0, RAID 1, RAID 5, and RAID 10, offer varying levels of data redundancy and performance.

Configuring RAID levels are essential for achieving desired levels of data redundancy, fault tolerance, and performance. By simulating RAID configurations, optimal storage solutions can be designed to meet specific application requirements.

In the guided session:

- I created a RAIDArray instance with 4 disks, block size 512 bytes, and RAID level 0 (striping).
- I wrote data to the RAID 0 array and read it back.
- I created another RAIDArray instance with 4 disks, block size 512 bytes, RAID level 1 (mirroring), and 1 spare disk.
- I wrote data to the RAID 1 array, read it back, simulate a disk failure, and rebuild the array using the spare disk.


 ### Buffer pools

A database buffer pool is a cache in a database management system (DBMS) that stores database pages in memory, allowing quicker access to frequently accessed data.

Implementing and managing buffer pools effectively is important for optimizing memory usage and access times in a database system. 

The code we used in the guided session ensures that frequently accessed pages are readily available in memory, while efficiently managing the limited memory resources by evicting less frequently accessed pages and handling the persistence of modified pages to disk.

In summary, tasks such as disk blocks implementation, RAID configuration, and buffer pools management are integral parts of storage and buffer management, contributing to the optimization of database system performance and reliability.

---

### Summary for the Exercise

As for the exercise we outlined the important procedures to be followed when building a relational database from scractch and their importance and listed data structures to be used.

To summarize, **while building a relational database from scracth**, several important procedures must be followed to ensure its successful development and functionality. 

Firstly, thorough requirements gathering is essential to understand the database's purpose, scope, and the needs of its users. This step sets the foundation for the entire database development process, guiding subsequent decisions and ensuring alignment with stakeholders' expectations. 

Once requirements are gathered, the conceptual database design phase begins where Entity-Relationship Diagram (ERD) is created to model the entities, attributes, and relationships within the database. The importance of this phase lies in its ability to establish a clear understanding of the data model, ensuring consistency and coherence in database design.

Following the conceptual design, the logical database design phase focuses on translating the ERD into a logical schema consisting of tables, relationships, and constraints. By normalizing the schema, data redundancy is minimized, and potential anomalies are mitigated, ensuring a reliable database structure.

Once the logical design is complete, the physical database design phase addresses the implementation details of the database on physical storage devices. 

The use of tables, fields, primary keys, foreign keys, and indexes are essential data structures that support these procedures, ensuring the database is effective, efficient, and well-structured.



