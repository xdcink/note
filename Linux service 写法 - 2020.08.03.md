# Linux service 写法 - 2020.08.03

### Examples

cat /etc/systemd/system/lbserver.service

```Shell
[Unit]
Description=go server


[Service]
TimeoutStrat=0
ExecStart=/root/csotr_server/server_demo /root/cstor_server/conf.toml
LimitNOFILE=88888
LimitNPROC=8888


[Install]
WantedBy=multi-user.target
```

