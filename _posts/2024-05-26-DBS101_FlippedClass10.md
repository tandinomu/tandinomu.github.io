---
Title: DBS101 Flipped Class 10
categories: [DBS101, Flipped_class10]
tags: [DBS101]
---

## Topic :  Transactions
---

### Transaction 

A transaction is a single logical unit of work that accesses and possibly modifies the contents of a database. Transactions are crucial for maintaining data consistency and integrity within a database management system (DBMS).

 To ensure the reliability and consistency of transactions, the ACID properties are followed. 

### ACID 

 Atomicity, Consistency, Isolation, and Durability

- Atomicity ensures that a transaction is treated as a single, indivisible unit of work. Either all operations within the transaction are completed successfully, or none of them are. If any part of the transaction fails, the entire transaction is rolled back to its original state, ensuring data consistency and integrity.

- Consistency requires that a transaction takes the database from one consistent state to another consistent state. The database must be in a consistent state both before and after the transaction is executed. Constraints, such as unique keys and foreign keys, must be maintained to ensure data consistency.

- Isolation ensures that multiple transactions can execute concurrently without interfering with each other. Each transaction must be isolated from other transactions until it is completed. This isolation prevents issues like dirty reads, non-repeatable reads, and phantom reads.

- Durability guarantees that once a transaction is committed, its changes are permanent and will survive any subsequent system failures. The transaction’s changes are saved to the database permanently, and even if the system crashes, the changes remain intact and can be recovered.

![ACID](/assets/img/Acid2.png)

### A Simple Transaction Model

Consider a transaction Ti that transfers $50 from account A
to account B:

Initial values: A = $1000, B = $2000
Transaction Ti
Ti: read(A);
A := A - 50;
write(A); read(B);
B := B + 50;
write(B);

#### Atomicity Example

Failure occurs after write(A) but before write(B)

- Values: A = $950, B = $2000 (Inconsistent state)

#### Ensuring Durability

- Write updates to disk before transaction completes.
- Log information to reconstruct updates after failure.

#### Isolation Example

- Transaction T1 reads A and B, computes A + B.
- Concurrent transaction T2 updates A and B based on
- inconsistent values.

- Solution: Execute transactions serially or use
concurrency control.

Transaction in Postgresql

![ss](/assets/img/Screenshot%20from%202024-05-20%2013-54-24.png)

#### Transaction Atomicity and Durability

- Transaction may abort, failing to complete
successfully, but for atomicity, its effects must be
undone.

- Recovery scheme manages aborts, typically by
maintaining a log.

- Log records each database modification, including
transaction and data item identifiers, old and new
values.

- Log-based recovery enables redoing or undoing
modifications to ensure atomicity and durability.

#### A simple abstract transaction model:

- Active: Initial state, transaction executing.

![ss3](/assets/img/Screenshot%20from%202024-05-20%2014-09-11.png)
![ss4](/assets/img/Screenshot%20from%202024-05-20%2014-09-44.png)

- Partially committed: After final statement execution.

![ss5](/assets/img/Screenshot%20from%202024-05-20%2014-11-13.png)
![ss6](/assets/img/Screenshot%20from%202024-05-20%2014-11-26.png)

- Failed: Normal execution can't proceed.

![ss7](/assets/img/Screenshot%20from%202024-05-20%2014-12-53.png)

- Aborted: Rolled back, database restored to
pre-transaction state.

![ss8](/assets/img/Screenshot%20from%202024-05-20%2014-13-18.png)

- Committed: Successfully completed.

![ss9](/assets/img/Screenshot%20from%202024-05-20%2014-13-18.png)

#### Transaction Isolation 

Transaction isolation in databases is about managing how concurrent transactions interact with each other to maintain data consistency and integrity. 

There are several isolation levels defined by the SQL standard, including:

- Read Uncommitted: This is the lowest isolation level. Transactions can see uncommitted changes made by other transactions. This level provides no protection against dirty reads, non-repeatable reads, or phantom reads.

- Read Committed: This level prevents dirty reads by ensuring that transactions only see committed data. However, it does not prevent non-repeatable reads or phantom reads.

- Repeatable Read: In this isolation level, a transaction sees a consistent snapshot of the database as it existed at the start of the transaction. This prevents non-repeatable reads but does not prevent phantom reads.

- Serializable: This is the highest isolation level. It ensures that transactions are executed in such a way that the outcome is the same as if they were executed serially, one after the other. Serializable isolation prevents all types of anomalies: dirty reads, non-repeatable reads, and phantom reads.

- Snapshot Isolation: This is an isolation level that provides a consistent snapshot of the database to each transaction. It ensures that each transaction sees a consistent snapshot of the database as it existed at the start of the transaction, regardless of changes made by other transactions. This prevents non-repeatable reads and phantom reads but allows some degree of concurrency.

#### Serializability

It is the final state of the database is the same as if the transactions had executed one after the other, in some order.

Here's an example to illustrate serializability:

- Transaction A transfers $100 from Account X to Account Y.
- Transaction B transfers $50 from Account Y to Account Z.

If these transactions execute serially, the final state would be consistent. However, if they execute concurrently and Transaction B reads the balance of Account Y before Transaction A has completed, Transaction B might end up transferring $50 based on an outdated balance, leading to an inconsistent state.
