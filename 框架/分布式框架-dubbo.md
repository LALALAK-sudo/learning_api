# dubbo

## **1-今日内容**

 分布式系统中的相关概念

dubbo 概述

dubbo快速入门

dubbo的高级特性


## **2-相关概念**

### 2.1-互联网项目架构-特点

互联网项目架构-特点

1. 用户多

2. 流量大，并发高

3. 海量数据

4. 易受攻击

5. 功能繁琐

6. 变更快

   

**传统项目和互联网项目的不同**

![1581310475046](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581310475046.png)



**用户体验**：
	美观、功能、速度、稳定性

**衡量一个网站速度是否快:**
	打开一个新页面一瞬间完成;页面内跳转，-刹那间完成。
	根据佛经《僧衹律》记载:一 刹那者为-念,二十念为-瞬,二十瞬为-弹
	指，二十弹指为-罗预， 二十罗预为-须臾，一日一夜有三十须臾。





### 2.2-互联网项目架构-目标



衡量网站的性能指标:

**响应时间:**指执行一个请求从开始到最后收到响应数据所花费的总体时间。

**并发数:**指系统同时能处理的请求数量。

- **并发连接数:** 指的是客户端向服务器发起请求，并建立了TCP连接。每秒钟服务器连接的总TCP数量
- **请求数:**也称为QPS(Query Per Second)指每秒多少请求.
- **并发用户数:**单位时间内有多少用户



**吞吐量:**指单位时间内系统能处理的请求数量。



	●QPS: Query Per Second每秒查询数。
	●TPS: Transactions Per Second每秒事务数。
	●一个事务是指一 个客户机向服务器发送请求然后服务器做出反应的过程。客户机在发送请求时开始计时，收到服务器响应后结束
	计时，以此来计算使用的时间和完成的事务个数。
	●一个页面的一次访问，只会形成一 个TPS; 但-次页面请求，可能产生多次对服务器的请求，就会有多个QPS
	  QPS>=并发连接数>= TPS

**大型互联网项目架构目标**:

​	●**高性能:**提供快速的访问体验。
​	●**高可用:**网站服务- 可以正常访问

### 2.3-集群和分布式

集群和分布式
●<font color="red">集群</font>:很多“人”一起，干一样的事。

一个业务模块，部署在多台服务器上。



●<font color="red">分布式</font>:很多"人”一起，干不样的事。这些不一样的事， 合起来是一件大事。

一个大的业务系统,拆分为小的业务模块,分别部署在不同的机器上。



![](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\集群和分布式-1581325224087.png)



### 2.4-架构演进

**单体架构：**

**优点:**
	简单:开发部署都很方便，小型项目首选
**缺点:**
●项目启动慢
●可靠性差

![1581313584459](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581313584459.png)



**垂直架构：**垂直架构是指将单体架构中的多个模块拆分为多个独立的项目。形成多个独立的单体架构。

**单体架构存在的问题:**

- 项目启动慢

- 可靠性差

- 可伸缩性差

- 扩展性和可维护性差

- 性能低

**垂直架构存在的问题:** 重复功能太多



![1581313910427](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581313910427.png)



**分布式架构：**是指在垂直架构的基础上,将公共业务模块抽取出来,作为独立的服务供其他调用者消费，以实现服务的共享和重用。底层通过RPC（远程过程调用实现）
	**RPC:** Remote Procedure Call远程过程调用。有非常多的协议和技术来都实现了RPC的过程。比如: HTTP REST风格，Java RMI规范、WebService SOAP协议Hession等等。
**垂直架构存在的问题:**
	●重复功能太多

**分布式架构存在的问题:**
​	●服务提供方- -旦产生变更,所有消费方都需要变更。



![](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\分布式架构.png)



**SOA: (Service- Oriented Architecture,面向服务的架构)**：是一个组件模型,它将应用程序的不同功能单元(称为服务)进行拆分，并通过这些服务之间定义良好的接口和契约联系起来。

**ESB: (Enterparise Servce Bus)**：企业服务总线,服务中介。主要是提供了一一个服
务于服务之间的交互。ESB包含的功能如:负载均衡，流量控制，加密处理，服务
的监控，异常处理，监控告急等等。





![1581314362523](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581314362523.png)



**微服务架构：**

●微服务架构是在SOA上做的升华,微服务架构强调的一个重点是“业务需要彻底的组件化和服务化”，原有的单个
业务系统会拆分为多个可以独立开发、设计、运行的小应用。这些小应用之间通过服务完成交互和集成。

●微服务架构= 80%的SOA服务架构思想+ 100%的组件化架构思想+ 80%的领域建模思想



**特点:**
●服务实现组件化:开发者可以自由选择开发技术。也不需要协调其他团队
●服务之间交互一 般使用REST API
●去中心化:每个微服务有自己私有的数据库持久化业务数据
●自动化部署:把应用拆分成为一 个-个独立的单个服务,方便自动化部署、测试、运维



![](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\微服务架构图.png)



## 3-dubbo 概述

**Dubbo概念**

●Dubbo是阿里巴巴公司开源的一个高性能、轻量级的Java RPC框架。
●致力于提供高性能和透明化的RPC远程服务调用方案,以及SOA服务治理方案。
●官网: http://dubbo.apache.otrgo



![](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\Dubbo架构图.png)



节点角色说明: .
●Provider: 暴露服务的服务提供方
●Contahier: 服务运行容器
●Consumer: 调用远程服务的服务消费方
●Registry: 服务注册与发现的注册中心
●Monitor:统计服务的调用次数和调用时间的监控中心



## 4-dubbo快速入门

### 4.1zookeeper安装

安装步骤：

第一步：安装 jdk（略）
第二步：把 zookeeper 的压缩包（zookeeper-3.4.6.tar.gz）上传到 linux 系统
第三步：解压缩压缩包

```sh
tar -zxvf  zookeeper-3.4.6.tar.gz
```

第四步：进入zookeeper-3.4.6目录，创建data目录

```sh
mkdir data
```

第五步：进入conf目录 ，把zoo_sample.cfg 改名为zoo.cfg

```sh
cd conf
mv zoo_sample.cfg zoo.cfg
```

第六步：打开zoo.cfg文件,  修改data属性：

```sh
dataDir=/root/zookeeper-3.4.6/data
```



进入Zookeeper的bin目录，启动服务命令

```sh
./zkServer.sh start
```

![1581315609244](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581315609244.png)

停止服务命令

```sh
./zkServer.sh stop
```



查看服务状态：standalone 单节点

```sh
./zkServer.sh status
```

![1581315645227](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581315645227.png)

### 4.2spring和springmvc整合

实施步骤：

1.创建服务提供者Provider模块
2.创建服务消费者Consumer模块
3.在服务提供者模块编写UserServicelmpl提供服务
4.在服务消费者中的UserC ontroller远程调用
5.UserServicelmpl提供的服务
6.分别启动两个服务，测试

![image-20210303101942062](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210303101942062.png)



![image-20210303110535758](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210303110535758.png)



Dubbo作为一个RPC框架，其最核心的功能就是要实现跨网络的远程调用。本小节就是要创建两个应用，一个作为服务的提供方，一个作为服务的消费方。通过Dubbo来实现服务消费方远程调用服务提供方的方法。

1 服务提供方开发

开发步骤：

（1）创建maven工程（打包方式为war）dubbodemo_provider，在pom.xml文件中导入如下坐标

```xml
<properties>
  <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
  <maven.compiler.source>1.8</maven.compiler.source>
  <maven.compiler.target>1.8</maven.compiler.target>
  <spring.version>5.0.5.RELEASE</spring.version>
</properties>
<dependencies>
  <dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-context</artifactId>
    <version>${spring.version}</version>
  </dependency>
  <dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-beans</artifactId>
    <version>${spring.version}</version>
  </dependency>
  <dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-webmvc</artifactId>
    <version>${spring.version}</version>
  </dependency>
  <dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-jdbc</artifactId>
    <version>${spring.version}</version>
  </dependency>
  <dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-aspects</artifactId>
    <version>${spring.version}</version>
  </dependency>
  <dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-jms</artifactId>
    <version>${spring.version}</version>
  </dependency>
  <dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-context-support</artifactId>
    <version>${spring.version}</version>
  </dependency>
  <!-- dubbo相关 -->
  <dependency>
    <groupId>com.alibaba</groupId>
    <artifactId>dubbo</artifactId>
    <version>2.6.0</version>
  </dependency>
  <dependency>
    <groupId>org.apache.zookeeper</groupId>
    <artifactId>zookeeper</artifactId>
    <version>3.4.6</version>
  </dependency>
  <dependency>
    <groupId>com.github.sgroschupf</groupId>
    <artifactId>zkclient</artifactId>
    <version>0.1</version>
  </dependency>
  <dependency>
    <groupId>javassist</groupId>
    <artifactId>javassist</artifactId>
    <version>3.12.1.GA</version>
  </dependency>
  <dependency>
    <groupId>com.alibaba</groupId>
    <artifactId>fastjson</artifactId>
    <version>1.2.47</version>
  </dependency>
</dependencies>
<build>
  <plugins>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-compiler-plugin</artifactId>
      <version>2.3.2</version>
      <configuration>
        <source>1.8</source>
        <target>1.8</target>
      </configuration>
    </plugin>
    <plugin>
      <groupId>org.apache.tomcat.maven</groupId>
      <artifactId>tomcat7-maven-plugin</artifactId>
      <configuration>
        <!-- 指定端口 -->
        <port>8081</port>
        <!-- 请求路径 -->
        <path>/</path>
      </configuration>
    </plugin>
  </plugins>
</build>
```

（2）配置web.xml文件

```xml
<!DOCTYPE web-app PUBLIC
 "-//Sun Microsystems, Inc.//DTD Web Application 2.3//EN"
 "http://java.sun.com/dtd/web-app_2_3.dtd" >
<web-app>
  <display-name>Archetype Created Web Application</display-name>
  <context-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>classpath:applicationContext*.xml</param-value>
  </context-param>
  <listener>
    <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
  </listener>
</web-app>

```

（3）创建服务接口

```java
package com.itheima.service;
public interface HelloService {
    public String sayHello(String name);
}
```

（4）创建服务实现类



**注意：**服务实现类上使用的Service注解是Dubbo提供的，用于对外发布服务



```java
package com.itheima.service.impl;
import com.alibaba.dubbo.config.annotation.Service;
import com.itheima.service.HelloService;

@Service//将这个类提供的方法（服务）对外发布。将访问的地址ip，端口，路径注册到注册中心中
public class HelloServiceImpl implements HelloService {
    public String sayHello(String name) {
        return "hello " + name;
    }
}
```





tomcat7:run

2 服务消费方开发

开发步骤：

（1）创建maven工程（打包方式为war）dubbodemo_consumer，pom.xml配置和上面服务提供者相同，只需要将Tomcat插件的端口号改为8082即可

（2）配置web.xml文件

```xml
<!DOCTYPE web-app PUBLIC
 "-//Sun Microsystems, Inc.//DTD Web Application 2.3//EN"
 "http://java.sun.com/dtd/web-app_2_3.dtd" >
<web-app>
  <display-name>Archetype Created Web Application</display-name>
  <servlet>
    <servlet-name>springmvc</servlet-name>
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    <!-- 指定加载的配置文件 ，通过参数contextConfigLocation加载 -->
    <init-param>
      <param-name>contextConfigLocation</param-name>
      <param-value>classpath:applicationContext-web.xml</param-value>
    </init-param>
    <load-on-startup>1</load-on-startup>
  </servlet>
  <servlet-mapping>
    <servlet-name>springmvc</servlet-name>
    <url-pattern>*.do</url-pattern>
  </servlet-mapping>
</web-app>
```

（3）将服务提供者工程中的HelloService接口复制到当前工程

（4）编写Controller

```java
package com.itheima.controller;
import com.alibaba.dubbo.config.annotation.Reference;
import com.itheima.service.HelloService;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;
@Controller
@RequestMapping("/demo")
public class HelloController {
    @Reference
    private HelloService helloService;
    @RequestMapping("/hello")
    @ResponseBody
    public String getName(String name){
        //远程调用
        String result = helloService.sayHello(name);
        System.out.println(result);
        return result;
    }
}
```

注意：Controller中注入HelloService使用的是Dubbo提供的@Reference注解

### 4.3服务提供者

在dubbodemo_provider工程中src/main/resources下创建applicationContext-service.xml 

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
		xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	    xmlns:p="http://www.springframework.org/schema/p"
		xmlns:context="http://www.springframework.org/schema/context"
		xmlns:dubbo="http://code.alibabatech.com/schema/dubbo"
	    xmlns:mvc="http://www.springframework.org/schema/mvc"
		xsi:schemaLocation="http://www.springframework.org/schema/beans
		http://www.springframework.org/schema/beans/spring-beans.xsd
         http://www.springframework.org/schema/mvc
         http://www.springframework.org/schema/mvc/spring-mvc.xsd
         http://code.alibabatech.com/schema/dubbo
         http://code.alibabatech.com/schema/dubbo/dubbo.xsd
         http://www.springframework.org/schema/context
         http://www.springframework.org/schema/context/spring-context.xsd">
	<!-- 当前应用名称，用于注册中心计算应用间依赖关系，注意：消费者和提供者应用名不要一样 -->
	<dubbo:application name="dubbodemo_provider" />
	<!-- 连接服务注册中心zookeeper ip为zookeeper所在服务器的ip地址-->
	<dubbo:registry address="zookeeper://192.168.134.129:2181"/>
	<!-- 注册  协议和port   端口默认是20880 -->
	<dubbo:protocol name="dubbo" port="20881"></dubbo:protocol>
    
	<!-- 扫描指定包，加上@Service注解的类会被发布为服务  -->
	<dubbo:annotation package="com.itheima.service.impl" />
</beans>
```



### 4.4服务消费者

在dubbodemo_consumer工程中src/main/resources下创建applicationContext-web.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns:p="http://www.springframework.org/schema/p"
	xmlns:context="http://www.springframework.org/schema/context"
	xmlns:dubbo="http://code.alibabatech.com/schema/dubbo"
	xmlns:mvc="http://www.springframework.org/schema/mvc"
	xsi:schemaLocation="http://www.springframework.org/schema/beans
			http://www.springframework.org/schema/beans/spring-beans.xsd
			http://www.springframework.org/schema/mvc
			http://www.springframework.org/schema/mvc/spring-mvc.xsd
			http://code.alibabatech.com/schema/dubbo
			http://code.alibabatech.com/schema/dubbo/dubbo.xsd
			http://www.springframework.org/schema/context
			http://www.springframework.org/schema/context/spring-context.xsd">

	<!-- 当前应用名称，用于注册中心计算应用间依赖关系，注意：消费者和提供者应用名不要一样 -->
	<dubbo:application name="dubbodemo-consumer" />
	<!-- 连接服务注册中心zookeeper ip为zookeeper所在服务器的ip地址-->
	<dubbo:registry address="zookeeper://192.168.134.129:2181"/>
	<!-- 包扫描的方式 引用服务 扫描@Reference -->
	<dubbo:annotation package="com.itheima.controller" />
</beans>
```



```java
@RestController
@RequestMapping("/user")
public class UserController {

//    @Autowired
    /**
     * 1 从zookeeper注册中心获取userService的访问url
     * 2 进行远程调用RPC
     * 3 将结果封装为一个代理对象。给变量赋值
     */
    @Reference
    private UserService userService;

    @RequestMapping("/sayHello")
    public String sayHello() {
        String sayHello = userService.sayHello();
        return sayHello;
    }
}

```



运行测试

tomcat7:run启动

在浏览器输入http://localhost:8082/demo/hello.do?name=Jack，查看浏览器输出结果

## 5-dubbo高级特性



**5、打包项目**

在 dubbo-admin-develop 目录执行打包命令

```shell
mvn  clean package
```

![1578300464726](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1578300464726.png)

**6、启动后端**

切换到目录

```shell
dubbo-Admin-develop\dubbo-admin-distribution\target>
```

执行下面的命令启动 dubbo-admin，dubbo-admin后台由SpringBoot构建。

```shell
java -jar .\dubbo-admin-0.1.jar
```

**7、前台后端**

dubbo-admin-ui 目录下执行命令

```shell
npm run dev
```

![1578300677041](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1578300677041.png)

**8、访问**

浏览器输入。用户名密码都是root

```
http://localhost:8081/
```

![1578300774258](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1578300774258.png)

二、dubbo-admin简单使用





**1、点击服务查询**





**2、查询结果**

![1578301528363](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1578301528363.png)



A:输入的查询条件com.itheima.service.UserService

B:搜索类型，主要分为【按服务名】【按IP地址】【按应用】三种类型查询

C:搜索结果

**3.1.4 dubo-admin查看详情**

我们查看com.itheima.service.UserService （服务提供者）的具体详细信息，包含【元数据信息】

**1）点击详情**





从【详情】界面查看，主要分为3个区域

A区域：主要包含服务端 基础信息比如服务名称、应用名称等

B区域：主要包含了生产者、消费者一些基本信息

**C区域：是元数据信息，注意看上面的图,元数据信息是空的**

我们需要打开我们的生产者配置文件加入下面配置

```xml
    <!-- 元数据配置 -->
    <dubbo:metadata-report address="zookeeper://192.168.149.135:2181" />
```

重新启动生产者，再次打开Dubbo-Admin

这样我们的元数据信息就出来了



具体安装参见：dubbo-admin.md





### 5.3序列化



1. dubbo 内部已经将序列化和反序列化的过程内部封装了
2. 我们只需要在定义pojo类时**实现serializable接口**即可
3. 一般会定义一 个公共的pojo模块,让生产者和消费者都依赖该模块。



![1581317650919](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581317650919.png)



User对象未实现seriali zable接口

错误信息：

![1581317583708](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581317583708-1615105055482.png)



解决办法：

```java
User implements Serializable
```



### 5.4地址缓存（面试）



**注册中心挂了，服务是否可以正常访问？**

1.  可以，因为dubbo服务消费者在第一-次调用时，会将服务提供方地址缓存到本地，以后在调用则不会访问注册中心。
2.  当服务提供者地址发生变化时，注册中心会通知服务消费者。

![](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\Dubbo架构图-1581318103917.png)



### 5.5 超时



![](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\超时图片.png)



- 服务消费者在调用服务提供者的时候发生了阻塞、等待的情形,这个时候,服务消费者会直等待下去。
- 在某个峰值时刻，大量的请求都在同时请求服务消费者,会造成线程的大量堆积，势必会造成雪崩。
- dubbo利用超时机制来解决这个问题，设置-个超时时间, 在这个时间段内，无法完成服务访问,则自动断开连接。
- 使用timeout属性配置超时时间，默认值1000，单位毫秒



服务端实现（建议在这里设置）

```java
//timeout 超时时间 单位毫秒  retries 重试次数
@Service(timeout = 3000,retries=0)
```



或者注入时候(优先)

```java
@Reference(timeout = 1000)
```



### 5.6重试



![1581322543136](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581322543136.png)

1. 设置了超时时间，在这个时间段内，无法完成服务访问,则自动断开连接。
2. 如果出现网络抖动,则这一-次请求就会失败。
3. Dubbo提供重试机制来避免类似问题的发生。
4. 通过retries属性来设置重试次数。默认为2次

```java
//timeout 超时时间 单位毫秒  retries 重试次数
@Service(timeout = 3000,retries=0)
```

### 5.7多版本

![](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\多版本图片.png)

**灰度发布:**当出现新功能时,会让一部分用户先使用新功能，用户反馈没问题时，再将所有用户迁移到新功能。

dubbo中使用version属性来设置和调用同一个接口的不同版本



生产者配置

```java
@Service(version="v2.0")
public class UserServiceImp12 implements UserService {...}
```

消费者配置

```java
@Reference(version = "v2.0")//远程注入
private UserService userService;
```



### 5.8负载均衡

**负载均衡策略(4种) :** 
**Random:**按权重随机，默认值。按权重设置随机概率。

**RoundRobin:** 按权重轮询。

**LeastActive:** 最少活跃调用数,相同活跃数的随机。

**ConsistentHash:**一 致性Hash,相同参数的请求总是发到同一提供者。



![](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\负载均衡图.png)





![image-20210306210844643](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210306210844643.png)

服务提供者配置

```java
@Service(weight = 100)
public class UserServiceImp12 implements UserService {...}
```



application.xml 配置parameter key

![](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\负载均衡-配置文件.png)

消费者配置

```java
//@Reference(loadbalance = "roundrobin")
//@Reference(loadbalance = "leastactive")
//@Reference(loadbalance = "consistenthash")
@Reference(loadbalance = "random")//默认 按权重随机
private UserService userService;
```

### 5.9集群容错

![1581324308044](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581324308044.png)





**集群容错模式:**
	**Failover Cluster:**失败重试。默认值。当出现失败，重试其它服务器，默认重试2次，使用retries配置。一般用于读操作
	**Failfast Cluster :**快速失败,发起-次调用，失败立即报错。通常用于写操作。
	**Failsafe Cluster:**失败安全，出现异常时，直接忽略。返回一个空结果。
	**Failback Cluster:**失败自动恢复,后台记录失败请求,定时重发。
	**Forking Cluster :**并行调用多个服务器，只要一个成功即返回。
	**Broadcast Cluster:** 广播调用所有提供者,逐个调用，任意一台报错则报错。

消费者配置

```java
@Reference(cluster = "failover")//远程注入
private UserService userService;
```

### 5.10服务降级

**服务降级**：当服务器压力剧增的情况下，根据实际业务情况及流量，对一些服务和页面有策略的不处理或换种简单的方式处理，从而释放服务器资源以保证**核心交易**正常运作或高效运作

**服务降级方式:**
**mock= force:return null**：表示消费方对该服务的方法调用都直接返回null值,不发起远程调用。用来屏蔽不重要服务不可用时对调用方的影响。

**mock=fail:return null**：表示消费方对该服务的方法调用在失败后，再返回null值,不抛异常。用来容忍不重要服务不稳定时对调用方的影响



![](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\服务降级图片.png)

消费方配置

```java
//远程注入
@Reference(mock =“ force :return null")//不再调用userService的服务
private UserService userService;
```







#  Zookeeper

## 1)初识 Zookeeper

### 1.1)Zookeeper概念

•Zookeeper 是 Apache Hadoop 项目下的一个子项目，是一个树形目录服务。

•Zookeeper 翻译过来就是 动物园管理员，他是用来管 Hadoop（大象）、Hive(蜜蜂)、Pig(小 猪)的管理员。简称zk

•Zookeeper 是一个分布式的、开源的分布式应用程序的协调服务。

•Zookeeper 提供的主要功能包括：

•配置管理

•分布式锁

•集群管理

![1592054580488](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1592054580488.png)

![1592054603167](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1592054603167.png)

## 2)ZooKeeper 安装与配置

### 2.1) 下载安装

#### **2.1.1、环境准备**

ZooKeeper服务器是用Java创建的，它运行在JVM之上。需要安装JDK 7或更高版本。

#### **2.1.2、上传**

将下载的ZooKeeper放到/opt/ZooKeeper目录下

```shell
#上传zookeeper alt+p
put f:/setup/apache-zookeeper-3.5.6-bin.tar.gz
#打开 opt目录
cd /opt
#创建zooKeeper目录
mkdir  zooKeeper
#将zookeeper安装包移动到 /opt/zooKeeper
mv apache-zookeeper-3.5.6-bin.tar.gz /opt/zookeeper/
```

#### **2.1.3、解压**

将tar包解压到/opt/zookeeper目录下

```shell
tar -zxvf apache-ZooKeeper-3.5.6-bin.tar.gz 
```

### 2.2) 配置启动

#### **2.2.1、配置zoo.cfg**

进入到conf目录拷贝一个zoo_sample.cfg并完成配置

```shell
#进入到conf目录
cd /opt/zooKeeper/apache-zooKeeper-3.5.6-bin/conf/
#拷贝
cp  zoo_sample.cfg  zoo.cfg
```



修改zoo.cfg

```shell
#打开目录
cd /opt/zooKeeper/
#创建zooKeeper存储目录
mkdir  zkdata
#修改zoo.cfg
vim /opt/zooKeeper/apache-zooKeeper-3.5.6-bin/conf/zoo.cfg
```

![1577548250377](G:/2020%E6%96%B0%E8%AF%BE%E7%A8%8B/zookeeper-2020-%E8%AF%BE%E4%BB%B6/%E8%AE%B2%E4%B9%89/assets/1577548250377.png)

修改存储目录：dataDir=/opt/zookeeper/zkdata

#### **2.2.2、启动ZooKeeper**

```shell
cd /opt/zooKeeper/apache-zooKeeper-3.5.6-bin/bin/
#启动
 ./zkServer.sh  start
```

![1577548052037](G:/2020%E6%96%B0%E8%AF%BE%E7%A8%8B/zookeeper-2020-%E8%AF%BE%E4%BB%B6/%E8%AE%B2%E4%B9%89/assets/1577548052037.png)

看到上图表示ZooKeeper成功启动

**3、查看ZooKeeper状态**

```shell
./zkServer.sh status
```

zookeeper启动成功。standalone代表zk没有搭建集群，现在是单节点

![1577548175232](G:/2020%E6%96%B0%E8%AF%BE%E7%A8%8B/zookeeper-2020-%E8%AF%BE%E4%BB%B6/%E8%AE%B2%E4%B9%89/assets/1577548175232.png)

zookeeper没有启动

![1577548112773](G:/2020%E6%96%B0%E8%AF%BE%E7%A8%8B/zookeeper-2020-%E8%AF%BE%E4%BB%B6/%E8%AE%B2%E4%B9%89/assets/1577548112773.png)

### 

## 3)ZooKeeper 命令操作

### 3.1)Zookeeper命令操作数据模型

•ZooKeeper 是一个树形目录服务,其数据模型和Unix的文件系统目录树很类似，拥有一个层次化结构。

•这里面的每一个节点都被称为： ZNode，每个节点上都会保存自己的数据和节点信息。 

• 节点可以拥有子节点，同时也允许少量（1MB）数据存储在该节点之下。

•节点可以分为四大类：

•PERSISTENT 持久化节点 

•EPHEMERAL 临时节点 ：-e

•PERSISTENT_SEQUENTIAL 持久化顺序节点 ：-s

•EPHEMERAL_SEQUENTIAL 临时顺序节点  ：-es

![image-20210306221214895](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210306221214895.png)



### **3.2)Zookeeper命令操作服务端命令**

•启动 ZooKeeper 服务: ./zkServer.sh start

•查看 ZooKeeper 服务状态: ./zkServer.sh status

•停止 ZooKeeper 服务: ./zkServer.sh stop 

•重启 ZooKeeper 服务: ./zkServer.sh restart 

![1592055088686](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1592055088686.png)

### **3.3)Zookeeper客户端常用命令**

![image-20210307092008365](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210307092008365.png)

•连接ZooKeeper服务端

```shell
./zkCli.sh –server ip:port(localhost:2181)
```

•断开连接

```shell
quit
```

•查看命令帮助

```shell
help
```

•显示指定目录下节点

```
ls 目录
```

•创建节点

```
create /节点path value
```

•获取节点值

```
get /节点path
```

•设置节点值

```
set /节点path value
```

•删除单个节点

```
delete /节点path
```

•删除带有子节点的节点

```
deleteall /节点path
```

![1592055332198](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1592055332198.png)

![1592055345400](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1592055345400.png)

### 3.4)客户端命令-创建临时有序节点

•创建临时节点(ephemeral)

```
create -e /节点path value
```

•创建顺序节点(sequential)

```
create -s /节点path value
```

•查询节点详细信息

```
ls –s /节点path 
```

•czxid：节点被创建的事务ID 

•ctime: 创建时间 

•mzxid: 最后一次被更新的事务ID 

•mtime: 修改时间 

•pzxid：子节点列表最后一次被更新的事务ID

•cversion：子节点的版本号 

•dataversion：数据版本号 

•aclversion：权限版本号 

•ephemeralOwner：用于临时节点，代表临时节点的事务ID，如果为持久节点则为0 

•dataLength：节点存储的数据的长度 

•numChildren：当前节点的子节点个数 

![1592055462588](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1592055462588.png)

## 4)ZooKeeper JavaAPI 操作

### 4.1)urator介绍

•Curator 是 Apache ZooKeeper 的Java客户端库。

•常见的ZooKeeper Java API ：

•原生Java API

•ZkClient

•Curator

•Curator 项目的目标是简化 ZooKeeper 客户端的使用。

•Curator 最初是 Netfix 研发的,后来捐献了 Apache 基金会,目前是 Apache 的顶级项目。

•官网：http://curator.apache.org/



![image-20210307093243514](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210307093243514.png)



### 4.2)JavaAPI操作建立连接

1，搭建项目

创建项目curator-zk

引入pom和日志文件

资料文件夹下pom.xml和log4j.properties

![1592055569716](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1592055569716.png)

2、创建测试类，使用curator连接zookeeper

```java
@Before
public void testConnect() {
    //重试策略
    RetryPolicy retryPolicy = new ExponentialBackoffRetry(3000, 10);
    //1.第一种方式
    //CuratorFramework client = CuratorFrameworkFactory.newClient("192.168.23.129:2181",
    //            60 * 1000, 15 * 1000, retryPolicy); 
    //2.第二种方式
    //CuratorFrameworkFactory.builder();
    client = CuratorFrameworkFactory.builder()
        .connectString("192.168.200.130:2181")
        .sessionTimeoutMs(60 * 1000)
        .connectionTimeoutMs(15 * 1000)
        .retryPolicy(retryPolicy)
        .namespace("itheima")
        .build();
    //开启连接
    client.start();
}
```

### 4.3)JavaAPI操作-创建节点

创建节点：create （持久 临时 顺序） 数据

1 基本创建

2 创建节点 带有数据

3 设置节点的类型

4 创建多级节点   /app1/p1



```java
/**
* 创建节点：create 持久 临时 顺序 数据
* 1. 基本创建 ：create().forPath("")
* 2. 创建节点 带有数据:create().forPath("",data)
* 3. 设置节点的类型：create().withMode().forPath("",data)
* 4. 创建多级节点  /app1/p1 ：create().creatingParentsIfNeeded().forPath("",data)
*/


@Test
public void testCreate() throws Exception {
    //2. 创建节点 带有数据
    //如果创建节点，没有指定数据，则默认将当前客户端的ip作为数据存储
    String path = client.create().forPath("/app2", "hehe".getBytes());
    System.out.println(path);
}
```

```java
@Test
public void testCreate2() throws Exception {
    //1. 基本创建
    //如果创建节点，没有指定数据，则默认将当前客户端的ip作为数据存储
    String path = client.create().forPath("/app1");
    System.out.println(path);
}
@Test
public void testCreate3() throws Exception {
    //3. 设置节点的类型
    //默认类型：持久化
    String path = client.create().withMode(CreateMode.EPHEMERAL).forPath("/app3");
    System.out.println(path);
}
@Test
public void testCreate4() throws Exception {
    //4. 创建多级节点  /app1/p1
    //creatingParentsIfNeeded():如果父节点不存在，则创建父节点
    String path = client.create().creatingParentsIfNeeded().forPath("/app4/p1");
    System.out.println(path);
}
```

### 4.4)JavaAPI操作-查询节点

```java
/**
* 查询节点：
* 1. 查询数据：get: getData().forPath()
* 2. 查询子节点： ls: getChildren().forPath()
* 3. 查询节点状态信息：ls -s:getData().storingStatIn(状态对象).forPath()
*/
@Test
public void testGet1() throws Exception {
    //1. 查询数据：get
    byte[] data = client.getData().forPath("/app1");
    System.out.println(new String(data));
}
```

```JAVA
@Test
public void testGet2() throws Exception {
    // 2. 查询子节点： ls
    List<String> path = client.getChildren().forPath("/");
    System.out.println(path);
}
@Test
public void testGet3() throws Exception {
    Stat status = new Stat();
    System.out.println(status);
    //3. 查询节点状态信息：ls -s
    client.getData().storingStatIn(status).forPath("/app1");
    System.out.println(status);
}
```

### 4.5)JavaAPI操作-修改节点

```JAVA
/**
* 修改数据
* 1. 基本修改数据：setData().forPath()
* 2. 根据版本修改: setData().withVersion().forPath()
* * version 是通过查询出来的。目的就是为了让其他客户端或者线程不干扰我。
*
* @throws Exception
*/
@Test
public void testSet() throws Exception {
	client.setData().forPath("/app1", "itcast".getBytes());
}
```

```JAVA
@Test
public void testSetForVersion() throws Exception {
    Stat status = new Stat();
    //3. 查询节点状态信息：ls -s
    client.getData().storingStatIn(status).forPath("/app1");
    int version = status.getVersion();//查询出来的 3
    System.out.println(version);
    client.setData().withVersion(version).forPath("/app1", "hehe".getBytes());
}
```

### 4.6)JavaAPI操作-删除节点

```JAVA
/**
* 删除节点： delete deleteall
* 1. 删除单个节点:delete().forPath("/app1");
* 2. 删除带有子节点的节点:delete().deletingChildrenIfNeeded().forPath("/app1");
* 3. 必须成功的删除:为了防止网络抖动。本质就是重试。  client.delete().guaranteed().forPath("/app2");
* 4. 回调：inBackground
* @throws Exception
*/
@Test
public void testDelete() throws Exception {
    // 1. 删除单个节点
    client.delete().forPath("/app1");
}
@Test
public void testDelete2() throws Exception {
    //2. 删除带有子节点的节点
    client.delete().deletingChildrenIfNeeded().forPath("/app4");
}
```

```JAVA
@Test
public void testDelete3() throws Exception {
    //3. 必须成功的删除
    client.delete().guaranteed().forPath("/app2");
}
@Test
public void testDelete4() throws Exception {
    //4. 回调
    client.delete().guaranteed().inBackground(new BackgroundCallback(){
        @Override
        public void processResult(CuratorFramework client, CuratorEvent event) throws Exception {
            System.out.println("我被删除了~");
            System.out.println(event);
        }
    }).forPath("/app1");
}
```

### 4.7)JavaAPI操作-Watch监听概述

![image-20210307104739019](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210307104739019.png)

•ZooKeeper 允许用户在指定节点上注册一些Watcher，并且在一些特定事件触发的时候，ZooKeeper 服务端会将事件通知到感兴趣的客户端上去，该机制是 ZooKeeper 实现分布式协调服务的重要特性。

•ZooKeeper 中引入了Watcher机制来实现了发布/订阅功能能，能够让多个订阅者同时监听某一个对象，当一个对象自身状态变化时，会通知所有订阅者。

•ZooKeeper 原生支持通过注册Watcher来进行事件监听，但是其使用并不是特别方便

​    需要开发人员自己反复注册Watcher，比较繁琐。

•Curator引入了 Cache 来实现对 ZooKeeper 服务端事件的监听。

•ZooKeeper提供了三种Watcher：

​	•NodeCache : 只是监听某一个特定的节点

​	•PathChildrenCache : 监控一个ZNode的子节点. 

​	•TreeCache : 可以监控整个树上的所有节点，类似于PathChildrenCache和NodeCache的组合

![1592057429708](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1592057429708.png)

### 4.8)JavaAPI操作-Watch监听-NodeCache

```java
/**
* 演示 NodeCache：给指定一个节点注册监听器
*/
@Test
public void testNodeCache() throws Exception {
    //1. 创建NodeCache对象
    final NodeCache nodeCache = new NodeCache(client,"/app1");
    //2. 注册监听
   	nodeCache.getListenable().addListener(new NodeCacheListener() {
        @Override
        public void nodeChanged() throws Exception {
            System.out.println("节点变化了~");
            //获取修改节点后的数据
            byte[] data = nodeCache.getCurrentData().getData();
            System.out.println(new String(data));
            }
        });
    	//3. 开启监听.如果设置为true，则开启监听是，加载缓冲数据
    	nodeCache.start(true);
    	while (true){
    }
}
```

### **4.9) JavaAPI操作-Watch监听-PathChildrenCache

```java
@Test
public void testPathChildrenCache() throws Exception {
    //1.创建监听对象
    PathChildrenCache pathChildrenCache = new PathChildrenCache(client,"/app2",true);
    //2. 绑定监听器
    pathChildrenCache.getListenable().addListener(new PathChildrenCacheListener() {    			@Override
        public void childEvent(CuratorFramework client, PathChildrenCacheEvent event) throws Exception {
            System.out.println("子节点变化了~");
            System.out.println(event);
            //监听子节点的数据变更，并且拿到变更后的数据
            //1.获取类型
            PathChildrenCacheEvent.Type type = event.getType();
            //2.判断类型是否是update
            if(type.equals(PathChildrenCacheEvent.Type.CHILD_UPDATED)){
                System.out.println("数据变了！！！");
                byte[] data = event.getData().getData();
                System.out.println(new String(data));
            }
        }
    });
    //3. 开启
    pathChildrenCache.start();
    while (true){
    }
}
```

### **4.10)JavaAPI操作-Watch监听-TreeCache

```java
/**
* 演示 TreeCache：监听某个节点自己和所有子节点们
*/
@Test
public void testTreeCache() throws Exception {
    //1. 创建监听器
    TreeCache treeCache = new TreeCache(client,"/app2");
    //2. 注册监听
    treeCache.getListenable().addListener(new TreeCacheListener() {
        @Override
        public void childEvent(CuratorFramework client, TreeCacheEvent event) throws Exception {
            System.out.println("节点变化了");
            System.out.println(event);
        }
    });
    //3. 开启
    treeCache.start();
    while (true){
    }
}
```

### 4.11)分布式锁-概念

•在我们进行单机应用开发，涉及并发同步的时候，我们往往采用synchronized或者Lock的方式来解决多线程间的代码同步问题，这时多线程的运行都是在同一个JVM之下，没有任何问题。

•但当我们的应用是分布式集群工作的情况下，属于多JVM下的工作环境，跨JVM之间已经无法通过多线程的锁解决同步问题。

•那么就需要一种更加高级的锁机制，来处理种跨机器的进程之间的数据同步问题——这就是分布式锁。

![1592057871141](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1592057871141-1615105055483.png)

### 4.12)zookeeper分布式锁原理

•核心思想：当客户端要获取锁，则创建节点，使用完锁，则删除该节点。

1.客户端获取锁时，在lock节点下创建<font color = "red">临时顺序</font>节点。

2.然后获取lock下面的所有子节点，客户端获取到所有的子节点之后，如果发现自己创建的子节点序号最小，那么就认为该客户端获取到了锁。使用完锁后，将该节点删除。

3.如果发现自己创建的节点并非lock所有子节点中最小的，说明自己还没有获取到锁，此时客户端需要找到比自己小的那个节点，同时对其<font color = "red">注册事件监听器</font>，监听删除事件。

4.如果发现比自己小的那个节点被删除，则客户端的

​    Watcher会收到相应通知，此时再次判断自己创建的节点

​    是否是lock子节点中序号最小的，如果是则获取到了锁，

​    如果不是则重复以上步骤继续获取到比自己小的一个节点

​    并注册监听。

![1592057925831](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1592057925831.png)

### **4.13)Zookeeper** 分布式锁-模拟12306售票案例

**Curator实现分布式锁API**

- 在Curator中有五种锁方案：

  - InterProcessSemaphoreMutex：分布式排它锁（非可重入锁）

  - InterProcessMutex：分布式可重入排它锁

  - InterProcessReadWriteLock：分布式读写锁

  - InterProcessMultiLock：将多个锁作为单个实体管理的容器

  - InterProcessSemaphoreV2：共享信号量

![1592058017457](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1592058017457.png)

1,创建线程进行加锁设置

```java
public class Ticket12306 implements Runnable{
    private int tickets = 10;//数据库的票数
    private InterProcessMutex lock ;
    @Override
    public void run() {
        while(true){
            //获取锁
            try {
            lock.acquire(3, TimeUnit.SECONDS);
                if(tickets > 0){
                    System.out.println(Thread.currentThread()+":"+tickets);
                    Thread.sleep(100);
                    tickets--;
                }
            } catch (Exception e) {
                e.printStackTrace();
            }finally {
                //释放锁
                try {
                    lock.release();
                } catch (Exception e) {
                    e.printStackTrace();
                }

            }
        }
    }
}
```

2,创建连接，并且初始化锁

```java
public Ticket12306(){
    //重试策略
    RetryPolicy retryPolicy = new ExponentialBackoffRetry(3000, 10);
    //2.第二种方式
    //CuratorFrameworkFactory.builder();
    CuratorFramework client = CuratorFrameworkFactory.builder()
        .connectString("192.168.149.135:2181")
        .sessionTimeoutMs(60 * 1000)
        .connectionTimeoutMs(15 * 1000)
        .retryPolicy(retryPolicy)
        .build();
    //开启连接
    client.start();
    lock = new InterProcessMutex(client,"/lock");
}
```

3,运行多个线程进行测试

```java
public class LockTest {
    public static void main(String[] args) {
        Ticket12306 ticket12306 = new Ticket12306();
        //创建客户端
        Thread t1 = new Thread(ticket12306,"携程");
        Thread t2 = new Thread(ticket12306,"飞猪");
        t1.start();
        t2.start();
    }
}
```

## 5)ZooKeeper 集群搭建

### **5.1)Zookeeper**集群介绍

Leader选举：

•Serverid：服务器ID

  比如有三台服务器，编号分别是1,2,3。

  编号越大在选择算法中的权重越大。

•Zxid：数据ID

  服务器中存放的最大数据ID.值越大说明数据  越新，在选举算法中数据越新权重越大。

•在Leader选举的过程中，如果某台ZooKeeper

​    获得了超过半数的选票，

​    则此ZooKeeper就可以成为Leader了。



![image-20210307155524517](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210307155524517.png)





### 5.2)搭建要求

真实的集群是需要部署在不同的服务器上的，但是在我们测试时同时启动很多个虚拟机内存会吃不消，所以我们通常会搭建**伪集群**，也就是把所有的服务都搭建在一台虚拟机上，用端口进行区分。

我们这里要求搭建一个三个节点的Zookeeper集群（伪集群）。

### **5.3)准备工作**

重新部署一台虚拟机作为我们搭建集群的测试服务器。

（1）安装JDK  【此步骤省略】。

（2）Zookeeper压缩包上传到服务器
（3）将Zookeeper解压 ，建立/usr/local/zookeeper-cluster目录，将解压后的Zookeeper复制到以下三个目录

/usr/local/zookeeper-cluster/zookeeper-1

/usr/local/zookeeper-cluster/zookeeper-2

/usr/local/zookeeper-cluster/zookeeper-3

```shell
[root@localhost ~]# mkdir /usr/local/zookeeper-cluster
[root@localhost ~]# cp -r  apache-zookeeper-3.5.6-bin /usr/local/zookeeper-cluster/zookeeper-1
[root@localhost ~]# cp -r  apache-zookeeper-3.5.6-bin /usr/local/zookeeper-cluster/zookeeper-2
[root@localhost ~]# cp -r  apache-zookeeper-3.5.6-bin /usr/local/zookeeper-cluster/zookeeper-3
```

（4）创建data目录 ，并且将 conf下zoo_sample.cfg 文件改名为 zoo.cfg

```shell
mkdir /usr/local/zookeeper-cluster/zookeeper-1/data
mkdir /usr/local/zookeeper-cluster/zookeeper-2/data
mkdir /usr/local/zookeeper-cluster/zookeeper-3/data

mv  /usr/local/zookeeper-cluster/zookeeper-1/conf/zoo_sample.cfg  /usr/local/zookeeper-cluster/zookeeper-1/conf/zoo.cfg
mv  /usr/local/zookeeper-cluster/zookeeper-2/conf/zoo_sample.cfg  /usr/local/zookeeper-cluster/zookeeper-2/conf/zoo.cfg
mv  /usr/local/zookeeper-cluster/zookeeper-3/conf/zoo_sample.cfg  /usr/local/zookeeper-cluster/zookeeper-3/conf/zoo.cfg
```





（5） 配置每一个Zookeeper 的dataDir 和 clientPort 分别为2181  2182  2183

修改/usr/local/zookeeper-cluster/zookeeper-1/conf/zoo.cfg

```shell
vim /usr/local/zookeeper-cluster/zookeeper-1/conf/zoo.cfg

clientPort=2181
dataDir=/usr/local/zookeeper-cluster/zookeeper-1/data
```

修改/usr/local/zookeeper-cluster/zookeeper-2/conf/zoo.cfg

```shell
vim /usr/local/zookeeper-cluster/zookeeper-2/conf/zoo.cfg

clientPort=2182
dataDir=/usr/local/zookeeper-cluster/zookeeper-2/data
```

修改/usr/local/zookeeper-cluster/zookeeper-3/conf/zoo.cfg

```shell
vim /usr/local/zookeeper-cluster/zookeeper-3/conf/zoo.cfg

clientPort=2183
dataDir=/usr/local/zookeeper-cluster/zookeeper-3/data
```



### **5.4)配置集群**

（1）在每个zookeeper的 data 目录下创建一个 myid 文件，内容分别是1、2、3 。这个文件就是记录每个服务器的ID

```shell
echo 1 >/usr/local/zookeeper-cluster/zookeeper-1/data/myid
echo 2 >/usr/local/zookeeper-cluster/zookeeper-2/data/myid
echo 3 >/usr/local/zookeeper-cluster/zookeeper-3/data/myid
```





（2）在每一个zookeeper 的 zoo.cfg配置客户端访问端口（clientPort）和集群服务器IP列表。

集群服务器IP列表如下

```shell
vim /usr/local/zookeeper-cluster/zookeeper-1/conf/zoo.cfg
vim /usr/local/zookeeper-cluster/zookeeper-2/conf/zoo.cfg
vim /usr/local/zookeeper-cluster/zookeeper-3/conf/zoo.cfg

server.1=192.168.149.135:2881:3881
server.2=192.168.149.135:2882:3882
server.3=192.168.149.135:2883:3883
```

解释：server.服务器ID=服务器IP地址：服务器之间通信端口：服务器之间投票选举端口



 

### **5.5)启动集群**

启动集群就是分别启动每个实例。

```shell
/usr/local/zookeeper-cluster/zookeeper-1/bin/zkServer.sh start
/usr/local/zookeeper-cluster/zookeeper-2/bin/zkServer.sh start
/usr/local/zookeeper-cluster/zookeeper-3/bin/zkServer.sh start
```





启动后我们查询一下每个实例的运行状态

```shell
/usr/local/zookeeper-cluster/zookeeper-1/bin/zkServer.sh status
/usr/local/zookeeper-cluster/zookeeper-2/bin/zkServer.sh status
/usr/local/zookeeper-cluster/zookeeper-3/bin/zkServer.sh status
```



先查询第一个服务



Mode为follower表示是**跟随者**（从）

再查询第二个服务Mod 为leader表示是**领导者**（主）

![image-20210307160429919](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210307160429919.png)

查询第三个为跟随者（从）





### **5.6)模拟集群异常**

（1）首先我们先测试如果是从服务器挂掉，会怎么样

把3号服务器停掉，观察1号和2号，发现状态并没有变化

```shell
/usr/local/zookeeper-cluster/zookeeper-3/bin/zkServer.sh stop

/usr/local/zookeeper-cluster/zookeeper-1/bin/zkServer.sh status
/usr/local/zookeeper-cluster/zookeeper-2/bin/zkServer.sh status
```



由此得出结论，3个节点的集群，从服务器挂掉，集群正常

（2）我们再把1号服务器（从服务器）也停掉，查看2号（主服务器）的状态，发现已经停止运行了。

```shell
/usr/local/zookeeper-cluster/zookeeper-1/bin/zkServer.sh stop

/usr/local/zookeeper-cluster/zookeeper-2/bin/zkServer.sh status
```





由此得出结论，3个节点的集群，2个从服务器都挂掉，主服务器也无法运行。因为可运行的机器没有超过集群总数量的半数。

（3）我们再次把1号服务器启动起来，发现2号服务器又开始正常工作了。而且依然是领导者。

```shell
/usr/local/zookeeper-cluster/zookeeper-1/bin/zkServer.sh start

/usr/local/zookeeper-cluster/zookeeper-2/bin/zkServer.sh status
```





（4）我们把3号服务器也启动起来，把2号服务器停掉,停掉后观察1号和3号的状态。

```shell
/usr/local/zookeeper-cluster/zookeeper-3/bin/zkServer.sh start
/usr/local/zookeeper-cluster/zookeeper-2/bin/zkServer.sh stop

/usr/local/zookeeper-cluster/zookeeper-1/bin/zkServer.sh status
/usr/local/zookeeper-cluster/zookeeper-3/bin/zkServer.sh status
```





发现新的leader产生了~  

由此我们得出结论，当集群中的主服务器挂了，集群中的其他服务器会自动进行选举状态，然后产生新得leader 

（5）我们再次测试，当我们把2号服务器重新启动起来启动后，会发生什么？2号服务器会再次成为新的领导吗？我们看结果

```shell
/usr/local/zookeeper-cluster/zookeeper-2/bin/zkServer.sh start

/usr/local/zookeeper-cluster/zookeeper-2/bin/zkServer.sh status
/usr/local/zookeeper-cluster/zookeeper-3/bin/zkServer.sh status
```



![img](G:/2020%E6%96%B0%E8%AF%BE%E7%A8%8B/zookeeper-2020-%E8%AF%BE%E4%BB%B6/%E8%B5%84%E6%96%99/images/wps19.jpg)![img](G:/2020%E6%96%B0%E8%AF%BE%E7%A8%8B/zookeeper-2020-%E8%AF%BE%E4%BB%B6/%E8%B5%84%E6%96%99/images/wps20.jpg) 

我们会发现，2号服务器启动后依然是跟随者（从服务器），3号服务器依然是领导者（主服务器），没有撼动3号服务器的领导地位。

由此我们得出结论，当领导者产生后，再次有新服务器加入集群，不会影响到现任领导者。



## 6)Zookeeper 集群核心理论

**Zookeepe集群角色**

在ZooKeeper集群服中务中有三个角色：

•Leader 领导者 ：          

​	1. 处理事务请求（增删改是事务，查不是事务）

​	2. 集群内部各服务器的调度者

•Follower 跟随者 ：

​	1. 处理客户端非事务请求，转发事务请求给Leader服务器

​	2. 参与Leader选举投票

•Observer 观察者：

	1. 处理客户端非事务请求，转发事务请求给Leader服务器

![image-20210307160815803](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210307160815803.png)

