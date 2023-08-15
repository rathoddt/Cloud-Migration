# Migrating an On_site PostgreSQL Database to Amazon Aurora

1) Check that the security group has one inbound rule allowing PostgreSQL connections from the listed subnet.

2) Create Replication Instance
	Click Create replication instance.  
	Under Name, enter `dms-rep-instance1`.  
	Under Description, enter aurora migration replication instance.  
	Under VPC, select the provided Lab_VPC.  
	Under Multi AZ, select Dev or test workload (Single-AZ).  
	Uncheck the box next to Publicly accessible.  
3) Create Endpoints
   - Source & target endpoints
4) Create database migration task.Set the following parameters:
	- Task identifier: Enter aurora-migration.
	- Replication instance: Select our replication instance.
	- Source database endpoint: Select psql-source.
	- Target database endpoint: Select our target endpoint.
