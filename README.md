# ec2-cf
Cloudformation EC2 Template in JSON

Create the CF stack from the AWC CLI:

```bash
aws cloudformation create-stack --stack-name myteststack --template-body file:///Users/TEMPLATEPATH/ec2.json --parameters ParameterKey=KeyName,ParameterValue=basicSSHKVW2 ParameterKey=InstanceType,ParameterValue=t2.micro --profile=default --region=us-west-2
```

Login to the newly created instance:

```bash
ssh -i ~/SSH-PEM-PATH/basicSSHKVW2.pem ubuntu@INSTANCE-NAME-OR-IP-ADDRESS
```

