# 服务启停

使用由Websoft9提供的 ActiveMQ 部署方案，可能需要用到的服务如下：

## ActiveMQ

```shell
sudo systemctl start activemq
sudo systemctl stop activemq
sudo systemctl restart activemq
sudo systemctl status activemq

# you can use this debug mode if ActiveMQ service can't run
/opt/apache-activemq/bin/activemq console
```