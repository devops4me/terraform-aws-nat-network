
# Example | create subnet network in existing vpc

In this example you first find the VPC you need to gatecrash and find the following attributes.



## Check Public IP Address from Private Subnet

To check which public IP address our services in private subnets present as we SSH into the private subnet machine and then **dig it** out.


### Copy the private key into the ec2 instance within the private subnet.

```
scp -C \
    -i ~/.ssh/<<private-key-name>>.pem \
    ~/.ssh/<<private-key-name>>.pem \
    ubuntu@<<ec2-public-dns-name>>:/home/ubuntu/gc-example-keypair.pem
```

## Dig out the public IP address


```
dig +short myip.opendns.com @resolver1.opendns.com
dig TXT +short o-o.myaddr.l.google.com @ns1.google.com
dig TXT +short o-o.myaddr.l.google.com @ns1.google.com | awk -F'"' '{ print $2}'
```
