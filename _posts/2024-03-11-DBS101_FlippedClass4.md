---
Title: DBS101 Flipped Class 4
categories: [DBS101, Flipped_class4]
tags: [DBS101]
---

### Topic : Advanced Aggregation Functions
---
Advanced aggregate functions are more complex and specialized functions used in databases, particularly in SQL to perform calculations on groups of rows and return a single result. They often involve multiple steps or conditions to calculate the result. Some of the advanced aggregate functions we learned in the class are:

1. Ranking: Used to rank each row of a partitioned part of a table. They are used with the OVER()clause and they assign rank on the basis of ORDER BY clause (sequential manner). These functions provide valuable insights into data by assigning a numerical position to each row based on specified criteria and enables users to perform various analytical tasks. 

2. Windowing: Windowing refers to the ability to define a subset or “window” of rows within a partition over which the aggregate function operates. Windowing functions are used to perform calculations across a set of rows related to the current row within a partition of a result set. They provide a way to perform aggregate calculations without collapsing the result set into a single row, allowing for more complex analyses and reporting.


3. Pivoting: It is the process of taking rows of data and converting them into columns. It allows users to:
transform long-format data into wide-format data(makes it easier to read.)
Aggregate multiple rows of data. 
Displays data in a user-friendly manner. 
Here is an example of SQL pivot query. 


syntax:

        SELECT Date,//lists the desired columns to display in the final output.
            SUM(IF(Product = 'Product A', Sales, 0)) AS 'Product A',
            SUM(IF(Product = 'Product B', Sales, 0)) AS 'Product B',
            SUM(IF(Product = 'Product C', Sales, 0)) AS 'Product C'
        FROM SalesData //defines the data source
        GROUP BY Date; // function for pivot


3. Rollup and cube: Both rollup and cube are used for data summarization in SQL queries, rollup generates subtotal rows for hierarchical levels of grouping, while cube generates subtotal rows for all possible combinations of grouping sets.

- Rollup: performs summarization on multiple levels of grouping. It computes multiple levels of subtotal aggregates and is usually applied in conjunction with the GROUP BY clause. Rollup produces a result set that includes not only the individual rows but also aggregated subtotal rows.
- Cube: Cube computes all possible combinations of groupings specified in the query, generating subtotal rows for each combination. It provides a more comprehensive summary of data compared to rollup. Like rollup, cube is also used with the GROUP BY clause, but it generates subtotal rows for all possible combinations of grouping sets, resulting in a more extensive result set.

During this flipped class, same like the classes before we formed groups on the 4 subtopics under advanced aggregate function and presented them to the class. Also, we presented demos on some of the databases we used for conveying more information and for better understanding. 

