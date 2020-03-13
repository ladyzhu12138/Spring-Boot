# Spring Boot入门
## 环境选择
- JDK1.8
- Maven 3.9.9
- IDEA 2018.3.5

## Maven的配置
虽然IDEA自带了Maven，但是还是使用了自己的配置，速度比自带的快捷一些
在下载完Maven之后，更改conf文件夹下的setting.xml文件，添加对jdk版本的设置

```XML
<!--存放于Profiles文件夹下->
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

在国内的大环境下，从官网下载数据的速度往往比较慢，这时需要添加一个阿里云的镜像
```xml
<!--存放于mirrors文件夹下->
<mirror>
    <id>nexus-aliyun</id>
    <mirrorOf>central</mirrorOf>
    <name>Nexus aliyun</name>
    <url>http://maven.aliyun.com/nexus/content/groups/public</url>
</mirror>
```
## 第一个项目的创建
### 导入spring boot的相关依赖项
```xml
<parent>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-parent</artifactId>
	<version>2.2.1.RELEASE</version>
	<relativePath/>
</parent>

<dependencies>
	<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
	</dependency>
</dependencies>
```
等待IDEA自动下载安装所需的jar包
### 编写主程序
首选引入需要的jar包
```java
/*用于SpringBoot的启动*/
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
```
然后编写对呀的主方法
```java
@SpringBootApplication//用于
public class ClassName{

    public static void main(String[] args) {
        SpringApplication.run(ClassName.class, args);
    }
}
```
### 添加Controller
引入所需的jar包
```java
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;
```
添加第一个控制器
```java

public class HelloController {

    @ResponseBody
    @RequestMapping("/hello")
    public String hello(){
        return "hello SpringBoot,this is my first Application";
    }
}
```
在为改变tomcat的配置的情况下默认是使用的8080端口，可以在浏览器查看是否成功启动  
[点击这里](http://localhost:8080/hello)


