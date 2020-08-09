# ECS capacity provider  - 2020.07.30

# 场景：ECS run 多个 task时，EC2会不够用的场景。

### 1、ASG中把 【实例保护】开起来

![71D4957C-D9E7-4C0E-B486-EE77C65B48D6](/var/folders/tj/pr8f2gh94r342pwdfm3zvxph0000gn/T/com.yinxiang.Mac/com.yinxiang.Mac/WebKitDnD.cLIsQP/71D4957C-D9E7-4C0E-B486-EE77C65B48D6.png)

### 2、ASG下方的实例也开起来

![793339B6-74C6-4B7E-973F-2488F6EFE408](/var/folders/tj/pr8f2gh94r342pwdfm3zvxph0000gn/T/com.yinxiang.Mac/com.yinxiang.Mac/WebKitDnD.EdhUQd/793339B6-74C6-4B7E-973F-2488F6EFE408.png)

### 3、在ECS控制台里面，点击 【集群】，选择 【Capacity Providers】，然后新建一个，配置如下：

![422C1F2B-05BB-4A5F-8094-6242E02381DA](/var/folders/tj/pr8f2gh94r342pwdfm3zvxph0000gn/T/com.yinxiang.Mac/com.yinxiang.Mac/WebKitDnD.ERbDb9/422C1F2B-05BB-4A5F-8094-6242E02381DA.png)