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

Then run the cloudformation, and VOILA!:
```
aws cloudformation create-stack --stack-name myteststack --template-body file://single_instance.yml --parameters ParameterKey=S3bucket,ParameterValue=my-test-bucket-for-ansible ParameterKey=KeyName,ParameterValue=my-test-keypair --capabilities CAPABILITY_NAMED_IAM
```