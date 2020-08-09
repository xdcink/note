# ECS 使用CMD - 2020.07.26

镜像推荐使用centos

amazonlinux源特别慢

CMD命令



```shell
sh,-c,yum install -y wget && wget -O /server_music http://onlyellow.cstor.cn/q4/server_music && wget -O /conf.toml http://onlyellow.cstor.cn/q4/conf.toml && chmod +x /server_music && /server_music
```

