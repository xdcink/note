# K12 Topic Logs 解法 - 2020.8.8

### 1、在 lambda中打印logs



### 2、lambda 代码

```Python
import json


def lambda_handler(event,context):
    try:
        msg =json.loads(event['body'])
        sg = msg['secret_code']
        print("secret " + sg)
    except:
        print("NO")
    return {
        "statusCode": 200,
        "headers": {
            "Content-Type": "application/json",
        },
        "body": json.dumps(event, indent=4),
    }
```

3、编写 Shell脚本

```Shell
#!/bin/bash
while:
do
# cat conf.toml |grep code |awk '{print $3}'|sed $'s/\"//g'
confcode=`cat /root/conf.toml |grep code |awk -F '=' '{print $2}'|sed $'s/\"//g'`
apicode=`aws logs filter-log-events --log-group-name /aws/logput |grep secretcode|awk '{print $3}'|awk -F '\' 'END {print $1}'`
if [ $confcode = $apicode ];then
    echo "True"
else
    echo "False"
    sed -i s/$confcode/$apicode/g /root/conf.toml
    # kill -9 `pgrep server_k12`
    # killall server_k12
    kill -9 `ps -ef|grep server_k12|grep -v grep |awk '{print $2}'`
    /root/server_k12 &
fi
sleep 3
done
```

