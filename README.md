# ec2-cf
Cloudformation EC2 Template in JSON

List running stacks in the CF:

```bash
 aws cloudformation list-stacks --profile=default --region=us-west-2 
```

Create the CF stack from the AWC CLI:

```bash
aws cloudformation create-stack --stack-name myteststack --template-body file:///Users/TEMPLATEPATH/ec2.json --parameters ParameterKey=KeyName,ParameterValue=basicSSHKVW2 ParameterKey=InstanceType,ParameterValue=t2.micro --profile=default --region=us-west-2
```

Login to the newly created instance:

```bash
ssh -i ~/SSH-PEM-PATH/basicSSHKVW2.pem ubuntu@INSTANCE-NAME-OR-IP-ADDRESS
```

Delete the stack:

```bash
aws cloudformation delete-stack --stack-name myteststack --profile=default --region=us-west-2
```

The python script used in this repo to convert the JSON template into YAML can be found here:
https://github.com/salbat/json2yaml
