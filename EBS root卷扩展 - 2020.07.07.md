# EBS root卷扩展 - 2020.07.07

**file -s /dev/xvd\* 标识卷的文件系统**

### **1、扩展分区** 

注意：设备名称和分区编号之间有空格！

**growpart /dev/nvme0n1 1 （Nitro实例类型）**

**growpart /dev/xvda 1    （T2实例类型）**



### **2、扩展文件系统**

yum install -y  xfsprogs  (xfs类型，可能需要下载安装包)

**resize2fs /dev/xvda1    （EXT4类型文件系统）**

**xfs_growfs -d /      （XFS实例类型）**



## 坑1：

```shell
[root@ip-10-99-1-21 ~]# /usr/bin/growpart /dev/vda 1
unexpected output in sfdisk –version [sfdisk，来自 util-linux 2.23.2]
```

解决办法：

```
[root@ip-10-99-1-21 ~]# LANG=en_US.UTF-8
```

然后从第一步开始。