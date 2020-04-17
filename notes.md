# ActiveMQ Notes

组件名称：ActiveMQ  
安装文档：[ActiveMQ Classic](https://activemq.apache.org/getting-started), [ActiveMQ Artemis](https://activemq.apache.org/components/artemis/documentation/)  
配置文档：同上  
支持平台：Windows, Unix(Linux)  

临时责任人：cdl

## 概要

ActiveMQ是一款开源的MQ系统，官方提供了：ActiveMQ Classic 和 ActiveMQ Artemis 两个发行版，其中ActiveMQ Artemis是下一代的高性能MQ

## 环境要求

* 程序语言：Java1.7 
* 应用服务器：自带
* 数据库：无
* 依赖组件：无
* 其他：无

## 安装说明

官方提供了源码和二进制包两种方式，建议使用二进制包的安装方式。  

下面基于不同的安装平台，分别进行安装说明。

### Linux

### Windows

待研究

## 路径

* 程序路径：  
* 日志路径：  
* 配置文件路径：  
* 其他...

## 配置

安装完成后，需要依次完成如下配置

```shell
# Set ActiveMQ
- name: Restart ActiveMQ
  shell: systemctl start rabbitmq-server

- name: Enable the management console of ActiveMQ
  shell: rabbitmq-plugins enable rabbitmq_management

- name: Create administrator for ActiveMQ console
  shell: |
    rabbitmqctl add_user admin admin
    rabbitmqctl set_user_tags admin administrator
```

## 账号密码

### 数据库密码

无

### 后台账号

如果有后台账号

* 登录地址：http://服务器公网IP:8161/admin/
* 账号密码：admin/admin
* 密码修改方案：暂无

## 服务

本项目安装需要自行编写服务，具体内容如下：

```
[Unit]
Description=activemq message queue
After=network.target
[Service]
PIDFile=/opt/apache-activemq/data/activemq.pid
ExecStart=/opt/apache-activemq/bin/activemq start
ExecStop=/opt/apache-activemq/bin/activemq stop
User=activemq
Group=activemq
[Install]
WantedBy=multi-user.target
```

## 环境变量

列出需要增加的环境变量以及增加环境变量的命令

* activemq: export PATH="$PATH:/opt/apache-activemq/bin
* java: 

## 版本号

通过如下的命令获取主要组件的版本号: 

```
# Check ActiveMQ version
sudo rabbitmqctl status | grep ActiveMQ*

# Check Erlang version
ls /usr/lib64/erlang
```

## 常见问题

#### 有没有管理控制台？

*http:// 公网 IP:8161* 即可访问控制台，系统默认存在一个无法通过外网访问的guest/guest账号

#### 本项目需要开启哪些端口？

运行`netstat -anopt | grep LISTEN` 查看端口后，列出

#### 有没有CLI工具？

未知

## 日志

* 2020-04-17  完成安装研究  cdl