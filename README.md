## 快速搭建springboot-jdbc



##使用
```
1.执行mvn install

2.加入下面依赖包

<dependency>
    <groupId>cn.bucheng</groupId>
    <artifactId>spring-boot-starter-quick-jdbc</artifactId>
    <version>1.0-SNAPSHOT</version>
</dependency>

3.添加下面配置文件

spring.datasource.type=com.alibaba.druid.pool.DruidDataSource
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
#配置自己数据量连接
spring.datasource.url=jdbc:mysql://127.0.0.1:3306/ad_test?serverTimezone=GMT%2B8&useUnicode=true&characterEncoding=UTF-8
spring.datasource.username=root
spring.datasource.password=123456
spring.datasource.druid.initial-size=5
spring.datasource.druid.min-idle=5
spring.datasource.druid.maxActive=20
spring.datasource.druid.maxWait=60000
spring.datasource.druid.timeBetweenEvictionRunsMillis=60000
spring.datasource.druid.minEvictableIdleTimeMillis=300000
spring.datasource.druid.validationQuery=SELECT 1
spring.datasource.druid.testWhileIdle=true
spring.datasource.druid.testOnBorrow=false
spring.datasource.druid.testOnReturn=false
spring.datasource.druid.poolPreparedStatements=true
spring.datasource.druid.maxPoolPreparedStatementPerConnectionSize=20

spring.datasource.druid.filters=stat,wall
spring.datasource.druid.connectionProperties=druid.stat.mergeSql=true;druid.stat.slowSqlMillis=5000

spring.datasource.druid.stat-view-servlet.login-username=admin
spring.datasource.druid.stat-view-servlet.login-password=admin


#配置自己需要输出sql语句的包
logging.level.cn.*.*=debug
#配置自己需要映射的Mapper文件
mybatis-plus.mapper-locations=classpath:/db/mapper/*Mapper.xml
#配置需要别名的包路径
mybatis-plus.typeAliasesPackage=cn.bucheng.esboot.entity
mybatis-plus.global-config.id-type=0
mybatis-plus.global-config.field-strategy=2
mybatis-plus.global-config.db-column-underline=true
mybatis-plus.global-config.key-generator=com.baomidou.mybatisplus.incrementer.OracleKeyGenerator
mybatis-plus.global-config.logic-delete-value=1
mybatis-plus.global-config.logic-not-delete-value=0
mybatis-plus.configuration.map-underscore-to-camel-case= true
mybatis-plus.configuration.cache-enabled= false
mybatis-plus.configuration.jdbc-type-for-null='null'


4.在springboot启动类添加，其为自己的mapper接口包路径
@MapperScan(basePackages = "cn.bucheng.esboot.mapper")
```
