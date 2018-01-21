# AWS - Amazon Web Services
### S3 Bucket
+ Its used for storage in the form of objects(files, images, videos, BLOBs etc)
+ Cannot install OS and run, S3 doesnot serve this purpose it will be extremly slow.
+ Basically S3 bucket is like folder which has many files, images etc.
+ The bucket name should be globally uniquie i.e. cannot have two bucket with same name.
+ Unlimited storage and files can be from 0 Bytes - 5 TB
+ *https//3-[**aws-region**].amazonaws.com/[**bucket_name**]* is the URL format it follows.
+ When you put a new file in bucket it is immedialty available for READ.
+ When you update or delete a file it can take some time(milli seconds depending on size of the file) to reflect in bucket globally.
+ Bucket will show you either old data or new data, there is no partial broken data that is shown in the bucket in case of update or delete operation.
+ We can encrypt data in S3 we have several methods to do so.
    + In transit (when data is in network and is done via SSL/TLS)
    + At Rest
        + Server Side Encryption 3 ways:
            + S3, managed keys SSE-S3
            + AWS Key Management Service, managed keys SSE-KMS
            + Customer provided keys SSE-C
        + Client Side Encryption:
            + It basically you encrpty the data on client side and then upload to S3.
    
+ By default the S3 bucket is private and the objects stored in it are also private.
+ S3 Transfer acceleration
+ Different tiers of S3 buckets are:
	+ S3 (immediatly availabe, durable, frquently accessed)
	+ S3-IA (immediatly availabe, durable, not frquently accessed) 
	+ S3- Reduced Reduncany Storage (data that can be reproducable like thumbnails)
	+ Glaciers- Data archived ( wait upto 5 hours to access data) Cheapest of all.
+ Amazon guarantee 99.99% availability and 99.99999999999% durability for S3.
+ The object stored in S3 bucket has following core properties:
    + Key (actual name of the object)
    + Value (actual data in bytes)
    + Version (if modified we have access to old data via versioning)
        + If versioning is enabled then it cant be deleted rather it can be suspended.
        + It stores all the version of objects of update or delete.
        + If you delete an object from S3 version enabled bucket you can there is an delete marker triggerd on this object.
        + If you delete the delete marker then you can recover the object back in bucket.
        + Versioning MFA delete capability which uses multi-factor autentication adds extra layer of security.
	+ Metadata (data about data when was created and so on)
	+ Sub-resources
		+ Access control list (who can access this data)
		+ torrent (has torrent protocols)
+ Upon successful upload of object in bucket it generates 200 status code.
+ S3 Cross Region Replication - Enables you to copy your bucket from one region to another
    + To copy the content of the bucket use aws cli and cp command.
    + Regions must be unique.
    + Delete markers are replicated and deleting these markers are not replicated.
+ S3 Life cycley management, this enables you to move your objects to S3-IA or Glacier after the number of days you mentioned and finally permanently delete it. Its good for making an enterprise a cost effective by managing the life cycle of objects. 


----

### CloudFront CDN Content Delivery Network
+ Suppose you have file uploaded to your bucket in London location and some one is trying to access this file from Australia then there is lot of latency in doing so for each request that is being made by users. So CDN allows you to cache your object in the edge location near Australia which enables faster access except for the first user until its cached in edge location.
+ By default its cached for 24 hours and controlled via TTL (Time To Live).
+ There are two types of distribution(also called as CDN):
    + Web
    + RTMP (for adobe, flash, videos)
+ You can also add or update or delete via distribution(CDN).
+ You can also restrict the distribution viewers access via signed urls or signed cookies.
+ You can also turn on the logging information and store them in different bucket.


----

### IAM Identity and Access Management
+ It basically consists of:
    + Users
    + Groups
    + Roles
    + Policy documents (JSON fromat)
+ IAM is universal and not region wise for one account.
+ New Users will have no permission when they are first created, you can assign them.
+ **Access key** id and **Secret Access key** are created one time per user for accessing aws via CLI or API.
+ Passwords used to login from console for users are not the same as these keys.
+ Access key and Secret Access key can be viewed only once if you loose them you have to regenerate them for that user.


