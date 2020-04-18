# 故障处理

此处收集使用 ActiveMQ 过程中最常见的故障，供您参考

> 大部分故障与云平台密切相关，如果你可以确认故障的原因是云平台造成的，请参考[云平台文档](https://support.websoft9.com/docs/faq/zh/tech-instance.html)

#### 如何查看错误日志？

最简单的方式是通过SSH连接服务器，运行`odoo`这个命令，就会显示错误日志以及ActiveMQ的运行情况

#### 恢复数据库、上传附件等操作，出现 “413 Request Entity Too Large” 错误？

这是由于 Nginx 默认安装下，上传文件最大为 1M，因此需要修改 Nginx 这个限制：
1. 使用 WinSCP 远程连接服务器
2. 编辑 [Nginx 虚拟机主机配置文件](/zh/stack-components.md#nginx)
3. 插入一行 `client_max_body_size 0;` 解除上传文件限制的配置项
   ```
   server {
    listen 80;
    server_name _;
    client_max_body_size 0; #解除上传文件限制
    ...
   ```
4. 保存并[重启 Nginx 服务](/zh/admin-services.md#nginx)

#### 访问ActiveMQ总是出现数据库设置提醒？

![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/odoo/odoo-setpasswodrem-websoft9.png)

这个提醒的是要求你尽快给数据库设置一个高强度的管理员密码，如果不设置将面临很大的风险。一旦设置后，此界面就不会再弹出了

#### 无法通过 SFTP 上传文件到ActiveMQ程序目录问题

由于部分 Ubuntu系统 默认创建了默认用户名 ubuntu ,ubuntu为普通用户没有对odoo程序的源码或目录有操作的权限,需要执行一下命令:

```
sudo chmod o+rw  /usr/lib/python2.x/dist-packages/odoo   # odoo10版本
sudo chmod o+rw  /usr/lib/python3/dist-packages/odoo   # odoo11版本以上
```

#### ActiveMQ服务无法启动？

1. 运行`activemq console`，以前台方式运行ActiveMQ服务，便可以查看启动状态和错误
2. 打开日志文件：*/opt/apache-activemq/data/activemq.log*，检索 **failed** 关键词，分析错误原因

比较常见的原因有如下几点：

* 主机名不符合要求
* 缺乏Java的环境变量。通过：`echo $JAVA_HOME` 或 `which java` 查看反馈信息。
