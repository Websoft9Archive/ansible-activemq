# FAQ

#### Active Classic 与 ActiveMQ Artemis

ActiveMQ Artemis 是ActiveMQ下一代产品，未来将替换 ActiveMQ Classic。 具体参考：[ActiveMQ Classic](https://activemq.apache.org/getting-started), [ActiveMQ Artemis](https://activemq.apache.org/components/artemis/documentation/)

#### ActiveMQ 无法启动，显示

ActiveMQ 采用 [Peer Authentication](https://www.postgresql.org/docs/10/auth-methods.html#AUTH-PEER) 方式连接 PostgreSQL，即以操作系统用户登录数据库，无需密码。

#### 为什么在设置面板看不到 ActiveMQ 更新（Updates）操作功能？

此功能只能在开发者模式下使用，请确保你的 ActiveMQ 控制台是否已经切换成[开发者管理模式](zh/solution-odoo.md#开发者模式)

#### 如何删除 ActiveMQ 演示数据？

由于 ActiveMQ 支持多企业组织方式，建议新增一个企业组织（不要勾选演示数据）后，再删除带演示的数据库。具体操作方式参考：[ ActiveMQ 数据库管理](/zh/admin-postgresql.md#新增)

#### ActiveMQ 是否可以导出 PDF 文件？

可以。安装 Invoice, Purchase 等模块可以测试 print to PDF 功能
![ActiveMQ 打印PDF](https://libs.websoft9.com/Websoft9/DocsPicture/en/odoo/odoo-printtopdf-websoft9.png)

#### 如果没有域名是否可以部署 ActiveMQ？

可以，访问`http://服务器公网IP` 即可

#### Windows版的 ActiveMQ 的 PostgreSQL 用户对应的密码是多少？

请在[账号密码](/zh/stack-components.md#postgresql)章节查看

#### 是否有可视化的数据库管理工具？

请直接通过 [ActiveMQ 自带的数据库管理工具](/zh/admin-postgresql.md)操作

#### 是否可以修改ActiveMQ的源码路径？

不可以

#### 如何修改上传的文件权限?

```shell
chown -R nginx.nginx /data/wwwroot/
find /data/wwwroot/ -type d -exec chmod 750 {} \;
find /data/wwwroot/ -type f -exec chmod 640 {} \;
```
#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器

#### ActiveMQ 在中国有哪些实施商？

如果您需要ActiveMQ的配置，咨询、实施和开发服务，请与专业的服务商联系。我们了解到的信息如下：

*   苏州远鼎 http://www.chinamaker.net/
*   开源智造 http://www.oscg.cn/
*   上海寰享网络科技有限公司 https://www.elico-corp.com/zh_CN/
*   北京开远科技有限公司 https://www.kalway.cn/
*   珠海市信莱德软件开发有限公司 http://www.zhsunlight.cn/
*   成都欧督系统科技有限公司 http://www.odoostart.com/
*   山西清水欧度信息技术有限公司  http://www.odooqs.com (54773801@qq.com)