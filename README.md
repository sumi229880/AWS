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
	+ Metadata (data about data when was created and so on)
	+ Sub-resources
		+ Access control list (who can access this data)
		+ torrent (has torrent protocols)
+ Upon successful upload of object in bucket it generates 200 status code.


