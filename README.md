# DBSAssignment

Serial Transactions:
A for loop is used to read the transactions one after the other. Each operation in transaction is 
implemented serially in the order as in Tn.txt file.

Interleaving Transactions:
Priority Queues have been used to implement interleaving transactions. A waiting queue is used to 
maintain the list of transactions which need to be executed. Two other queues(pipeline1 and pipeline2) 
have the operations from currently executing transactions that execute the operations alternately.

Strict 2-phase locking:
Priority Queues have been used here as well for transactions list and for operands two queues (pipeline1, 
pipeline2) have been used for alternate transaction execution. A dict() variable ‘locks’ has been used for 
performing the exclusive locks on the resources A1,A2,…. In the database. 
By strict 2PL, if a transaction gets exclusive lock (write lock) on a resource, another transaction cannot 
access it for any operation. In the given transaction list, T3 acquires exclusive lock on resource A2 and T4 
acquires exclusive lock on resource A1. Then T3 tries to read from A1 and keeps waiting for T4 to release 
the lock and T4 tries to read from A2 and keeps waiting for T3 to release the lock. So these transaction 
result Deadlock situation
