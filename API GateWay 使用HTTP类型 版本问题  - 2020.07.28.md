# API GateWay 使用HTTP类型 版本问题  - 2020.07.28

Lambda版本集成使用版本

### V1 

print(event)

```python
{'version': '1.0', 'resource': '/', 'path': '/', 'httpMethod': 'GET', 'headers': {'Content-Length': '0', 'Host': 'orp6rjioyi.execute-api.cn-northwest-1.amazonaws.com.cn', 'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.89 Safari/537.36', 'X-Amzn-Trace-Id': 'Root=1-5f1f9f03-bc377af584022475591234b4', 'X-Forwarded-For': '221.226.74.202', 'X-Forwarded-Port': '443', 'X-Forwarded-Proto': 'https', 'accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9', 'accept-encoding': 'gzip, deflate, br', 'accept-language': 'zh-CN,zh;q=0.9,zh-TW;q=0.8', 'sec-fetch-dest': 'document', 'sec-fetch-mode': 'navigate', 'sec-fetch-site': 'none', 'sec-fetch-user': '?1', 'upgrade-insecure-requests': '1'}, 'multiValueHeaders': {'Content-Length': ['0'], 'Host': ['orp6rjioyi.execute-api.cn-northwest-1.amazonaws.com.cn'], 'User-Agent': ['Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.89 Safari/537.36'], 'X-Amzn-Trace-Id': ['Root=1-5f1f9f03-bc377af584022475591234b4'], 'X-Forwarded-For': ['221.226.74.202'], 'X-Forwarded-Port': ['443'], 'X-Forwarded-Proto': ['https'], 'accept': ['text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9'], 'accept-encoding': ['gzip, deflate, br'], 'accept-language': ['zh-CN,zh;q=0.9,zh-TW;q=0.8'], 'sec-fetch-dest': ['document'], 'sec-fetch-mode': ['navigate'], 'sec-fetch-site': ['none'], 'sec-fetch-user': ['?1'], 'upgrade-insecure-requests': ['1']}, 'queryStringParameters': None, 'multiValueQueryStringParameters': None, 'requestContext': {'accountId': '134898497215', 'apiId': 'orp6rjioyi', 'domainName': 'orp6rjioyi.execute-api.cn-northwest-1.amazonaws.com.cn', 'domainPrefix': 'orp6rjioyi', 'extendedRequestId': 'QXXIhgLz5PgEPZw=', 'httpMethod': 'GET', 'identity': {'accessKey': None, 'accountId': None, 'caller': None, 'cognitoAuthenticationProvider': None, 'cognitoAuthenticationType': None, 'cognitoIdentityId': None, 'cognitoIdentityPoolId': None, 'principalOrgId': None, 'sourceIp': '221.226.74.202', 'user': None, 'userAgent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.89 Safari/537.36', 'userArn': None}, 'path': '/', 'protocol': 'HTTP/1.1', 'requestId': 'QXXIhgLz5PgEPZw=', 'requestTime': '28/Jul/2020:03:44:03 +0000', 'requestTimeEpoch': 1595907843210, 'resourceId': 'GET /', 'resourcePath': '/', 'stage': '$default'}, 'pathParameters': None, 'stageVariables': None, 'body': None, 'isBase64Encoded': False}

```



### V2

print(event)

```python
{'version': '2.0', 'routeKey': 'GET /', 'rawPath': '/v1/', 'rawQueryString': '', 'headers': {'accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9', 'accept-encoding': 'gzip, deflate, br', 'accept-language': 'zh-CN,zh;q=0.9,zh-TW;q=0.8', 'cache-control': 'max-age=0', 'content-length': '0', 'host': 'orp6rjioyi.execute-api.cn-northwest-1.amazonaws.com.cn', 'sec-fetch-dest': 'document', 'sec-fetch-mode': 'navigate', 'sec-fetch-site': 'none', 'sec-fetch-user': '?1', 'upgrade-insecure-requests': '1', 'user-agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.89 Safari/537.36', 'x-amzn-trace-id': 'Root=1-5f1f9f00-5282ef5227be61cc32897711', 'x-forwarded-for': '221.226.74.202', 'x-forwarded-port': '443', 'x-forwarded-proto': 'https'}, 'requestContext': {'accountId': '134898497215', 'apiId': 'orp6rjioyi', 'domainName': 'orp6rjioyi.execute-api.cn-northwest-1.amazonaws.com.cn', 'domainPrefix': 'orp6rjioyi', 'http': {'method': 'GET', 'path': '/v1/', 'protocol': 'HTTP/1.1', 'sourceIp': '221.226.74.202', 'userAgent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.89 Safari/537.36'}, 'requestId': 'QXXIFgRJ5PgEPNA=', 'routeKey': 'GET /', 'stage': 'v1', 'time': '28/Jul/2020:03:44:00 +0000', 'timeEpoch': 1595907840486}, 'isBase64Encoded': False}

```

