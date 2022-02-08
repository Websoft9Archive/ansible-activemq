# Parameters

The ActiveMQ deployment package contains a sequence software (referred to as "components") required for ActiveMQ to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

You can check the file path by the cmd `whereis` of ActiveMQ, and we have prepared more detail for your reference

```
whereis activemq
whereis java
```

### ActiveMQ

ActiveMQ installation directory:  */opt/apache-activemq/*  
ActiveMQ configuration directory:  */opt/apache-activemq/conf*  
ActiveMQ data directory:  */opt/apache-activemq/data*  
ActiveMQ logs directory:  */opt/apache-activemq/data/activemq.log*

> you can reset the administrator password of ActiveMQ by modify the file: */opt/apache-activemq/conf/jetty-realm.propertie* 

### Java

Java Directory: */usr/lib/jvm*

## Ports

You can control(open or shut down) ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** of your Cloud Server whether the port can be accessed from Internet.

You can run the cmd `netstat -tunlp` to list all used ports, and we list the following most useful ports for you:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| HTTP | 8161 | HTTP requests for ActiveMQ Console| Required |
| HTTPS | 5672 | amqp | Optional |

## Version

You can see the version from product page of Marketplace. However, after being deployed to your server, the components will be automatically updated, resulting in a certain change in the version number. Therefore, the exact version number should be viewed by running the command on the server:

```shell
# Linux Version
lsb_release -a

# Java Version
java -version

# ActiveMQ version
ls /opt/apache-activemq | grep activemq
```
