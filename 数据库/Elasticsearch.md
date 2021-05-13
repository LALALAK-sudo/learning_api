## **1-今日内容**

1.  初识 ElasticSearch

2. 安装 ElasticSearch
3. ElasticSearch 核心概念
4. 操作 ElasticSearch
5.  ElasticSearch JavaAPI

 

## **2-初识ElasticSearch**

### 2.1-基于数据库查询的问题

ElasticSearch是一个搜索服务器

搜索就是查询

select * from xxx  ---------> 关系型数据库



![1580888245982](img/1580888245982.png)

 ![image-20210310084849278](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310084849278.png)









### **2.2-倒排索引**

**倒排索引**：将文档进行分词，形成词条和id的对应关系即为反向索引。

 以唐诗为例，所处包含“前”的诗句

正向索引：由《静夜思》-->窗前明月光--->“前”字（大脑储存数据）

![image-20210310085019102](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310085019102.png)



反向索引：“前”字-->窗前明月光-->《静夜思》

反向索引的实现就是对诗句进行分词，分成单个的词，由词推据，即为反向索引



“床前明月光”--> 分词

将一段文本按照一定的规则，拆分为不同的词条（term）



![image-20210319120451091](D:\h后端\imgs\image-20210319120451091.png)

**倒排索引:将各个文档中的内容,进行分词,形成词条。然后记录词条和数据的唯一标识(id)的对应关系，形成的产物。**

![image-20210319120512594](D:\h后端\imgs\image-20210319120512594.png)



### **2.3-ES存储和查询的原理**

 

**index（索引）**：相当于mysql的库

**映射**：相当于mysql 的表结构

**document(文档)**：相当于mysql的表中的数据



 **数据库查询存在的问题：**

1. 性能低：使用模糊查询，左边有通配符，不会走索引，会全表扫描，性能低
2.  功能弱：如果以”华为手机“作为条件，查询不出来数据

Es使用倒排索引，对title 进行分词



![1581143412491](img/1581143412491.png)

 

1. 使用“手机”作为关键字查询

   生成的倒排索引中，词条会排序，形成一颗**树形结构**，提升词条的查询速度

2. 使用“华为手机”作为关键字查询

   华为：1,3

   手机：1,2,3

   ![1581143489911](img/1581143489911.png)

### **2.4-ES概念详解**

•ElasticSearch是一个基于Lucene的搜索服务器

![1580887955947](img/1580887955947.png)

•是一个分布式、高扩展、高实时的搜索与数据分析引擎

•基于RESTful web接口

•Elasticsearch是用Java语言开发的，并作为Apache许可条款下的开放源码发布，是一种流行的企业级搜索引擎

•官网：https://www.elastic.co/





应用场景

•搜索：海量数据的查询

•日志数据分析

•实时数据分析



逻辑外键：你只要把id属性放到从表中，思想上知道表与表之间是怎么关联的就行，不需要额外设置。物理外键：当你把id属性放到从表中时，还要通过references属性进行硬性关联。

![image-20210310091028237](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310091028237.png)







## **3-安装ElasticSearch**

### 3.1-ES安装

 参见ElasticSearch-ES安装.md

 查看elastic是否启动

```
ps -ef|grep elastic
```



### **3.2-ES辅助工具安装**

 参见ElasticSearch-ES安装.md

后台启动

```
nohup ../bin/kibana &
```

 

## **4-ElasticSearch核心概念**

 ![image-20210310121024392](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310121024392.png)

**索引（index）**

ElasticSearch存储数据的地方，可以理解成关系型数据库中的数据库概念。

**映射（mapping）**

mapping定义了每个字段的类型、字段所使用的分词器等。相当于关系型数据库中的表结构。

**文档（document）**

   Elasticsearch中的最小数据单元，常以json格式显示。一个document相当于关系型数据库中的一行数据。

**倒排索引**

   一个倒排索引由文档中所有不重复词的列表构成，对于其中每个词，对应一个包含它的文档id列表。

**类型（type）**

   一种type就像一类表。如用户表、角色表等。在Elasticsearch7.X默认type为_doc

     \- ES 5.x中一个index可以有多种type。
    
      \- ES 6.x中一个index只能有一种type。
    
      \- ES 7.x以后，将逐步移除type这个概念，现在的操作已经不再使用，默认_doc

 








## **5-脚本操作ES**

### 5.1-RESTful风格介绍

 1.ST（Representational State Transfer），表述性状态转移，是一组架构约束条件和原则。满足这些约束条件和原则的应用程序或设计就是RESTful。就是一种定义接口的规范。

2.基于HTTP。

3.使用XML格式定义或JSON格式定义。

4.每一个URI代表1种资源。

5.客户端使用GET、POST、PUT、DELETE 4个表示操作方式的动词对服务端资源进行操作：

<font  color="red">GET：用来获取资源</font>

<font  color="red">POST：用来新建资源（也可以用于更新资源）</font>

<font  color="red">PUT：用来更新资源</font>

<font  color="red">DELETE：用来删除资源</font>



![image-20210310121345497](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310121345497.png)



 

### **5.2-操作索引**

 ![image-20210310162150773](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310162150773.png)

添加索引----**PUT**

```
http://ip:端口/索引名称
```

查询索引

```
GET http://ip:端口/索引名称  # 查询单个索引信息
GET http://ip:端口/索引名称1,索引名称2...  # 查询多个索引信息
GET http://ip:端口/_all  # 查询所有索引信息
```

•删除索引

```
DELETE http://ip:端口/索引名称
```

•关闭、打开索引

```
POST http://ip:端口/索引名称/_close  
POST http://ip:端口/索引名称/_open 
```




### **5.3-ES数据类型**

 

1. **简单数据类型**

- 字符串

聚合：相当于mysql 中的sum（求和）

```text
text：会分词，不支持聚合

keyword：不会分词，将全部内容作为一个词条，支持聚合
```

- 数值
- 布尔：boolean

- 二进制：binary
- 范围类型


```
integer_range, float_range, long_range, double_range, date_range 
```

- 日期:date

2. **复杂数据类型**

•数组：[ ]  Nested: `nested` (for arrays of JSON objects 数组类型的JSON对象)  

•对象：{ } Object: object(for single JSON objects 单个JSON对象)

![image-20210310162923880](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310162923880.png)



### **5.4-操作映射**

 ![image-20210310163129375](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310163129375.png)

```json
 PUT person
 
 GET person
 #添加映射
 PUT /person/_mapping
 {
   "properties":{
     "name":{
       "type":"text"
     },
     "age":{
       "type":"integer"
     }
   }
 }


 
```

 ![image-20210310164153595](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310164153595.png)

 #创建索引并添加映射

```json
 
 #创建索引并添加映射
 PUT /person1
{
  "mappings": {
    "properties": {
      "name": {
        "type": "text"
      },
      "age": {
        "type": "integer"
      }
    }
  }
}

GET person1/_mapping
```



添加字段

```json
#添加字段
PUT /person1/_mapping
{
  "properties": {
      "name": {
        "type": "text"
      },
      "age": {
        "type": "integer"
      }
    }
}
```



![image-20210310164339400](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310164339400.png)













### **5.5-操作文档**

 

•添加文档，指定id

```json
#添加文档，指定id put可以
PUT person1/_doc/2
{
  "name":"张三",
  "age":18,
  "address":"北京"
}

GET person1/_doc/1


```

 •添加文档，不指定id

```json
#添加文档，不指定id put不可以
POST person1/_doc/
{
  "name":"张三",
  "age":18,
  "address":"北京"
}

#查询所有文档
GET person1/_search
```



```json
#删除指定id文档
DELETE /person1/_doc/1
```





## 6-分词器

![image-20210310170114350](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310170114350.png)

###  6.1 IK分词器-介绍

 •IKAnalyzer是一个开源的，基于java语言开发的轻量级的中文分词工具包

•是一个基于Maven构建的项目

•具有60万字/秒的高速处理能力

•支持用户词典扩展定义

•下载地址：https://github.com/medcl/elasticsearch-analysis-ik/archive/v7.4.0.zip 

安装包在资料文件夹中提供



### **6.2-ik分词器安装**

参见 ik分词器安装.md

 执行如下命令时如果出现  打包失败（501码）将maven镜像换成阿里云的

```
mvn package
```

 /opt/apache-maven-3.1.1/conf/setting.xml

```xml
	<mirror>
        <id>alimaven</id>
        <name>aliyun maven</name>
        <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
        <mirrorOf>central</mirrorOf>
    </mirror>
```





### **6.3-ik分词器使用**

IK分词器有两种分词模式：**ik_max_word**和**ik_smart**模式。

1、**ik_max_word**

会将文本做最细粒度的拆分，比如会将“乒乓球明年总冠军”拆分为“乒乓球、乒乓、球、明年、总冠军、冠军。

```json
#方式一ik_max_word
GET /_analyze
{
  "analyzer": "ik_max_word",
  "text": "乒乓球明年总冠军"
}
```

ik_max_word分词器执行如下：

```json
{
  "tokens" : [
    {
      "token" : "乒乓球",
      "start_offset" : 0,
      "end_offset" : 3,
      "type" : "CN_WORD",
      "position" : 0
    },
    {
      "token" : "乒乓",
      "start_offset" : 0,
      "end_offset" : 2,
      "type" : "CN_WORD",
      "position" : 1
    },
    {
      "token" : "球",
      "start_offset" : 2,
      "end_offset" : 3,
      "type" : "CN_CHAR",
      "position" : 2
    },
    {
      "token" : "明年",
      "start_offset" : 3,
      "end_offset" : 5,
      "type" : "CN_WORD",
      "position" : 3
    },
    {
      "token" : "总冠军",
      "start_offset" : 5,
      "end_offset" : 8,
      "type" : "CN_WORD",
      "position" : 4
    },
    {
      "token" : "冠军",
      "start_offset" : 6,
      "end_offset" : 8,
      "type" : "CN_WORD",
      "position" : 5
    }
  ]
}

```

2、**ik_smart**
会做最粗粒度的拆分，比如会将“乒乓球明年总冠军”拆分为乒乓球、明年、总冠军。

```json
#方式二ik_smart
GET /_analyze
{
  "analyzer": "ik_smart",
  "text": "乒乓球明年总冠军"
}
```

ik_smart分词器执行如下：

```json
{
  "tokens" : [
    {
      "token" : "乒乓球",
      "start_offset" : 0,
      "end_offset" : 3,
      "type" : "CN_WORD",
      "position" : 0
    },
    {
      "token" : "明年",
      "start_offset" : 3,
      "end_offset" : 5,
      "type" : "CN_WORD",
      "position" : 1
    },
    {
      "token" : "总冠军",
      "start_offset" : 5,
      "end_offset" : 8,
      "type" : "CN_WORD",
      "position" : 2
    }
  ]
}

```

由此可见  使用ik_smart可以将文本"text": "乒乓球明年总冠军"分成了【乒乓球】【明年】【总冠军】

这样看的话，这样的分词效果达到了我们的要求。

 

### **6.4使用IK分词器-查询文档**

<font color="red">创建mapping的时候要指定分词器哟</font>

 •词条查询：term

​			词条查询不会分析查询条件，只有当词条和查询字符串完全匹配时才匹配搜索

•全文查询：match

​           全文查询会分析查询条件，先将查询条件进行分词，然后查询，求并集



1.创建索引，添加映射，并指定分词器为ik分词器

```json
PUT person2
{
  "mappings": {
    "properties": {
      "name": {
        "type": "keyword"
      },
      "address": {
        "type": "text",
        "analyzer": "ik_max_word"
      }
    }
  }
}
```

2.添加文档

```
POST /person2/_doc/1
{
  "name":"张三",
  "age":18,
  "address":"北京海淀区"
}

POST /person2/_doc/2
{
  "name":"李四",
  "age":18,
  "address":"北京朝阳区"
}

POST /person2/_doc/3
{
  "name":"王五",
  "age":18,
  "address":"北京昌平区"
}

```



3.查询映射

```json
GET person2
```



4.查看分词效果

```json
GET _analyze
{
  "analyzer": "ik_max_word",
  "text": "北京海淀"
}

```





5.词条查询：term

查询person2中匹配到"北京"两字的词条

```json
GET /person2/_search
{
  "query": {
    "term": {
      "address": {
        "value": "北京"
      }
    }
  }
}
```



6.全文查询：match

​           全文查询会分析查询条件，先将查询条件进行分词，然后查询，求并集

```
GET /person2/_search
{
  "query": {
    "match": {
      "address":"北京昌平"
    }
  }
}
```





## **7-ElasticSearch JavaApi-**

 

### 7.1SpringBoot整合ES

 ①搭建SpringBoot工程

②引入ElasticSearch相关坐标

```xml
<!--引入es的坐标-->
        <dependency>
            <groupId>org.elasticsearch.client</groupId>
            <artifactId>elasticsearch-rest-high-level-client</artifactId>
            <version>7.4.0</version>
        </dependency>
        <dependency>
            <groupId>org.elasticsearch.client</groupId>
            <artifactId>elasticsearch-rest-client</artifactId>
            <version>7.4.0</version>
        </dependency>
        <dependency>
            <groupId>org.elasticsearch</groupId>
            <artifactId>elasticsearch</artifactId>
            <version>7.4.0</version>
        </dependency>
```

为了不是每次都要获取client所有用配置类

![image-20210310204922325](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210310204922325.png)



③测试

ElasticSearchConfig

```java
@Configuration
@ConfigurationProperties(prefix="elasticsearch")
public class ElasticSearchConfig {

    private String host;

    private int port;

 
    public String getHost() {
        return host;
    }

    public void setHost(String host) {
        this.host = host;
    }

    public int getPort() {
        return port;
    }

    public void setPort(int port) {
        this.port = port;
    }
    @Bean
    public RestHighLevelClient client(){
        // http://192.168.23.129:5601/
        return new RestHighLevelClient(RestClient.builder(
                new HttpHost(host,port,"http")
        ));
    }
}
```

ElasticsearchDay01ApplicationTests

注意：使用@Autowired注入RestHighLevelClient 如果报红线，则是因为配置类所在的包和测试类所在的包，包名不一致造成的

```java
@SpringBootTest
class ElasticsearchDay01ApplicationTests {

    @Autowired
    RestHighLevelClient client;

    /**
     * 测试
     */
    @Test
    void contextLoads() {

        System.out.println(client);
    }
}
```



### **7.2-创建索引**

1.添加索引

 ```java
/**
     * 添加索引
     * @throws IOException
     */
    @Test
    public void addIndex() throws IOException {
       //1.使用client获取操作索引对象
        IndicesClient indices = client.indices();
        //2.具体操作获取返回值
        //2.1 设置索引名称
        CreateIndexRequest createIndexRequest=new CreateIndexRequest("itheima");

        CreateIndexResponse createIndexResponse = indices.create(createIndexRequest, RequestOptions.DEFAULT);
        //3.根据返回值判断结果
        System.out.println(createIndexResponse.isAcknowledged());
    }
 ```
2.添加索引，并添加映射

```java
 /**
     * 添加索引，并添加映射
     */
    @Test
    public void addIndexAndMapping() throws IOException {
       //1.使用client获取操作索引对象
        IndicesClient indices = client.indices();
        //2.具体操作获取返回值
        //2.具体操作，获取返回值
        CreateIndexRequest createIndexRequest = new CreateIndexRequest("itcast");
        //2.1 设置mappings
        String mapping = "{\n" +
                "      \"properties\" : {\n" +
                "        \"address\" : {\n" +
                "          \"type\" : \"text\",\n" +
                "          \"analyzer\" : \"ik_max_word\"\n" +
                "        },\n" +
                "        \"age\" : {\n" +
                "          \"type\" : \"long\"\n" +
                "        },\n" +
                "        \"name\" : {\n" +
                "          \"type\" : \"keyword\"\n" +
                "        }\n" +
                "      }\n" +
                "    }";
        createIndexRequest.mapping(mapping,XContentType.JSON);

        CreateIndexResponse createIndexResponse = indices.create(createIndexRequest, RequestOptions.DEFAULT);
        //3.根据返回值判断结果
        System.out.println(createIndexResponse.isAcknowledged());
    }

```

 

### **7.3-查询、删除、判断索引**



查询索引
```java

   

    /**
     * 查询索引
     */
    @Test
    public void queryIndex() throws IOException {
        IndicesClient indices = client.indices();

        GetIndexRequest getRequest=new GetIndexRequest("itcast");
        GetIndexResponse response = indices.get(getRequest, RequestOptions.DEFAULT);
        Map<String, MappingMetaData> mappings = response.getMappings();
        //iter 提示foreach
        for (String key : mappings.keySet()) {
            System.out.println(key+"==="+mappings.get(key).getSourceAsMap());
        }
    }

   
   
```

删除索引

```java
 /**
     * 删除索引
     */
    @Test
    public void deleteIndex() throws IOException {
         IndicesClient indices = client.indices();
        DeleteIndexRequest deleteRequest=new DeleteIndexRequest("itheima");
        AcknowledgedResponse delete = indices.delete(deleteRequest, RequestOptions.DEFAULT);
        System.out.println(delete.isAcknowledged());

    }
```



索引是否存在

```java
 /**
     * 索引是否存在
     */
    @Test
    public void existIndex() throws IOException {
        IndicesClient indices = client.indices();

        GetIndexRequest getIndexRequest=new GetIndexRequest("itheima");
        boolean exists = indices.exists(getIndexRequest, RequestOptions.DEFAULT);


        System.out.println(exists);

    }
    
```



### **7.4-添加文档**

1.添加文档,使用map作为数据

```java
 @Test
    public void addDoc1() throws IOException {
        Map<String, Object> map=new HashMap<>();
        map.put("name","张三");
        map.put("age","18");
        map.put("address","北京二环");
        IndexRequest request=new IndexRequest("itcast").id("1").source(map);
        IndexResponse response = client.index(request, RequestOptions.DEFAULT);
        System.out.println(response.getId());
    }
```

 2.添加文档,使用对象作为数据

```java
@Test
public void addDoc2() throws IOException {
    Person person=new Person();
    person.setId("2");
    person.setName("李四");
    person.setAge(20);
    person.setAddress("北京三环");
    String data = JSON.toJSONString(person);
    IndexRequest request=new IndexRequest("itcast").id(person.getId()).source(data,XContentType.JSON);
    IndexResponse response = client.index(request, RequestOptions.DEFAULT);
    System.out.println(response.getId());
}
```

 

### **7.5-修改、查询、删除文档**

1.修改文档：添加文档时，如果id存在则修改，id不存在则添加

```java
    /**
     * 修改文档：添加文档时，如果id存在则修改，id不存在则添加
     */

    @Test
    public void UpdateDoc() throws IOException {
        Person person=new Person();
        person.setId("2");
        person.setName("李四");
        person.setAge(20);
        person.setAddress("北京三环车王");

        String data = JSON.toJSONString(person);

        IndexRequest request=new IndexRequest("itcast").id(person.getId()).source(data,XContentType.JSON);
        IndexResponse response = client.index(request, RequestOptions.DEFAULT);
        System.out.println(response.getId());
    }
```

2.根据id查询文档

```java
    /**
     * 根据id查询文档
     */
    @Test
    public void getDoc() throws IOException {

        //设置查询的索引、文档
        GetRequest indexRequest=new GetRequest("itcast","2");

        GetResponse response = client.get(indexRequest, RequestOptions.DEFAULT);
        System.out.println(response.getSourceAsString());
    }
```

3.根据id删除文档

```java
/**
     * 根据id删除文档
     */
    @Test
    public void delDoc() throws IOException {

        //设置要删除的索引、文档
        DeleteRequest deleteRequest=new DeleteRequest("itcast","1");

        DeleteResponse response = client.delete(deleteRequest, RequestOptions.DEFAULT);
        System.out.println(response.getId());
    }
```





## **01-今日内容**

1.  ElasticSearch 高级操作

2.  ElasticSearch 集群管理

## **02-ElasticSearch高级操作**（重点）

- 批量操作
- 导入数据
- <font color="red">各种查询</font>
- 索引别名和重建索引



### 2.1-bulk批量操作-脚本

 脚本：

![image-20210311083545292](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210311083545292.png)

测试用的5号文档

```
POST /person1/_doc/5
{
  "name":"张三5号",
  "age":18,
  "address":"北京海淀区"
}
```

批量操作文本

```json
#批量操作
#1.删除5号
#新增8号
#更新2号 name为2号
POST _bulk
{"delete":{"_index":"person1","_id":"5"}}
{"create":{"_index":"person1","_id":"8"}}
{"name":"八号","age":18,"address":"北京"}
{"update":{"_index":"person1","_id":"2"}}
{"doc":{"name":"2号"}}
```

结果

```json
{
  "took" : 51,
  "errors" : true,
  "items" : [
    {
      "delete" : {
        "_index" : "person1",
        "_type" : "_doc",
        "_id" : "5",
        "_version" : 2,
        "result" : "deleted",
        "_shards" : {
          "total" : 2,
          "successful" : 1,
          "failed" : 0
        },
        "_seq_no" : 6,
        "_primary_term" : 2,
        "status" : 200
      }
    },
    {
      "create" : {
        "_index" : "person1",
        "_type" : "_doc",
        "_id" : "8",
        "_version" : 1,
        "result" : "created",
        "_shards" : {
          "total" : 2,
          "successful" : 1,
          "failed" : 0
        },
        "_seq_no" : 7,
        "_primary_term" : 2,
        "status" : 201
      }
    },
    {
      "update" : {
        "_index" : "person1",
        "_type" : "_doc",
        "_id" : "2",
        "_version" : 2,
        "result" : "updated",
        "_shards" : {
          "total" : 2,
          "successful" : 1,
          "failed" : 0
        },
        "_seq_no" : 10,
        "_primary_term" : 2,
        "status" : 200
      }
    }
  ]
}

```






### **2.2-bulk批量操作-JavaAPI**



```java
 /**
     *  Bulk 批量操作
     */
    @Test
    public void test2() throws IOException {

        //创建bulkrequest对象，整合所有操作
        BulkRequest bulkRequest =new BulkRequest();

           /*
        # 1. 删除5号记录
        # 2. 添加6号记录
        # 3. 修改3号记录 名称为 “三号”
         */
        //添加对应操作
        //1. 删除5号记录
        DeleteRequest deleteRequest=new DeleteRequest("person1","5");
        bulkRequest.add(deleteRequest);

        //2. 添加6号记录
        Map<String, Object> map=new HashMap<>();
        map.put("name","六号");
        IndexRequest indexRequest=new IndexRequest("person1").id("6").source(map);
        bulkRequest.add(indexRequest);
        //3. 修改3号记录 名称为 “三号”
        Map<String, Object> mapUpdate=new HashMap<>();
        mapUpdate.put("name","三号");
        UpdateRequest updateRequest=new UpdateRequest("person1","3").doc(mapUpdate);

        bulkRequest.add(updateRequest);
        //执行批量操作


        BulkResponse response = client.bulk(bulkRequest, RequestOptions.DEFAULT);
        System.out.println(response.status());

    }
```






### **2.3-导入数据-分析&创建索引**

 ![image-20210311090551635](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210311090551635.png)

```json
PUT goods
{
	"mappings": {
		"properties": {
			"title": {
				"type": "text",
				"analyzer": "ik_smart"
			},
			"price": { 
				"type": "double"
			},
			"createTime": {
				"type": "date"
			},
			"categoryName": {	
				"type": "keyword"
			},
			"brandName": {	
				"type": "keyword"
			},
	
			"spec": {		
				"type": "object"
			},
			"saleNum": {	
				"type": "integer"
			},
			
			"stock": {	
				"type": "integer"
			}
		}
	}
}
```






### **2.4-导入数据-代码实现**

 <font color= "red">注意JSON对象和字符串</font>

```java
String字符串:
var str1 = '{ "name": "cxh", "sex": "man" }'; 
JSON对象:
var str2 = { "name": "cxh", "sex": "man" };
```





```java
 /**
     * 从Mysql 批量导入 elasticSearch
     */
    @Test
    public void test3() throws IOException {
        //1.查询所有数据，mysql
        List<Goods> goodsList = goodsMapper.findAll();

        //2.bulk导入
        BulkRequest bulkRequest=new BulkRequest();

        //2.1 循环goodsList，创建IndexRequest添加数据
        for (Goods goods : goodsList) {

            //2.2 设置spec规格信息 Map的数据   specStr:{}
            String specStr = goods.getSpecStr();

            //将json格式字符串转为Map集合 ！！！！！
            Map map = JSON.parseObject(specStr, Map.class);

            //设置spec map
            goods.setSpec(map);

            //将goods对象转换为json字符串
            String data = JSON.toJSONString(goods);

            IndexRequest indexRequest=new IndexRequest("goods").source(data,XContentType.JSON);
            bulkRequest.add(indexRequest);

        }


        BulkResponse response = client.bulk(bulkRequest, RequestOptions.DEFAULT);
        System.out.println(response.status());

    }
```



可能超时

```yml
# actuator 还有中说法是es的健康监测机制时间太短，所以加长它的时间
management:
  endpoints:
    web:
      exposure:
        include: ['*']
  health:
    elasticsearch:
      response-timeout: 3s
      
      
# 关闭健康监测，不建议
management:
      health:
        elasticsearch:
          enabled: false
```






### **2.5-导入数据-代码实现-详解（选放）**

 转换成JSON的原因：

```JSON
#spec配置的数据类型是JSON对象，所以当存放字符串的时候报错
			"spec": {		
				"type": "object"
			},
```



错误信息

![1581164001550](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581164001550.png)




## **3-ElasticSearch查询**(重点!!!)

###  3.1-matchAll-脚本

![image-20210311103548812](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210311103548812.png)



```json
# 默认情况下，es一次展示10条数据,通过from和size来控制分页
# 查询结果详解

GET goods/_search
{
  "query": {
    "match_all": {}
  },
  "from": 0,
  "size": 100
}

GET goods
```




### **3.2-matchAll-JavaAPI**

 

```java
/**
     * 查询所有
     *  1. matchAll
     *  2. 将查询结果封装为Goods对象，装载到List中
     *  3. 分页。默认显示10条
     */
    @Test
    public void matchAll() throws IOException {

        //2. 构建查询请求对象，指定查询的索引名称
        SearchRequest searchRequest=new SearchRequest("goods");

        //4. 创建查询条件构建器SearchSourceBuilder
        SearchSourceBuilder sourceBuilder=new SearchSourceBuilder();

        //6. 查询条件
        QueryBuilder queryBuilder= QueryBuilders.matchAllQuery();
        //5. 指定查询条件
        sourceBuilder.query(queryBuilder);

        //3. 添加查询条件构建器 SearchSourceBuilder
        searchRequest.source(sourceBuilder);
        // 8 . 添加分页信息  不设置 默认10条
//        sourceBuilder.from(0);
//        sourceBuilder.size(100);
        //1. 查询,获取查询结果

        SearchResponse searchResponse = client.search(searchRequest, RequestOptions.DEFAULT);

        //7. 获取命中对象 SearchHits
        SearchHits hits = searchResponse.getHits();

        //7.1 获取总记录数
      Long total= hits.getTotalHits().value;
        System.out.println("总数："+total);
        //7.2 获取Hits数据  数组
        SearchHit[] hits1 = hits.getHits();
            //获取json字符串格式的数据
        List<Goods> goodsList = new ArrayList<>();
        for (SearchHit searchHit : hits1) {
            String sourceAsString = searchHit.getSourceAsString();
            //转为java对象
            Goods goods = JSON.parseObject(sourceAsString, Goods.class);
            goodsList.add(goods);
        }

        for (Goods goods : goodsList) {
            System.out.println(goods);
        }

    }
```



设置条件的疑问点

![1580909328868](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1580909328868.png)







### **3.3-termQuery**

<font color = "red">一般查keyword类型</font> 

![image-20210311105632076](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210311105632076.png)

term查询和字段类型有关系，首先回顾一下ElasticSearch两个数据类型

 ElasticSearch两个数据类型

```
text：会分词，不支持聚合

keyword：不会分词，将全部内容作为一个词条，支持聚合
```

term查询：不会对查询条件进行分词。

```
GET goods/_search
{
  "query": {
    "term": {
      "title": {
        "value": "华为"
      }
    }
  }
}
```

term查询，查询text类型字段时，只有其中的单词相匹配都会查到，text字段会对数据进行分词

例如：查询title 为“华为”的，title type 为text



![1580910336989](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1580910336989.png)





![1580910384673](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1580910384673.png)





查询categoryName 字段时，categoryName字段为keyword  ,keyword：不会分词，将全部内容作为一个词条,

即完全匹配，才能查询出结果

![1580910596746](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1580910596746.png)





```json
GET goods/_search
{
  "query": {
    "term": {
      "categoryName": {
        "value": "华为手机"
      }
    }
  }
}
```



![1580910648421](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1580910648421.png)






### **3.4-matchQuery**

 ![image-20210311112217726](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210311112217726.png)

match查询：

•会对查询条件进行分词。

•然后将分词后的查询条件和词条进行等值匹配

•默认取并集（OR）



```
# match查询
GET goods/_search
{
  "query": {
    "match": {
      "title": "华为手机"
    }
  },
  "size": 500
}
```



match 的默认搜索（or 并集）

例如：华为手机，会分词为 “华为”，“手机” 只要出现其中一个词条都会搜索到

match的 and（交集） 搜索

例如：例如：华为手机，会分词为 “华为”，“手机”  但要求“华为”，和“手机”同时出现在词条中



**总结：**

- term query会去倒排索引中寻找确切的term，它并不知道分词器的存在。这种查询适合**keyword** 、**numeric**、**date**
- match query知道分词器的存在。并且理解是如何被分词的



### **3.5-模糊查询-脚本**



"华？"

<font color= "red">注意：通配符一定不能写在前面，会全表扫描，性能很低，甚至失效</font>

#### 3.5.1-wildcard查询

wildcard查询：会对查询条件进行分词。还可以使用通配符 ?（任意单个字符） 和  * （0个或多个字符）

```
"*华*"  包含华字的
"华*"   华字后边多个字符
"华?"  华字后边多个字符
"*华"或"?华" 会引发全表（全索引）扫描 注意效率问题
```



```json
# wildcard 查询。查询条件分词，模糊查询
GET goods/_search
{
  "query": {
    "wildcard": {
      "title": {
        "value": "华*"
      }
    }
  }
}
```

#### 3.5.2正则查询(用的不多)

```
\W：匹配包括下划线的任何单词字符，等价于 [A-Z a-z 0-9_]   开头的反斜杠是转义符

+号多次出现

(.)*为任意字符
正则查询取决于正则表达式的效率
```

```json
GET goods/_search
{
  "query": {
    "regexp": {
      "title": "\\w+(.)*"
    }
  }
}

```

#### 3.5.3前缀查询

 对keyword类型支持比较好

```json
# 前缀查询 对keyword类型支持比较好
GET goods/_search
{
  "query": {
    "prefix": {
      "brandName": {
        "value": "三"
      }
    }
  }
}
```




### **3.6-模糊查询-JavaAPI**

 

```java
//模糊查询
WildcardQueryBuilder query = QueryBuilders.wildcardQuery("title", "华*");//华后多个字符
//正则查询
 RegexpQueryBuilder query = QueryBuilders.regexpQuery("title", "\\w+(.)*");
 //前缀查询
 PrefixQueryBuilder query = QueryBuilders.prefixQuery("brandName", "三");
```






### **3.7-范围&排序查询**

 

```json
# 范围查询

GET goods/_search
{
  "query": {
    "range": {
      "price": {
        "gte": 2000,
        "lte": 3000
      }
    }
  },
  "sort": [
    {
      "price": {
        "order": "desc"
      }
    }
  ]
}
```



```java
 //范围查询 以price 价格为条件
RangeQueryBuilder query = QueryBuilders.rangeQuery("price");

//指定下限
query.gte(2000);
//指定上限
query.lte(3000);

sourceBuilder.query(query);

//排序  价格 降序排列
sourceBuilder.sort("price",SortOrder.DESC);
```








### **3.8-queryString查询**

 queryString **多条件**查询

•会对查询条件进行分词。

•然后将分词后的查询条件和词条进行等值匹配

•默认取并集（OR）

•可以指定多个查询字段

query_string：识别query中的连接符（or 、and）

```
# queryString

GET goods/_search
{
  "query": {
    "query_string": {
      "fields": ["title","categoryName","brandName"], 
      "query": "华为 AND 手机"
    }
  }
}
```



simple_query_string：不识别query中的连接符（**or 、and**），查询时会将 “华为”、"and"、“手机”分别进行查询

```
GET goods/_search
{
  "query": {
    "simple_query_string": {
      "fields": ["title","categoryName","brandName"], 
      "query": "华为 AND 手机"
    }
  }
}
```



query_string：有default_operator连接符的脚本

```json
GET goods/_search
{
  "query": {
    "query_string": {
      "fields": ["title","brandName","categoryName"],
      "query": "华为手机 "
      , "default_operator": "AND"
    }
  }
}

```

**java代码**

```java
QueryStringQueryBuilder query = QueryBuilders.queryStringQuery("华为手机").field("title").field("categoryName")
.field("brandName").defaultOperator(Operator.AND);
```



simple_query_string：有default_operator连接符的脚本

```json
GET goods/_search
{
  "query": {
    "simple_query_string": {
      "fields": ["title","brandName","categoryName"],
      "query": "华为手机 "
      , "default_operator": "OR"
    }
  }
}
```



注意：query中的or   and 是查询时 匹配条件是否同时出现----or 出现一个即可，and 两个条件同时出现

default_operator的or   and 是对结果进行 并集（or）、交集（and）



### **3.9-布尔查询-脚本**(重要)

![image-20210311122046595](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210311122046595.png)



 boolQuery：对多个查询条件连接。连接方式：

•must（and）：条件必须成立

•must_not（not）：条件必须不成立

•should（or）：条件可以成立

•filter：条件必须成立，性能比must高。不会计算得分

**得分:**即条件匹配度,匹配度越高，得分越高



```json 
# boolquery
#must和filter配合使用时，max_score（得分）是显示的
#must 默认数组形式
GET goods/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "term": {
            "brandName": {
              "value": "华为"
            }
          }
        }
      ],
      "filter":[ 
        {
        "term": {
          "title": "手机"
        }
       },
       {
         "range":{
          "price": {
            "gte": 2000,
            "lte": 3000
         }
         }
       }
      
      ]
    }
  }
}
#filter 单独使用   filter可以是单个条件，也可多个条件（数组形式）
GET goods/_search
{
  "query": {
    "bool": {
      "filter": [
        {
          "term": {
            "brandName": {
              "value": "华为"
            }
          }
        }
      ]
    }
  }
}
```




### **3.10-布尔查询-JavaAPI**

布尔查询：boolQuery 

1. 查询品牌名称为:华为 
2. 查询标题包含：手机
3. 查询价格在：2000-3000 

must 、filter为连接方式

term、match为不同的查询方式

```java
       //1.构建boolQuery
        BoolQueryBuilder boolQuery = QueryBuilders.boolQuery();
        //2.构建各个查询条件
        //2.1 查询品牌名称为:华为
        TermQueryBuilder termQueryBuilder = QueryBuilders.termQuery("brandName", "华为");
        boolQuery.must(termQueryBuilder);
        //2.2. 查询标题包含：手机
        MatchQueryBuilder matchQuery = QueryBuilders.matchQuery("title", "手机");
        boolQuery.filter(matchQuery);

        //2.3 查询价格在：2000-3000
        RangeQueryBuilder rangeQuery = QueryBuilders.rangeQuery("price");
        rangeQuery.gte(2000);
        rangeQuery.lte(3000);
        boolQuery.filter(rangeQuery);

        sourceBuilder.query(boolQuery);
```








### **3.11-聚合查询-脚本**

 

•指标聚合：相当于MySQL的聚合函数。max、min、avg、sum等

•桶聚合：相当于MySQL的 group by 操作。不要对text类型的数据进行分组，会失败。



```json
# 聚合查询

# 指标聚合 聚合函数

GET goods/_search
{
  "query": {
    "match": {
      "title": "手机"
    }
  },
  "aggs": {
    "max_price": {
      "max": {
        "field": "price"
      }
    }
  }
}

# 桶聚合  分组

GET goods/_search
{
  "query": {
    "match": {
      "title": "手机"
    }
  },
  "aggs": {
    "goods_brands": {
      "terms": {
        "field": "brandName",
        "size": 100
      }
    }
  }
}
```




### **3.12-聚合查询-JavaAPI**

 

聚合查询：桶聚合，分组查询

1. 查询title包含手机的数据
2. 查询品牌列表

```java 
/**
     * 聚合查询：桶聚合，分组查询
     * 1. 查询title包含手机的数据
     * 2. 查询品牌列表
     */
@Test
public void testAggQuery() throws IOException {

    SearchRequest searchRequest=new SearchRequest("goods");

    SearchSourceBuilder sourceBuilder=new SearchSourceBuilder();
    //1. 查询title包含手机的数据

    MatchQueryBuilder queryBuilder = QueryBuilders.matchQuery("title", "手机");

    sourceBuilder.query(queryBuilder);
    //2. 查询品牌列表  只展示前100条
    AggregationBuilder aggregation=AggregationBuilders.terms("goods_brands").field("brandName").size(100);
    sourceBuilder.aggregation(aggregation);


    searchRequest.source(sourceBuilder);

    SearchResponse searchResponse = client.search(searchRequest, RequestOptions.DEFAULT);

    //7. 获取命中对象 SearchHits
    SearchHits hits = searchResponse.getHits();

    //7.1 获取总记录数
    Long total= hits.getTotalHits().value;
    System.out.println("总数："+total);

    // aggregations 对象
    Aggregations aggregations = searchResponse.getAggregations();
    //将aggregations 转化为map
    Map<String, Aggregation> aggregationMap = aggregations.asMap();


    //通过key获取goods_brands 对象 使用Aggregation的子类接收  buckets属性在Terms接口中体现

    //        Aggregation goods_brands1 = aggregationMap.get("goods_brands");
    Terms goods_brands =(Terms) aggregationMap.get("goods_brands");

    //获取buckets 数组集合
    List<? extends Terms.Bucket> buckets = goods_brands.getBuckets();

    Map<String,Object>map=new HashMap<>();
    //遍历buckets   key 属性名，doc_count 统计聚合数
    for (Terms.Bucket bucket : buckets) {

        System.out.println(bucket.getKey());
        map.put(bucket.getKeyAsString(),bucket.getDocCount());
    }

    System.out.println(map);

}
```






### **3.13-高亮查询-脚本**

 

高亮三要素：

•高亮字段

•前缀

•后缀

默认前后缀 ：em

```html
<em>手机</em>
```



```json
GET goods/_search
{
  "query": {
    "match": {
      "title": "电视"
    }
  },
  "highlight": {
    "fields": {
      "title": {
        "pre_tags": "<font color='red'>",
        "post_tags": "</font>"
      }
    }
  }
}
```






### **3.14-高亮查询-JavaAPI**

  实施步骤：
      高亮查询：
       1. 设置高亮
                  		高亮字段
                		 前缀
                    	   后缀
            2. 将高亮了的字段数据，替换原有数据

```java
/**
     *
     * 高亮查询：
     *  1. 设置高亮
     *      * 高亮字段
     *      * 前缀
     *      * 后缀
     *  2. 将高亮了的字段数据，替换原有数据
     */
@Test
public void testHighLightQuery() throws IOException {


    SearchRequest searchRequest = new SearchRequest("goods");

    SearchSourceBuilder sourceBulider = new SearchSourceBuilder();

    // 1. 查询title包含手机的数据
    MatchQueryBuilder query = QueryBuilders.matchQuery("title", "手机");

    sourceBulider.query(query);

    //设置高亮
    HighlightBuilder highlighter = new HighlightBuilder();
    //设置三要素
    highlighter.field("title");
    //设置前后缀标签
    highlighter.preTags("<font color='red'>");
    highlighter.postTags("</font>");

    //加载已经设置好的高亮配置
    sourceBulider.highlighter(highlighter);

    searchRequest.source(sourceBulider);

    SearchResponse searchResponse = client.search(searchRequest, RequestOptions.DEFAULT);


    SearchHits searchHits = searchResponse.getHits();
    //获取记录数
    long value = searchHits.getTotalHits().value;
    System.out.println("总记录数："+value);

    List<Goods> goodsList = new ArrayList<>();
    SearchHit[] hits = searchHits.getHits();
    for (SearchHit hit : hits) {
        String sourceAsString = hit.getSourceAsString();

        //转为java
        Goods goods = JSON.parseObject(sourceAsString, Goods.class);

        // 获取高亮结果，替换goods中的title
        Map<String, HighlightField> highlightFields = hit.getHighlightFields();
        HighlightField HighlightField = highlightFields.get("title");
        Text[] fragments = HighlightField.fragments();
        //highlight title替换 替换goods中的title
        goods.setTitle(fragments[0].toString());
        goodsList.add(goods);
    }

    for (Goods goods : goodsList) {
        System.out.println(goods);
    }


}
```




### **3.15-重建索引&索引别名**

 

![image-20210311152239228](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210311152239228.png)





```json
#查询别名 默认别名无法查看，默认别名同索引名
GET goods/_alias/
#结果
{
  "goods" : {
    "aliases" : { }
  }
}

```



1.新建student_index_v1索引

```json
# -------重建索引-----------

# 新建student_index_v1。索引名称必须全部小写

PUT student_index_v1
{
  "mappings": {
    "properties": {
      "birthday":{
        "type": "date"
      }
    }
  }
}
#查看 student_index_v1 结构
GET student_index_v1
#添加数据
PUT student_index_v1/_doc/1
{
  "birthday":"1999-11-11"
}
#查看数据
GET student_index_v1/_search

#添加数据
PUT student_index_v1/_doc/1
{
  "birthday":"1999年11月11日"
}
```

2.重建索引:将student_index_v1 数据拷贝到 student_index_v2

```json
# 业务变更了，需要改变birthday字段的类型为text

# 1. 创建新的索引 student_index_v2
# 2. 将student_index_v1 数据拷贝到 student_index_v2

# 创建新的索引 student_index_v2
PUT student_index_v2
{
  "mappings": {
    "properties": {
      "birthday":{
        "type": "text"
      }
    }
  }
}
# 将student_index_v1 数据拷贝到 student_index_v2
# _reindex 拷贝数据
POST _reindex
{
  "source": {
    "index": "student_index_v1"
  },
  "dest": {
    "index": "student_index_v2"
  }
}

GET student_index_v2/_search



PUT student_index_v2/_doc/2
{
  "birthday":"1999年11月11日"
}

```

3.创建索引库别名：

注意：DELETE student_index_v1 这一操作将删除student_index_v1索引库，并不是删除别名

```json
# 思考： 现在java代码中操作es，还是使用的实student_index_v1老的索引名称。
# 1. 改代码（不推荐）
# 2. 索引别名（推荐）

# 步骤：
# 0. 先删除student_index_v1
# 1. 给student_index_v2起个别名 student_index_v1



# 先删除student_index_v1
#DELETE student_index_v1 这一操作将删除student_index_v1索引库
#索引库默认的别名与索引库同名，无法删除

# 给student_index_v1起个别名 student_index_v11
POST student_index_v2/_alias/student_index_v11
#测试删除命令
POST /_aliases
{
    "actions": [
        {"remove": {"index": "student_index_v1", "alias": "student_index_v11"}}
    ]
}

# 删除v1索引
DELETE student_index_v1
# 给student_index_v2起个别名 student_index_v1
POST student_index_v2/_alias/student_index_v1

#查询别名
GET goods/_alias/


GET student_index_v1/_search
GET student_index_v2/_search

```




## **4-ElasticSearch 集群**

### 4.1-集群介绍

- 集群和分布式：

​			集群：多个人做一样的事。

​			分布式：多个人做不一样的事

- 集群解决的问题：

​			让系统高可用

​			分担请求压力

- 分布式解决的问题：

​		分担存储和计算的压力，提速

​		解耦

- **集群和分布式架构往往是并存的**

![1581042245219](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581042245219.png)




### **4.2-ES集群相关概念**

 **es 集群:**

•ElasticSearch 天然支持分布式

•ElasticSearch 的设计隐藏了分布式本身的复杂性

**ES集群相关概念**:

•集群（cluster）：一组拥有共同的 cluster name 的 节点。

•节点（node)  ：集群中的一个 Elasticearch 实例

•索引（index) ：es存储数据的地方。相当于关系数据库中的database概念

•<font color="red">分片（shard）</font>：索引可以被拆分为不同的部分进行存储，称为分片。在集群环境下，一个索引的不同分片可以拆分到不同的节点中

•主分片（Primary shard）：相对于副本分片的定义。

•副本分片（Replica shard）每个主分片可以有一个或者多个副本，数据和主分片一样。



![image-20210311161625804](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210311161625804.png)












### **4.3-集群搭建**

 	参见ElasticSearch 集群-集群搭建.md




### **4.4-kibina管理集群**

 

```shell
vim  kibana-7.4.0-linux-x86_64-cluster/config/kibana.yml
```

kibana.yml

```yaml
#支持中文
i18n.locale: "zh-CN"
#5602避免与之前的冲突
server.port: 5602
server.host: "0.0.0.0"
server.name: "kibana-itcast-cluster"
elasticsearch.hosts: ["http://localhost:9201","http://localhost:9202","http://localhost:9203"]
elasticsearch.requestTimeout: 99999

```






### **4.5-JavaAPI 访问集群**

 

```json
PUT cluster_test
{
  "mappings": {
    "properties": {
      "name":{
        "type": "text"
      }
    }
  }
}

GET cluster_test
GET cluster_test/_search

POST /cluster_test/_doc/1
{
  "name":"张三"
}
```

测试类

```java
 
    @Resource(name="clusterClient")
    RestHighLevelClient clusterClient;
 
 /**
     * 测试集群
     * @throws IOException
     */
    @Test
    public void testCluster() throws IOException {


        //设置查询的索引、文档
        GetRequest indexRequest=new GetRequest("cluster_test","1");

        GetResponse response = clusterClient.get(indexRequest, RequestOptions.DEFAULT);
        System.out.println(response.getSourceAsString());

    }
```



ElasticSearchConfig

```java
private String host1;

private int port1;

private String host2;

private int port2;

private String host3;

private int port3;

//get/set ...

@Bean("clusterClient")
    public RestHighLevelClient clusterClient(){
        return new RestHighLevelClient(RestClient.builder(
                new HttpHost(host1,port1,"http"),
                new HttpHost(host2,port2,"http"),
                new HttpHost(host3,port3,"http")
        ));
    }
```

application.yml

```yml
elasticsearch:
   host: 192.168.140.130
   port: 9200
   host1: 192.168.140.130
   port1: 9201
   host2: 192.168.140.130
   port2: 9202
   host3: 192.168.140.130
   port3: 9203
```




### **4.6-分片配置**

 •在创建索引时，如果不指定分片配置，则默认主分片1，副本分片1。

•在创建索引时，可以通过settings设置分片

![1581043174004](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581043174004.png)





![1581043214369](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581043214369.png)



![1581043148796](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581043148796.png)

**分片配置**

```json
#分片配置
#"number_of_shards": 3, 主分片数量
#"number_of_replicas": 1  主分片备份数量，每一个主分片有一个备份
# 3个主分片+3个副分片=6个分片
PUT cluster_test1
{
  "settings": {
    "number_of_shards": 3,
    "number_of_replicas": 1
  }, 
  "mappings": {
    "properties": {
      "name":{
        "type": "text"
      }
    }
  }
}
```



1.三个节点正常运行（0、1、2分片标号）

![1581044158693](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581044158693.png)

2.itcast-3 挂掉

![1581044220349](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581044220349.png)



3.将挂掉节点的分片，自平衡到其他节点

![1581044251012](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581044251012.png)

4.itcast-3 恢复正常后，节点分片将自平衡回去（并不一定是原来的分片）

![1581044368389](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581044368389.png)



**分片与自平衡**

•当节点挂掉后，挂掉的节点分片会自平衡到其他节点中

注意：分片数量一旦确定好，不能修改。

<font color='red'>**索引分片推荐配置方案：**</font>

1.每个分片推荐大小10-30GB

2.分片数量推荐 = 节点数量 * 1~3倍



**思考：比如有1000GB数据，应该有多少个分片？多少个节点**

1.每个分片25GB   则可以分为40个分片

2.分片数量推荐 = 节点数量 * 1~3倍 -->  40/2=20   即20个节点




### **4.7-路由原理**

 **路由原理**

•文档存入对应的分片，ES计算分片编号的过程，称为路由。

•Elasticsearch 是怎么知道一个文档应该存放到哪个分片中呢？

•查询时，根据文档id查询文档， Elasticsearch 又该去哪个分片中查询数据呢？

•路由算法 ：shard_index = hash(id) % number_of_primary_shards



![1581044026981](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581044026981.png)



查询id为5的文档：假如hash(5)=17  ，根据算法17%3=2




### **4.8-脑裂**

 **ElasticSearch 集群正常状态：**

• 一个正常es集群中只有一个**主节点**（Master），主节点负责管理整个集群。如创建或删除索引，跟踪哪些节点是群集的一部分，并决定哪些分片分配给相关的节点。

•集群的所有节点都会选择同一个节点作为主节点。



**脑裂现象：**

•脑裂问题的出现就是因为从节点在选择主节点上出现分歧导致一个集群出现多个主节点从而使集群分裂，使得集群处于异常状态。



![1581042550583](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581042550583.png)

**脑裂产生的原因：**

1.网络原因：网络延迟

​	•一般es集群会在内网部署，也可能在外网部署，比如阿里云。

​	•内网一般不会出现此问题，外网的网络出现问题的可能性大些。

2.节点负载

​	•主节点的角色既为master又为data。数据访问量较大时，可能会导致Master节点停止响应（假死状态）。

​	![1581042578379](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\1581042578379.png)

3. JVM内存回收

   •当Master节点设置的JVM内存较小时，引发JVM的大规模内存回收，造成ES进程失去响应。



**避免脑裂**：

1.网络原因：discovery.zen.ping.timeout 超时时间配置大一点。默认是3S

2.节点负载：角色分离策略

​	•候选主节点配置为

​		•node.master: true

​		•node.data: false

​	•数据节点配置为

​		•node.master: false

​		•node.data: true

3.JVM内存回收：修改 config/jvm.options 文件的 -Xms 和 -Xmx 为服务器的内存一半。






### **30-ElasticSearch 集群-集群扩容**

 

 按照集群搭建步骤再复制Es节点进行配置，参见ElasticSearch 集群-集群搭建.md