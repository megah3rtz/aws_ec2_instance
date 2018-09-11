# AWS Cloudformation to start and EC2 instance in an autoscaling group, and run ansible localy on the instance.

To run this, use the aws cli :-

Create the S3 Bucket you need

```
aws s3 mb my-test-bucket-for-ansible
```

Upload the ansible to the bucket :-
```
aws s3 sync ./ansible s3://my-test-bucket-for-ansible
```