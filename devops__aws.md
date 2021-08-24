## CLI

### Adding Ip from Security Group
https://docs.aws.amazon.com/cli/latest/reference/ec2/authorize-security-group-ingress.html#authorize-security-group-ingress
```bash
aws ec2 authorize-security-group-ingress --group-id sg-XXXX --protocol -1 --cidr X.X.X.X/32 --profile name
```
### Removing Ip from Security Group
https://docs.aws.amazon.com/cli/latest/reference/ec2/revoke-security-group-ingress.html#revoke-security-group-ingress
```bash
aws ec2 revoke-security-group-ingress --group-id sg-XXXX --protocol -1 --cidr X.X.X.X/32 --profile name
```

### Sample Retails AWS application
https://github.com/aws-samples/retail-demo-store
