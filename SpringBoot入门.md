- [一、Spring Boot入门](#%e4%b8%80spring-boot%e5%85%a5%e9%97%a8)

# 一、Spring Boot入门

在文件中添加对应的jdk版本设置
```XML
<profile>
  <id>jdk-1.8</id>
  <activation>
    <activeByDefault>true</activeByDefault>
    <jdk>1.8</jdk>
  </activation>
  <properties>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
    <maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>
  </properties>
</profile>

```
但仅仅是这样还不够，因为国内的环境，还需要添加阿里云的镜像配置
```xml
<mirror>
    <id>nexus-aliyun</id>
    <mirrorOf>central</mirrorOf>
    <name>Nexus aliyun</name>
    <url>http://maven.aliyun.com/nexus/content/groups/public</url>
</mirror>
```