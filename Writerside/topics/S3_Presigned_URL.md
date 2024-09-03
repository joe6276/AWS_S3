# S3 Pre-Signed URL
![Pre-Signed URL](image_37.png)

By default, the owner of the bucket has access to the S3 buckets; but assuming that they wanted to
give access to a public user, how do we do it?

Make the bucket public? (well will work but not a great approach)

## Pre-Signed URL
This is a URl that has the user authentication details in the URL, This will trick S3 to think  the user accessing the bucket.
![Pre-Signed URL](image_39.png)

- When creating a pre-signed URLs, an expiration date must be provided.
- Expiration duration of maximum 7 days using an IAM user is provided.
- If an IAM user does not have access to an S3 bucket, a pre-signed URL can still be generated using that account
- The Pre-signed URL does not give you access to a bucket; however, it allows you to send a request to S3 as the user that generated the URL.
- Any other user with IAM role for S# can generate a URL, but it won't work.
