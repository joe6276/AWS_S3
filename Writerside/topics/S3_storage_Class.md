# S3 Storage Classes
S3 has different classes because the following factors make S3 Classes different:
- Data Access
- Resiliency
- Cost
### S3 Standard(Default)
- This can handle two simultaneous AZ failures because data is stored across multiple AZs
- This is the most expensive S3 storage class
- Data will be accessed instantly
- You will be charged based on the number of gigabytes you use in a month.

if you don't need to access data frequently you can use:
### S3 Standard-IA
- This can handle two simultaneous AZ failures because data is stored across multiple AZs
- You will be charged based on the number of gigabytes you use in a month.
- Cheaper that standard
- You have a retrieval fee
- Has a minimum duration charge of 90 days -If you store an object in these classes
  and delete it before the minimum duration ,you will still be charged as if the object was stored for the full 90 days.

- Minimum size charge of 128 KB per object- If you store an object in these storage classes that is smaller than 128 KB, Amazon S3 will still charge you as if the object were 128 KB in size.
- If data is accessed frequently or files are too small then you will pay more

### S3 One Zone-IA
- Similar to S3 Standard IA but the difference is data is stored in one Availability Zone but replicated in  multiple data centers
  which makes it cheaper
- You have a retrieval fee
- Has a minimum duration charge of 90 days
- Minimum size charge of 128 KB per object

### S3 Glacier-Instant

- This can handle two simultaneous AZ failures because data is stored across multiple AZs
- Low-cost option for rarely accessed data
- Performance same as that of S3 standard
- You have a retrieval fee but higher that the previous ones.
- Has a minimum duration charge of 90 days
- Minimum size charge of 128 KB per object
- Cheaper than the previous
-
### S3 Glacier-Flexible
- This can handle two simultaneous AZ failures because data is stored across multiple AZs
- Data is not immediately available , it takes sometime to retrieve the data
- You have a retrieval fee
- How long to wait for the data to be retrieved depends on the option selected:
    - Bulk : 5-12 Hours
    - Expedited: 1-5 Minutes
    - Standard: 3-5 Hours
      ( The less the time the higher the cost)
    - During retrieval data is stored in  S3 standard-IA class temporarily.
- Has a minimum duration charge of 90 days
- Minimum size charge of 40 KB per object

### S3 Glacier Deep Archive
Cheapest storage class in S#
- You have a retrieval fee
- How long to wait for the data to be retrieved depends on the option selected:
    - Bulk : 12Hours
    - Standard: 48Hours
- Has a minimum duration charge of 90 days
- Minimum size charge of 40 KB per object


What happens when you don't know the storage class to use?

## S3 Intelligent-Tiering

- Here AWS will analyse the access pattern on a file and move it to a fitting category.
- Automatically reduces storage costs by intelligently moving data to the most cost-effective access tier
- Apart from the cost of the storage class and all objects also incur a monitoring/automation cost per 1,000 objects.

## How to Select the Best Storage Class
How do you select the best storage class , use the diagram below to guide you.
![image_84.png](image_84.png)
