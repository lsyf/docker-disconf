```dockerfile
FROM tomcat:8.5.66-jdk8

ARG app_file
ADD ${app_file} /usr/local/tomcat/webapps/${webapp_file}
```

```shell
docker build \
--build-arg app_file=disconf-web.tar.gz \
-f Dockerfile \
-t \
lsyf/disconf-web:2.6.36 \
.
```

docker可配置的环境变量：

- jdbc_url
- jdbc_username
- jdbc_password
- redis_host1
- redis_port1
- redis_password1
- redis_host2
- redis_port2
- redis_password2
- zk_hosts

docker可挂载的配置有：

- /usr/local/tomcat/webapps/disconf-web/WEB-INF/classes/application.properties
- /usr/local/tomcat/webapps/disconf-web/WEB-INF/classes/jdbc-mysql.properties
- /usr/local/tomcat/webapps/disconf-web/WEB-INF/classes/redis-config.properties
- /usr/local/tomcat/webapps/disconf-web/WEB-INF/classes/zoo.properties

