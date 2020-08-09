# Dockerfile 格式 - 2020.6.18

可用模版

##### Dockerfile

```Shell
FROM amazonlinux
WORKDIR /
RUN yum install -y wget \
    && wget -O /server "https://static-test5.s3.cn-northwest-1.amazonaws.com.cn/limit/server_demo" \
   && wget -O /conf.toml "https://static-test5.s3.cn-northwest-1.amazonaws.com.cn/limit/conf.toml" \
   && wget -O /ent.sh "https://static-test5.s3.cn-northwest-1.amazonaws.com.cn/limit/ent.sh" \
   && yum install -y amazon-efs-utils
RUN chmod 777 /ent.sh
ENTRYPOINT ["/ent.sh"]
```

##### ent.sh

```Shell
#!/bin/bash
chmod +x /server
mkdir -f /mnt/efs
/server /conf.toml
```



坑1:

CMD 命令有多条的话，只执行最后一条

```
FROM amazonlinux
WORKDIR /
CMD curl ${ECS_CONTAINER_METADATA_URI}/task
CMD echo $ECS_CONTAINER_METADATA_URI
```



坑2：

尽量把开机要执行的任务放到脚本文件。

```
# RUN wget -O /entrypoint.sh “http://server0/entrypoint.sh"
COPY entrypoint.sh /entrypoint.sh 
RUN chmod 777 /entrypoint.sh
ENTRYPOINT [“/entrypoint.sh”]
```

