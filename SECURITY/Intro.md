# SECURITY


| Services                     | Use Cases                  | Database type
| :---                         | :----                      | :-----:
| Amazon Autora                | Traditional applications.  | Relational              
| Amazon RDS                   | ERP, CRM.                  | Relational 
| Amazon Redshift              | e-commerce.                | Relational 
| Amazon DynamoDB              | High-traffic web apps, e-commerce systems, gaming applications.                 |  Key-value      
| ElastiCache for Memcached    | Caching, session management, gaming leaderboards, geospatial applications.      |  In-memory     
| ElastiCache for Redis        | Easily store, manage, and deploy container images.                              |  In-memory       
| MemoryDB for Redis           | Fully managed Kubernetes service.                                               |  In-memory 
| DocumentDB (MongoDB compatibility) | Content management, catalogs, user profiles                                              | Document
| Keyspaces (Apache casandra) | High scale industrial apps for equipment maintenance, fleet management, and route optimization  | Graph


# AWS IAM 

# Shared Responsability Model

AWS created the shared responsability model:

1. AWS: Software, Compute, Storage, Database, Networking, Infraestructure, Regions, Availability Zones, Edge Locations.

2. Customers: Customer Data, Platform, Applications, OSm Network and firewall configuration, client-side Data Encryption, Server-side encryption, Networking Traffic Prottection.

## AWS Root User

> Authentication: Combination of an email address and a password to verify your identity.

> Authorization: What actions you can take, its the process of giving users permissions to access AWS resources and services. 

> Root User: Has complete access to all AWS services and resources in your account, in addition to your billing and personal information.