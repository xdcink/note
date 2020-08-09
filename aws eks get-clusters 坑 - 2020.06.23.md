# aws eks get-clusters 坑 - 2020.06.23

无法描述集群与列出集群

但是可以 获取到集群的token

![33633A57-3F2B-4DC1-B686-E6A1D5D68644](/var/folders/tj/pr8f2gh94r342pwdfm3zvxph0000gn/T/com.yinxiang.Mac/com.yinxiang.Mac/WebKitDnD.89EEQk/33633A57-3F2B-4DC1-B686-E6A1D5D68644.png)



解决：

  如果VPC中存在VPCE （Endpoint）aws eks 命令会报错。

   删除VPCE就可以了。

