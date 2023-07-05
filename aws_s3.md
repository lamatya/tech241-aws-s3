# AWSCLI
The AWS Command Line Interface (CLI) is a tool from Amazon Web Services (AWS) that lets you control and automate your AWS resources using commands in a command prompt or terminal on your computer. It's like a text-based interface that allows you to manage and automate your AWS services without using a graphical user interface.


## How to install awscli


Step 1: go to pychar and download and install the AWS CLI

```
pip install awscli
```

Step 2: Configure the AWS CLI:

```
aws configure
```

Step3: Run the command aws configure.

Enter your;

1. **AWS Access Key ID**:

2. **Secret Access Key (provided by AWS).**

3. **Choose your preferred region**

4. **Set the output format**


# s3 Bucket

An S3 bucket, in the context of AWS, is a storage container provided by Amazon S3 (Simple Storage Service) to store and retrieve objects such as files, documents, images, and videos. It is like a folder or directory where you can organize and store your data securely in the cloud.

s3 bucket is equivalent to blob storage in azure......

**To use s3 command we need to install boto3 using ;
```
pip install boto3
```
To see the s3 bucket contents:
```
aws s3 ls s3://bucket-name--bucket-name is the name of your bucket.
```

To upload a file to an S3 bucket:

```
aws s3 cp file-path s3://bucket-name
```
To download a file from an S3 bucket:
```
aws s3 cp s3://bucket-name/file-path
```
To delete a file from an S3 bucket:
```
aws s3 rm s3://bucket-name/file-path
```

To delete a bucket (only if it's empty):
```
aws s3 rb s3://bucket-name
```

# Creating s3 Bucket

**First thing is to install the required boto3 library**
```
import boto3
```
**Set up an s3 connection**
```
s3 = boto3.client("s3")
```
**create a bucket, in the eu-west-1 region**
```
bucket_name = s3.create_bucket(Bucket= "tech241-larisha-python-bucket", CreateBucketConfiguration={"LocationConstraint":"eu-west-1"})
```

**print bucket name to confirm working script.**
```
print(bucket_name)
```


# Uploading file to a bucket
```
import boto3
```
```
s3 = boto3.client("s3")
```
```
bucketCont = s3.upload_file("testfile.txt", "tech241-larisha-python-bucket", "uploadfile.txt")
```
```
print(bucketCont)
```
# Downloading file to a bucket
```
import boto3
```

**Create an S3 client**
```
s3 = boto3.client('s3')
```
**Set the bucket name and file path**
```
bucket_name = 'tech241-larisha-python-bucket'
```
```
file_path = 'uploadfile.txt'
```
```
local_file_path = 'downloadedFile.txt'
```

# Deleting file from a bucket

```
import boto3
```
```
s3 = boto3.client('s3')
```
```
response = s3.delete_object(Bucket="tech241-larisha-python-bucket", Key="uploadfile.txt")
```
```
print(response)
```
# Deleting Bucket
```
import boto3
```
```
s3 = boto3.resource("s3")
```
```
bucket = s3.Bucket("tech241-larisha-python-bucket")
```
```
response = bucket.delete()
```
```
print(response)
```