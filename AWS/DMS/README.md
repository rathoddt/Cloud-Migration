# Migrating from On-Site PostgreSQL to Amazon Aurora


1. Proof of Concept Migration
2. Replication Instances
3. Configuring the Endpoints
4. Creating Migration Tasks
5. Testing the Migration


Begin with a list of databases.
Identify application owners.
Do a "proof of concept" migration.

1) <b>Proof of Concept Migration</b>
    - Keep the tools simple.
        - `pg_dump` and `pg_restore`
        - Can enable compression 
        - Custom, binary format

    - Simple migration to prove it can work
    - Keep the size small. Not a lot of time or effort
    - Have a fallback plan.
        - Whom to notify
        - What applications are affected?
        - How to restore the data?



AWS Schema Conversion Tool (AWS SCT)
    Migrating non-PostgreSQL compatible databases
    Supported data types

2) Replication Instances
    - Replication instances run DMS tasks.
    - Increase instance class for more resources.
    - Deploy as Multi-AZ for higher availability.
    - Ensure security groups allow connections.

3) Configuring Endpoints
    - Endpoints come in two flavors (target and source)
    - Data is read from the source.
    - Data is written to the target.
    - Not all database types are supported.

4) Migration Tasks
    - Three modes
        - Migrate existing data.
        - Migrate existing data and replicate ongoing changes.
            - Change Data Capture (CDC)
        - Replicate data changes only.
    - Large Binary Object (LOB) support
    - Table mappings
        - Use rules to specify which data source to utilize.
        - Use filters to specify data.
        - Use transformations to modify

5) Testing the Migration
    - Involve application owner
    - Pre-migration test
        - Data type assessment
        - Pre-migration assessment run
    - Monitoring
        - Task status
        - CloudWatch and CloudTrail
        - Database logs
        - Time Travel logs



- Catalog Your Databases  
    Generate a list of databases.   
    Identify application owners.   
    Define a Service Level Agreement (SLA).   
    Any other useful data.  