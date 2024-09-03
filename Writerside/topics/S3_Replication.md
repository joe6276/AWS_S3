# S3 Replication
S3 replication is when you have a source bucket, and you want data synced to another bucket.

## Uses of Replication
- Ensures data protection
- Is a compliance requirement
- Helps store data closer to users
- Keeps data near their servers

## Types of Replication 

### Same-Region Replication 
When you are replicating from one bucket to another in the same region.

### Use Cases
![SRR](image_31.png)
### Cross-Region Replication
When you are replicating from one bucket to another in a separate region
### Use Cases {id="use-cases_1"}
![CRR](image_32.png)

### Multi-Destination Replication
When replicating from one region to more that one region.


## Bidirectional Replication
Replication by default is one way, but it can be bidirectional if configured manually.

## Replication Requirement

![Requirement](image_33.png)


## Other Details
- Only objects created after enabling replication will be replicated
- Objects with encryption enabled will be replicated
- Object in the S3 Glacier Flexible Retrieval and S# Glacier Deep Archive storage classes do not get replicated.
- Object metadata and tags will be replicated
- After replication, objects can be moved from one storage class to another

## Deletion with Replication
- By default delete markers do not get replicated
(Enable delete marker replication)
- If a specific version of an object is deleted on the source bucket, that version will not be deleted 
- on the destination bucket (This protects data from malicious deletions)

## Replication Time Control 
- Replication does not occur instantly and can take some time before a file shows up in  the destination bucket.
-  S3 Replication Time Control (S3 RTC) replicated objects within 15 minutes (Great for meeting compliance or business requirements)