# Update & Upgrade

Updates and upgrades are one of the maintenance tasks for sytem. Programs that are not upgraded for a long time, like buildings that are not maintained for a long time, will accelerate aging and gradually lose functionality until they are unavailable.

You should know the differences between the terms **Update** and **Upgrade**([Extended reading](https://support.websoft9.com/docs/faq/tech-upgrade.html#update-vs-upgrade))
- Operating system patching is **Update**, Ubuntu16.04 to Ubuntu18.04 is **Upgrade**
- MySQL5.6.25 to MySQL5.6.30 is **Update**, MySQL5.6 to MySQL5.7 is **Upgrade**

For ActiveMQ maintenance, focus on the following two Update & Upgrade jobs

- Sytem update(Operating System and Running Environment) 
- ActiveMQ upgrade 

## System Update

Run an update command to complete the system update:

``` shell
#For Ubuntu&Debian
apt update && apt upgrade -y

#For Centos&Redhat
yum update -y
```
> This deployment package is preconfigured with a scheduled task for automatic updates. If you want to remove the automatic update, please delete the corresponding Cron

## ActiveMQ Upgrade

ActiveMQ upgrade is similar to installation, you can upgrade it by the following steps

1. Prepare for upgrade
   ```
   # stop ActiveMQ service
   systemctl stop activemq

   # rename the dir of ActiveMQ for backup
   mv /opt/apache-activemq  /opt/apache-activemqBK
   ```
2. [Download ActiveMQ](http://activemq.apache.org/components/classic/download/) and upload it to the directory */opt* after unzip it, then renamed the directory to *apache-activemq*
3. Run the following modify permissions separately
   ```
   chown -R activemq. /opt/apache-activemq
   chmod 640  /opt/apache-activemq/examples/stomp/php/*
   chmod +x /opt/apache-activemq/bin/activemq
   ```
4. Restart the [ActiveMQ Service](/zh/admin-services#activemq) 