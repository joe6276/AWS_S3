# Using CLI

Let's see how we can work with S3 using the CLI

### To List all Buckets in your aws account:
```Javascript
aws s3 ls
```
### Create a New Bucket
This will create a new bucket named newbucket in the us-east-1 region

mb: make bucket
```Docker
aws s3 mb s3://newbucket --region us-east-1
```

### Delete Bucket

rb: remove bucket
```Docker
aws s3 rb s3://newbucket
```
<tip>
The above command won't work if the buckets contains files
</tip>
To delete buckets containing files use the --force command

```Docker
aws s3 rb s3://newbucket --force
```
### List objects in Bucket

```Docker
aws s3 ls s3://newbucket
```
To print all the files within a directory recursively use
the --recursive flag.

```Docker
aws s3 ls s3://newbucket --recursive
```
### Copy Files
To copy files from my local machine to S3 Bucket, the files will still remain


```Docker
aws s3 cp file1 s3://newbucket
```
To copy from S3 to local machine

```Docker
aws s3 cp  s3://newbucket/file1 /testFolder
```
To copy from Bucket to another bucket

```Docker
aws s3 cp  s3://newbucket/file1 s3://bucket2
```

### Delete objects

```Docker
aws s3 rm s3://bucket/test.html
```

### Copy Folder
This will copy an entire folder to the S3 bucket
```Docker
aws s3 cp media/ s3://newbucket --recursive
```
From Bucket to local
```Docker
aws s3 cp s3://newbucket  /media/ --recursive
```
From Bucket to Bucket

```Docker
aws s3 cp s3://newbucket/media   s3://bucket2/media  --recursive
```

### Move Files
With move command it will remove the local copy permanently to the destination bucket/folder
```Docker
aws s3 mv file1 s3://newbucket 
```
Bucket to local
```Docker
aws s3 mv  s3://newbucket/file1 /testFolder 
```
Bucket to Bucket

```Docker
aws s3 mv  s3://newbucket/file1 s3://bucket2
```
You can do the same with folder, you will just use --recursive command.

###  Sync
Will make sure your directory is in Sync with your bucket
```Docker
awa sync / s3://bucket
```