---
Title: DBS101 Flipped Class 11
categories: [DBS101, Flipped_class11]
tags: [DBS101]
---

## Topic : Concurrency Control
---

### Two-Phase Locking (2PL):

Two-phase locking is a concurrency control mechanism used in database systems to ensure serializability of transactions.It consists of two phases: the **growing phase** and the **shrinking phase**.

In the **growing phase**, a transaction can acquire locks on data items but cannot release any locks.

In the **shrinking phase**, a transaction can release locks but cannot acquire any new locks.

![2pl](/assets/img/2pl.jpeg)

Two-phase locking ensures that transactions acquire all the locks they need before releasing any locks, which helps prevent certain types of conflicts and ensures serializability.
However, 2PL can lead to potential deadlocks if transactions acquire locks in a way that creates a cycle in the lock dependency graph.

### Timestamp Ordering Concurrency Control:

Timestamp ordering is another concurrency control mechanism used in database systems.Each transaction is assigned a unique timestamp when it begins execution.
Operations performed by transactions are ordered based on their timestamps.
Conflicts between transactions are resolved by comparing their timestamps. 

For example, if transaction T1 wants to read an item that was modified by transaction T2, T1's read operation will be rejected if T1's timestamp is earlier than T2's timestamp.
Timestamp ordering ensures serializability by ordering transactions based on their timestamps and preventing certain types of conflicts.

### Locking in Practice

Applications typically don’t acquire a txn’s locks
manually (i.e., explicit SQL commands).
Sometimes you need to provide the DBMS with hints to
help it to improve concurrency.
- Update a tuple after reading it.
- Explicit locks are also useful when doing major
changes to the database.

**Example**

![ss8](/assets/img/Screenshot%20from%202024-05-27%2014-36-45.png)

**SHARE Mode**: Allows read and schema modification
operations but not data modification operations within
the same transaction.

![ss10](/assets/img/Screenshot%20from%202024-05-27%2014-39-32.png)

- **EXCLUSIVE Mode**: Allows full access (read, write,
delete) to the table, blocking all other transactions.

![ss11](/assets/img/Screenshot%20from%202024-05-27%2014-40-59.png)

- **FOR UPDATE**: Acquires an exclusive lock on the selected
rows, allowing modifications on those rows.

![ss12](/assets/img/Screenshot%20from%202024-05-27%2014-41-47.png)

- **FOR SHARE**: Acquires a shared lock on the selected rows,
preventing other transactions from acquiring exclusive locks but allows updates within the same transaction.

![ss13](/assets/img/Screenshot%20from%202024-05-27%2014-42-14.png)

### Locks vs. Latches:

Locks and latches are both synchronization mechanisms used in database systems, but they serve different purposes and operate at different levels of granularity.
Locks are used to control access to shared resources such as data items or database records. They prevent concurrent transactions from accessing the same resource simultaneously in a way that could lead to inconsistencies.

Latches, on the other hand, are lightweight synchronization primitives used to protect in-memory data structures and ensure consistency within the database management system itself.
Locks typically have higher overhead compared to latches because they involve more complex mechanisms for managing concurrency and resolving conflicts.
Locks are usually associated with transactions and are managed by the database management system, while latches are often used internally by the database system to protect its own data structures and are managed by the system itself.

![ss14](/assets/img/LocksVsLatches.png)
