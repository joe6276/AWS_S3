# S3 Versioning

## Problem 
If we delete a file, the file will be gone forever, 
also if we try to upload files with the same name, then the older one will be overridden. 
And this is why versioning was created.

Versioning is enabled on a bucket and not on objects.

## Versioning States

### Unversioned 
This is the default state; it means that versioning is not enabled.

### Versioning Enabled 
This is where versioning is enabled. Once enabled, versioning cannot be disabled can only be suspended.
### Versioning Suspended
This means versioning is now not enabled.

## How versioning Works
When you enable versioning to a bucket and a file with the same key is uploaded, 
it is given a newer version ID.
The newest version of an object is the latest/current version. This is the version the user will see.
If versioning is disabled, the version ID of files will be set to NULL.

## Deleting File Versions
When you delete an object, a delete Marker is set to that object;
it does not delete anything, it makes it look like its deleted.
To undelete, you delete the Delete Marker
If you specify the object and the version then the object is permanently deleted.

## Versioning Price
You will be charged for all the versions that are there in your bucket.
If you have two objects, one 15 GB and the Other 10 GB, you will be charged for 25 GB.
![Image_21.png](image_21.png)

## Version Suspending 

When versioning is suspended, all the previous versions are going to remain  but moving forward when you upload
a new object, it's going to have a version id of NULL.

## Multi-Factor Authentication (MFA) Delete
This is some extra security layer required to change the versioning state of the bucket.
MFA is required also to delete versions and can only be enabled using CLI.


