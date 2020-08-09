# boto3 查找 logs  2020.8.9

### 1、Lambda代码

```Python
import json


def lambda_handler(event, context):
    # TODO implement
    try:
        print(event["body"])
    except Exception:
        pass
    return {
        'statusCode': 200,
        'headers': {
            "Content-Type": "application/json",
        },
        'body':json.dumps(event,indent=4)
    }

```

### 2、获取logs

```Python
import boto3

AK = "AKIAR62ETW27TA6OUM5M"
SK = "B52Y/Rv0h2nOYjoE695xi3gHPd9WokIHjl3YRkN3"


logs = boto3.client(
    "logs",
    region_name='cn-northwest-1',
    aws_access_key_id=AK,
    aws_secret_access_key=SK,
    aws_session_token=None
)

response = logs.filter_log_events(
    logGroupName="/aws/lambda/xcloud-code2",
    filterPattern="secret_code"  # 筛选条件
)

print(response)
print(response["events"][-1]["message"])
# 每次都取最后一个(最新) message
msg = response["events"][-1]["message"]
# out_put----->> "secret_code":"Sunday-1:13"

```

### 3、如有需要，Shell脚本



```Shell
#!/bin/bash
while:
do
confcode=`cat conf.toml |grep code |awk -F '=' '{print $2}'|sed $'s/\"//g'`
logcode=`python3 log.py |sed $'s/\"//g'|awk -F ':' '{print $2}'`
if [ $confcode = $logcode ];then
    echo "True"
else
    echo "False"
    sed -i s/$confcode/$logcode/g conf.toml
    killall server_k12
    /root/server_k12 &
fi
sleep 3
done
```

