# S# Object Lock 

- Prevent user from permanently deleting or overwriting user data
- It meets regulatory requirements
- Also enforces write-once-read-many (WORM) model
- You can lock an object or all object

## Object Lock Modes
### Governance Mode

- Most users can't delete or modify a locked object or modify lock setting of an object. 
- The only people who can bypass this are users with Bypass Governance retention.
![Governance Mode](image_40.png)

### Compliance Mode 
- All users can't delete or modify a locked object or modify lock setting of an object during the retention period, Not even the root user
![Compliance Mode](image_42.png)

### Legal Hold

- Most users can't delete or modify a locked object or modify lock setting of an object.
- The only people who can bypass this are users with PutObjectLegalHold Permission 
#### Use Case
- Documents used during active litigation


## To use Object Lock
- Versioning must be enabled in the bucket
- Object locking on the bucket must be enabled
