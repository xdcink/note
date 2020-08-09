# ECS使用 efs坑 - 2020.6.15

## 问题：

挂载无权限

![5031591975061_.pic_hd](/var/folders/tj/pr8f2gh94r342pwdfm3zvxph0000gn/T/com.yinxiang.Mac/com.yinxiang.Mac/WebKitDnD.pF3XNw/5031591975061_.pic_hd.jpg)

## 解决办法：

ECS控制台可以直接使用efs挂载

####

#### ECS控制台不能使用LETEST版本，需要使用1.4版本

![853AC4AC-9FDE-413F-9030-22D372D4CA33](/var/folders/tj/pr8f2gh94r342pwdfm3zvxph0000gn/T/com.yinxiang.Mac/com.yinxiang.Mac/WebKitDnD.DwEung/853AC4AC-9FDE-413F-9030-22D372D4CA33.png)



并编写policy

```json
{
    "containerDefinitions": [
        {
            "memory": 1024,
            "portMappings": [
                {
                    "hostPort": 80,
                    "containerPort": 80,
                    "protocol": "tcp"
                }
            ],
            "essential": true,
            "mountPoints": [
                {
                    "containerPath": "/root",
                    "sourceVolume": "efs-html"
                }
            ],
            "name": "nginx",
            "image": "nginx"
        }
    ],
    "volumes": [
        {
            "name": "efs-html",
            "efsVolumeConfiguration": {
                "fileSystemId": "fs-273ffac2"
            }
        }
    ],
    "family": "efs-tutorial"
}
```

