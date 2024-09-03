# S3 Encryption
This is to scramble data so that only authorized parties can understand the information.

## Types of Encryption
![encryption](image_34.png)
Where Do we need to focus on encryption:

When we are sending data to and from S3, we need to make sure that the data is encrypted, and this is already taken care of by SSL/ TLS. This is called **In Transit.**

The S3 bucket at the end of the day it's going to store data in a server hosted by AWS. When we store on the server, we have to make sure it's encrypted.
This is what we refer to as **Encryption at Rest** 

##  Client-Side Vs Server-Side Encryption

### Client-side Encryption
This is where you as the client encrypt the file and store it in an S# bucket when its already encrypted.

### Server-Side Encryption
Here we take a file then send it to S3 (here it's already safe because of SSl/TLS) the S3 will now encrypt the file

_Our Focus will be on Server side encryption_

## Encryption Methods
S3 supports three types of encryption:
- Server-side encryption with Amazon S3-Managed Keys (SSE-S3)- default.
- Server-side encryption with Customer-Provided Keys (SSE-C)
- Server-side encryption with Key Management Service Keys (SSE-KMS)

There are two parts involved in handling encryption and decryption:
- Generating and Managing the keys
- Using the Keys to perform encryption and Decryption

The method to use depends on what you want to be responsible for vs what AWS should be responsible for.

Note about encryption
<tip>
Encryption occurs on per an object basis (One Object can use one type of encryption, while another object can use a different type) 

A default encryption method can be configured on a bucket( All objects where user does not specify the encryption method will use the bucket default encryption)

</tip>

## SSE-S3 Encryption
- Here, Generating and Managing the keys and encryption and Decryption will be handled by AWS 
- For every object we upload, there will ke a key created by the root key to encrypt the object, then the encrypted key and the object will be stored together
- To decrypt the root key, is going to decrypt the encrypted key, and once we have the key, we will decrypt the file and send the file back to the user.

## SSE-KMS
- SSE-KMS instead of having the root key managed by AWS is managed by Key Management Service.
- The KMS will generate unique keys for every object and also manage the Keys.
- The Encryption and decryption is handled by AWS.

## SSE-C
- The customer will generate and manage the key 
- We upload the object and the key
- S3 will take the Key and object and Encrypt the object
- Then it will hash the key and store the hash and the object on the server
- AWS will still be responsible for encrypting and decrypting

_But how do we send the key?_
## Headers
![Headers](image_35.png)


## Summary
![Summary](image_36.png)