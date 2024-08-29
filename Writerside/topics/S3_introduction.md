# Amazon S3
## What is S3 
Amazon S3 is a simple storage service. It's more like Google Drive and DropBox.

_But we have different types of storage in AWS_
We have:
- File storage (EFS)
- Object-based Storage (S3)
- Block-based Storage (EBS)

### File Storage
Best for shared access to files, using hierarchical structures.
### Object Storage
Best for scalable, unstructured data with metadata, accessed via REST APIs.
### Block-based Storage
Best for low-latency applications requiring consistent performance, used as virtual hard drives. This supports booting .

## S3 Use Cases
![Use Cases](image.png)

## Traditional Way of File Storage
Traditionally you had a server with your website files (HTML, CSS, JavaScript), and also your media were
stored in the same location e.g.(Videos). This way is not efficient, especially with scalability.
![Traditional](image_2.png)

_So how do we solve this?_

## S3
Which S3 you can separate your media from your server, your server can hold the: HTML, CSS and JavaScript that are responsible for loading the website
then the Media Files can be stored in a S3. Every time you want to show a video on your website,
you can make a request to your S3 bucket.
![S3](image_1.png)

_let's check on some terminologies_

## What is a Bucket in S3
A bucket is more of a folder, and you can have multiple folders(so multiple buckets)

## What is an Object in S3
An Object is a file uploaded to S3 
An Object has:
- Key: The file name
- Value: The file data
![Object](image_3.png)


## S3 Folder structure
S3 has a flat folder structure. Here you just have one folder(bucket) that cant have folder structure.
The only way to create a 'folder structure like structure' is using the key name and appending a name e.g. music/song name 
![Folder structure](image_4.png)


## Availability
S3 buckets are going to be replicated in several availability zones 
that mean that if one AZ is down, there is still a copy of the bucket in other AZ; 
hence no downtime will be experienced.

![AZ](image_5.png)

## S3 Bucket Names
S3 bucket names must be unique globally across all AWS accounts. The reason is the bucket name is part of the URL
so two buckets should not have the same names.
![Bucket Names](image_6.png)

## S3 Bucket Restrictions

- S3 can handle unlimited number of objects
- The maximum size of a single file is 5TB
- An AWS account supports 100 buckets by default, but this number can be increased to 1,00 by requesting a service limit increase.
