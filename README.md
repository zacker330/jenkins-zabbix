
## 使用 Zabbix 监控 Jenkins
使用 Docker Compose 做实验。启动方式命令：`docker-compose up -d`。


### 各系统访问方法

#### LDAP（可选）
* url: https://localhost:6443/
* login DN: cn=admin,dc=example,dc=org
* password: admin

#### Zabbix web
* url: http://localhost:8081
* username: Admin
* password: zabbix


#### Zabbix agent
可以提前将 jenkins_zabbix.conf 和 jenkins.metrics.py 放到相应的目录中。

#### Jenkins 
Jenkins 访问地址：http://localhost:8080 。Jenkins 第一次启动需要输入一个 security token，你可以通过`docker-compose logs -f jenkins`命令，看到日志。从日志中找到这样的一段：
```shell
*************************************************************

Jenkins initial setup is required. A security token is required to proceed.
Please use the following security token to proceed to installation:

41d2b60b0e4cb5bf2025d33b21cb

*************************************************************
```
将 security token 拷贝到 Jenkins 界面，然后按提示操作就可以了。


