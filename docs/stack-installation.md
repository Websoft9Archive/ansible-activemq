# Initial Installation

If you have completed the ActiveMQ deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:8161 is allowed
3. Make a domain resolution on your DNS Console if you want to use domain for ActiveMQ

## ActiveMQ Installation Wizard

1. Using local Chrome or Firefox to visit the URL *http://DNS:8161* or *http://Internet IP:8161*, you will enter installation wizard of ActiveMQ
  ![ActiveMQ console](http://libs.websoft9.com/Websoft9/DocsPicture/zh/activemq/activemq-login-websoft9.png)

2. Click link【Manage ActiveMQ broker】to login ActiveMQ console([Don't know password?](/stack-accounts.md#activemq))
  ![ActiveMQ console](http://libs.websoft9.com/Websoft9/DocsPicture/zh/activemq/activemq-logined-websoft9.png)

3. You can reset the password by modify the file */opt/apache-activemq/conf/jetty-realm.properties* 

> More useful ActiveMQ guide, please refer to [Using Apache ActiveMQ](https://activemq.apache.org/using-activemq)

## Q&A

#### I can't visit the start page of ActiveMQ?

Your TCP:8161 of Security Group Rules is not allowed so there no response from Chrome or Firefox

#### ActiveMQ service can't start? 

Make sure your **hostname** of Server not include the str ".". e.g activemq5.6 is a not regular for ActiveMQ

you can rename hostname by the following command

```
hostnamectl set-hostname activemq
```