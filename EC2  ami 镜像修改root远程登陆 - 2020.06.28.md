# EC2  ami 镜像修改root远程登陆 - 2020.06.28

### 1、修改完 /etc/ssh/sshd_config 

```Shell
sed -i "s/PasswordAuthentication no/PasswordAuthentication yes/" /etc/ssh/sshd_config
sed -i  "s/PermitRootLogin forced-commands-only/PermitRootLogin yes/" /etc/ssh/sshd_config
```

### 2、修改 /etc/ssh/sshd_config 文件权限，不能修改

```shell
chattr +i /etc/ssh/sshd_config
```

### 3、创建AMI 

