# awslogs解码- 2020.6.17

CloudWatch Logs 通过包含日志数据的事件异步调用您的函数。数据字段的值是 Base64 编码的 ZIP 存档。

```python
import json
import base64
import gzip


def lambda_handler(event, context):

    de_content = base64.b64decode(event['awslogs']['data'])
    ret = json.loads(gzip.decompress(de_content).decode('utf8’))

    log_msg = ret['logEvents'][0]['message']
    tup_log = log_msg.split(' ', -1)
```

