Session8
Assignment 2
1)	Core changes made in Hadoop 2.x
1.	Architectural Evolution: 
•	Fundamental architectural changes are made for both computing and storage sides of the platform in Hadoop 2.X.
•	Compatibility With Map Reduce:
	Scalability
	Better Cluster Utilization
	Support for workloads other than MapReduce
	Agility
	Disaster Recovery
2.	NameNode High Availability: 
•	Hadoop 1.X has a single master server called NameNode where all the metadata is stored.
•	Hadoop 2.X handles this situation by triggering automatic failover by which the standby NameNode becomes active.
3.	HDFS Snapshots: 
•	Hadoop 2.X adds support for file system snapshots.
•	A snapshot is a point-in-time image of the entire file system or a subtree of a file system.
4.	RPC Improvements and Wire Compatibility:
•	Hadoop 2.X is having several betterments to the RPC layer shared by HDFS, YARN, and MapReduce v2. 
•	RPC also adds support for client-side retries of the operation, a key functionality for supporting highly available server implementation. 
•	These betterments help in running different versions of daemons within the cluster, paving the way for rolling upgrades.

2)	Difference between MapReduce 1 and MapReduce 2 (Yarn)
1.	MapReduce 1.0:
•	MRv1 which is also called as Hadoop 1 where the HDFS (Resource management and scheduling) and MapReduce (Programming Framework) are tightly coupled.
•	MRv1 uses the JobTracker to create and assign tasks to data nodes, which can become a resource bottleneck when the cluster scales out far enough (usually around 4,000 nodes) which is one of the limitations.
•	Hadoop is “Rack Aware” and HDFS has replicated chunks on nodes on different racks.
•	A file in MapReduce 1.0 is broken into 64MB chunks by default and distributed across Data Nodes.
•	It has single NameNode so, it doesn't provides high system availability and scalability.
•	Another issue being multi-tenancy that is it is impossible to run other frameworks than MapReduce 1.0 on a Hadoop cluster.
•	The default replication factor of MapReduce 1.0 is 3, meaning there will be 3 copies of the data at any given time.
2.	MapReduce 2.0:
•	MapReduce 2.0 has two components – YARN ("Yet Another Resource Negotiator") that has cluster resource management capabilities and MapReduce.
•	It has a Resource Manager for each cluster, and each data node runs a Node Manager.
•	NodeManager is responsible for launching containers that could either be a map or reduce task.
•	It also provides high system availability and scalability as we can create redundant NameNodes.
•	The new feature of snapshot through which we can take backup of file systems which helps disaster recovery that is it has a Secondary NameNode.
•	Thus in Hadoop clusters, MapReduce 2.0 helps in scaling up to larger configurations more than 4000 nodes.
•	This architecture also allows simultaneous execution of a variety of programming models such as graph processing, iterative processing, machine learning, and general cluster computing, including the traditional MapReduce.
