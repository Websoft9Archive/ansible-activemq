# FAQ

#### What the difference between Active Classic and ActiveMQ Artemis?

ActiveMQ Artemis is the next generation of ActiveMQClassic. Refer to: [ActiveMQ Classic](https://activemq.apache.org/getting-started), [ActiveMQ Artemis](https://activemq.apache.org/components/artemis/documentation/)

#### How can I enable the debug mode of ActiveMQ service?

```
systemctl stop activemq
/opt/apache-activemq/bin/activemq console
```

#### How to set the ActiveMQ console password?

You can reset or set the password by modity the file: */opt/apache-activemq/conf/jetty-realm.properties*, then **systemctl restart activemq**

#### How can I log out ActiveMQ console?

coming soon...


#### Is the Tomcat included in the ActiveMQ directory?

Yes, ActiveMQ integrated the Tomcat

#### If there is no domain name, can I deploy ActiveMQ?

Yes, visit ActiveMQ by *http://Internet IP:8161*

#### Is it possible to modify the source path of ActiveMQ?

Yes, but you should reset the PATH of ActiveMQ by the following command
```
echo 'export PATH="$PATH:/opt/apache-activemq/bin"' >> /etc/profile
```

#### How to change the permissions of file system?

Change owner(group) or permissions like below:

```shell
chown -R activemq.activemq /opt/apache-activemq
find /opt/apache-activemq -type d -exec chmod 750 {} \;
find /opt/apache-activemq -type f -exec chmod 640 {} \;
```

#### What's the difference between Deployment and Installation?

- Deployment is a process of installing and configuring a sequence of software in sequence in a different order, which is a complex system engineering.  
- Installation is the process of starting the initial wizard after the application is prepared.  
- Installation is simpler than deployment. 

#### What's Cloud Platform?

Cloud platform refers to platform manufacturers that provide cloud computing services, such as: **Azure, AWS, Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud**, etc.

#### What is the difference between Instance, Cloud Server, Virtual Machine, ECS, EC2, CVM, and VM?

No difference, just the terminology used by different manufacturers, actually cloud servers