# liquibase opt mysql  deamon

### auto generate ChangeLog
```shell
liquibase --driver=com.mysql.jdbc.Driver --classpath=./mysql/mysql-connector-java-5.1.44-bin.jar --url=jdbc:mysql://localhost/test   --username=root --password=king --referenceUrl=jdbc:mysql://localhost/test01 --referenceUsername=root --referencePassword=king  diffChangeLog >test.xml 
```      
### run the ChangeSet
```shell
 liquibase --driver=com.mysql.jdbc.Driver --classpath=./mysql/mysql-connector-java-5.1.44-bin.jar --changeLogFile=./test/changelog.xml  --url="jdbc:mysql://localhost/test" --username=root --password=king  migrate
```

### check your database
 * 数据库中多了一张test001的表
### 描述
 * changelog.xml 描述数据变更
 * deamon 以mysql数据库为例
 
### 更多操作，请参考官方文档
 - http://www.liquibase.org/documentation/index.html