# Parameters

The ActiveMQ deployment package contains a sequence software (referred to as "components") required for ActiveMQ to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

### ActiveMQ

ActiveMQ installation directory: */usr/lib/python3/dist-packages/odoo*  
ActiveMQ configuration file: */etc/odoo/odoo.conf*  
ActiveMQ log directory: */var/log/odoo*    

### Python

Python installation directory: * /usr/lib/python-v*    
Python VM directory: */usr/bin/python-v*

-v is version 2.7/3/3.6/3.7

### Nginx

Nginx vhost configuration file: */etc/nginx/sites-available/default*  
Nginx main configuration file: */etc/nginx/nginx.conf*  
Nginx logs file: */var/log/nginx/*

### PostgreSQL

PostgreSQL installation directory: */usr/bin/psql*  
PostgreSQL data file: */var/lib/postgresql*   
PostgreSQL configuration file: */etc/postgresql/10/main/postgresql.conf*      
PostgreSQL log directory: */var/log/postgresql*  
PostgreSQL GUI management: ActiveMQ's log in page have provided the database GUI management tools


## Ports

You can control(open or shut down) ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** of your Cloud Server whether the port can be accessed from Internet.

These ports should be opened for this application:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| MySQL | 3306 | Remote connect MySQL | Optional |
| HTTP | 80 | HTTP requests for ActiveMQ | Required |
| HTTPS | 443 | HTTPS requests ActiveMQ | Optional |
| PostgreSQL | 5432 | Remote connect PostgreSQL | Optional |

## Version

You can see the version from product page of Marketplace. However, after being deployed to your server, the components will be automatically updated, resulting in a certain change in the version number. Therefore, the exact version number should be viewed by running the command on the server:

```shell
# Linux Version
lsb_release -a

# Python Version
python --version  
python3 --version

# Nginx version:
nginx -v

# PostgeSQL version:
psql --version
```