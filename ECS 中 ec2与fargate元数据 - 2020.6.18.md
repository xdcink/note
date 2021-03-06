# ECS 中 ec2与fargate元数据 - 2020.6.18

### ec2 类型

```Python

{
    "Cluster":"ec2-task-test",
    "TaskARN":"arn:aws-cn:ecs:cn-northwest-1:134898497215:task/14e4df89-c113-4911-ab46-296d641eda21",
    "Family":"ec2-meta-v2",
    "Revision":"1",
    "DesiredStatus":"RUNNING",
    "KnownStatus":"CREATED",
    "Limits":{
        "CPU":0.2421875,
        "Memory":500
    },
    "PullStartedAt":"2020-06-18T06:42:26.642431336Z",
    "PullStoppedAt":"2020-06-18T06:42:26.766867092Z",
    "AvailabilityZone":"cn-northwest-1b",
    "Containers":[
        {
            "DockerId":"10a9d4dcacb4b97584ab92ad1e5af106a39cd159f22ee57ed073df0ea4379cc8",
            "Name":"asdasd",
            "DockerName":"ecs-ec2-meta-v2-1-asdasd-b08ec5d8b6e5c7caf201",
            "Image":"134898497215.dkr.ecr.cn-northwest-1.amazonaws.com.cn/xc:ec2-meta-v2",
            "ImageID":"sha256:cda17ce97542c00aa1e0b664277089436a76ec2051ea8d69ca3420b516f39c9c",
            "Ports":[
                {
                    "ContainerPort":7777,
                    "Protocol":"tcp",
                    "HostPort":81
                }
            ],
            "Labels":{
                "com.amazonaws.ecs.cluster":"ec2-task-test",
                "com.amazonaws.ecs.container-name":"asdasd",
                "com.amazonaws.ecs.task-arn":"arn:aws-cn:ecs:cn-northwest-1:134898497215:task/14e4df89-c113-4911-ab46-296d641eda21",
                "com.amazonaws.ecs.task-definition-family":"ec2-meta-v2",
                "com.amazonaws.ecs.task-definition-version":"1"
            },
            "DesiredStatus":"RUNNING",
            "KnownStatus":"CREATED",
            "Limits":{
                "CPU":0,
                "Memory":254
            },
            "CreatedAt":"2020-06-18T06:42:26.773401792Z",
            "Type":"NORMAL",
            "Networks":[
                {
                    "NetworkMode":"default",
                    "IPv4Addresses":[
                        ""
                    ]
                }
            ]
        }
    ]
}
```

### fargate类型

```Python
{
    "Cluster":"arn:aws-cn:ecs:cn-northwest-1:134898497215:cluster/f-c",
    "TaskARN":"arn:aws-cn:ecs:cn-northwest-1:134898497215:task/a85e6fdb-3c97-4774-a8e3-c9f1f8ae6276",
    "Family":"fargate-metadata-a",
    "Revision":"1",
    "DesiredStatus":"RUNNING",
    "KnownStatus":"RUNNING",
    "Containers":[
        {
            "DockerId":"a85e6fdb-3c97-4774-a8e3-c9f1f8ae6276-598753618",
            "Name":"metadata-1",
            "DockerName":"metadata-1",
            "Image":"134898497215.dkr.ecr.cn-northwest-1.amazonaws.com.cn/xc:a-v1",
            "ImageID":"sha256:e26bc180187347bc713e454d8c02a921e36f9fdd91747c780fc4edceef0b5d3c",
            "Labels":{
                "com.amazonaws.ecs.cluster":"arn:aws-cn:ecs:cn-northwest-1:134898497215:cluster/f-c",
                "com.amazonaws.ecs.container-name":"metadata-1",
                "com.amazonaws.ecs.task-arn":"arn:aws-cn:ecs:cn-northwest-1:134898497215:task/a85e6fdb-3c97-4774-a8e3-c9f1f8ae6276",
                "com.amazonaws.ecs.task-definition-family":"fargate-metadata-a",
                "com.amazonaws.ecs.task-definition-version":"1"
            },
            "DesiredStatus":"RUNNING",
            "KnownStatus":"RUNNING",
            "Limits":{
                "CPU":2
            },
            "CreatedAt":"2020-06-15T06:31:11.467736716Z",
            "StartedAt":"2020-06-15T06:31:11.467736716Z",
            "Type":"NORMAL",
            "Networks":[
                {
                    "NetworkMode":"awsvpc",
                    "IPv4Addresses":[
                        "172.31.26.246"
                    ]
                }
            ]
        }
    ],
    "Limits":{
        "CPU":0.25,
        "Memory":512
    },
    "PullStartedAt":"2020-06-15T06:31:10.173120329Z",
    "PullStoppedAt":"2020-06-15T06:31:10.680716442Z",
    "AvailabilityZone":"cn-northwest-1b"
}
```

