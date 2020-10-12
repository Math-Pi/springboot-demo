@[TOC](SpringBoot学习笔记（一）：Demo)

## 一、pom.xml引入Maven依赖

```xml
<!-- web开发包：包含Tomcat和Springmvc -->
<dependency>    
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
<!-- 单元测试包 -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-test</artifactId>
    <scope>test</scope>
</dependency>
```

## 二、启动类

- **@SpringBootApplication**：声明当前类为SpringBoot入口类，且项目只只能有一个。

```java
@SpringBootApplication
public class DemoApplication {
    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }
}
```

## 三、Controller类

- **@RestController**：声明当前类为控制层的类（等价于**@Controller+@ResponseBody**的结合，方法返回**json**格式数据）。
- **@RequestMapping**：用来处理请求地址映射的注解，可用于类或方法上。

```java
@RestController
public class HelloController {
    @RequestMapping("hello")
    public String hello() {
        return "Hello";
    }
}
```

## 四、测试类

- **@SpringBootTest**：是SpringBoot Since:1.4.0 版本开始引入的一个用于测试的注解。
- **@Test**：该方法可以不用main方法调用就可以测试出运行结果，是一种测试方法。

```java
@SpringBootTest
class DemoApplicationTests {
    @Test
    void contextLoads() {
        System.out.println("Hello World!");
    }
}
```