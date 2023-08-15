# Migrating from On-Site PostgreSQL to Amazon Aurora


1. Proof of Concept Migration
2. Replication Instances
3. Configuring the Endpoints
4. Creating Migration Tasks
5. Testing the Migration


Begin with a list of databases.
Identify application owners.
Do a "proof of concept" migration.

1) Proof of Concept Migration
    - Keep the tools simple.
        - `pg_dump` and `pg_restore`
        - Can enable compression 
        - Custom, binary format

    - Simple migration to prove it can work
    - Keep the size small. Not a lot of time or effort
    - Have a fallback plan.



AWS Schema Conversion Tool (AWS SCT)
    Migrating non-PostgreSQL compatible databases
    Supported data types

2) Replication Instances
    - Replication instances run DMS tasks.
    - Increase instance class for more resources.
    - Deploy as Multi-AZ for higher availability.
    - Check the security group.

3) Configuring Endpoints
    - Data is read from the source.
    - Data is written to the target.
    - Not all database types are supported.

4) Migration Tasks
    - Three modes
    - Large Binary Object (LOB support
    - Table mappings

5) Testing the Migration
    - Involve application owner
    - Pre-migration test
    - Time Travel logs


- Catalog Your Databases  
    Generate a list of databases.   
    Identify application owners.   
    Define a Service Level Agreement (SLA).   
    Any other useful data.  