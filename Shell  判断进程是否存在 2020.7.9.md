# Shell  判断进程是否存在 2020.7.9



```Shell
#!/bin/sh
while true;do
        count=`ps -ef|grep http|grep -v grep`
        if [ "$?" != "0" ];then
echo    ">>>>no httpd,run it"
service httpd start
else
echo ">>>>httpd is runing..."
fi
sleep 5
done
```



````Shell
#!/bin/bash
while true;do
    count=`ps -ef|grep server_demo|grep -v grep|wc -l`
    if [ $count -eq 0 ];then
        /server_demo /conf.toml
    else
        echo ">>>Done>>>"
    fi
sleep 5
done
````





```shell
REDIS_PIDS=$(ps -ef | grep redis | grep -v grep | awk '{print $2}')
if [ "$REDIS_PIDS" = "" ]; then
    Echo_Yellow "Redis is not runing."
    #运行进程
fi
```

