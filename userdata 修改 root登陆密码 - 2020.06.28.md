# userdata 修改 root登陆密码 - 2020.06.28

## 无密钥对

```Shell
Content-Type: multipart/mixed; boundary="//"
MIME-Version: 1.0


--//
Content-Type: text/cloud-config; charset="us-ascii"
MIME-Version: 1.0
Content-Transfer-Encoding: 7bit
Content-Disposition: attachment; filename="cloud-config.txt"


#cloud-config
cloud_final_modules:
- [scripts-user, always]


--//
Content-Type: text/x-shellscript; charset="us-ascii"
MIME-Version: 1.0
Content-Transfer-Encoding: 7bit
Content-Disposition: attachment; filename="userdata.txt"


#!/bin/bash -xe
service amazon-ssm-agent restart
echo cstorfs|passwd --stdin root
sed -i "s/PasswordAuthentication no/PasswordAuthentication yes/" /etc/ssh/sshd_config
sed -i "s/PermitRootLogin forced-commands-only/PermitRootLogin yes/" /etc/ssh/sshd_config
service sshd restart
service memcached restart
echo '1234' > /root/2.txt
--//

```

