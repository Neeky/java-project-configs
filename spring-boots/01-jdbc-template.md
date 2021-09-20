## 在 spring-boot 项目中配置 jdbc-template 的 datasource 

1、application.properties 配置文件添加如下内容
```ini
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.datasource.url=jdbc:mysql://neekystudio.com:3306/tempdb
spring.datasource.username=appuser
spring.datasource.password=dbma@0352
```
---

2、pom.xml 中添加如下内容
```xml
    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>8.0.26</version>
    </dependency>

    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-jdbc</artifactId>
    </dependency>
```

---