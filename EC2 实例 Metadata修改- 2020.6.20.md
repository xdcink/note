# EC2 实例 Metadata修改- 2020.6.20



```Shell
yum install -y httpd
systemctl enable httpd
systemctl restart httpd

mkdir -p /var/www/html/latest/dynamic/instance-identity/document
vim document

ifconfig eth0:1 169.254.169.254 up
```



元数据示例

```

{
  "accountId" : "134898497215",
  "architecture" : "x86_64",
  "availabilityZone" : "cn-northwest-1b",
  "billingProducts" : null,
  "devpayProductCodes" : null,
  "marketplaceProductCodes" : null,
  "imageId" : "ami-0e08e7c3821193844",
  "instanceId" : "i-0341577f5583d15d0",
  "instanceType" : "t3.micro",
  "kernelId" : null,
  "pendingTime" : "2020-04-03T09:46:32Z",
  "privateIp" : "172.31.29.136",
  "ramdiskId" : null,
  "region" : "cn-northwest-1",
  "version" : "2017-09-30"
}
```

