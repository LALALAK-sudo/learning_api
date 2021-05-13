# lua

## 1.1 lua是什么

Lua 是一个小巧的脚本语言。它是巴西里约热内卢天主教大学（Pontifical Catholic University of Rio de Janeiro）里的一个由Roberto Ierusalimschy、Waldemar Celes 和 Luiz Henrique de Figueiredo三人所组成的研究小组于1993年开发的。 其设计目的是为 了通过灵活嵌入应用程序中从而为应用程序提供灵活的扩展和定制功能。Lua由标准C编 写而成，几乎在所有操作系统和平台上都可以编译，运行。Lua并没有提供强大的库，这 是由它的定位决定的。所以Lua不适合作为开发独立应用程序的语言。Lua 有一个同时进 行的JIT项目，提供在特定平台上的即时编译功能。 

简单来说：

Lua 是一种轻量小巧的脚本语言，用标准C语言编写并以源代码形式开放， 其设计目 的是为了嵌入应用程序中，从而为应用程序提供灵活的扩展和定制功能。

**lua 语言具有以下特性**

- 支持面向过程(procedure-oriented)编程和函数式编程(functional programming)；
-  自动内存管理；只提供了一种通用类型的表（table），用它可以实现数组，哈希表，集合，对象； 
- 语言内置模式匹配；闭包(closure)；函数也可以看做一个值；提供多线程（协同进程，并非操作系统所支持的线程）支持； 
- 通过闭包和table可以很方便地支持面向对象编程所需要的一些关键机制，比如数据 抽象，虚函数，继承和重载等。

**应用场景**

- 游戏开发 
- 独立应用脚本 
- Web 应用脚本 
- 扩展和数据库插件如：MySQL Proxy 和 MySQL WorkBench 
- 安全系统，如入侵检测系统 
- redis中嵌套调用实现类似事务的功能 
- web容器中应用处理一些过滤 缓存等等的逻辑，例如nginx。



## 1.2 lua的安装

有linux版本的安装也有mac版本的安装。。我们采用linux版本的安装，首先我们准备一 个linux虚拟机。 

安装步骤,在linux系统中执行下面的命令。

```linux
yum install ‐y gcc
yum install libtermcap‐devel ncurses‐devel libevent‐devel readline‐devel
curl ‐R ‐O http://www.lua.org/ftp/lua‐5.3.5.tar.gz
tar ‐zxf lua‐5.3.5.tar.gz
cd lua‐5.3.5
make linux test
make install

```



## 1.3 快速入门

创建hello.lua文件，内容为

```lua
print("hello");
```

保存。执行命令

```lua
lua helloworld.lua
```

输出为：

```lua
Hello
```



## 1.4 LUA的基本语法

- lua有交互式编程和脚本式编程。 
- 交互式编程就是直接输入语法，就能执行。 
- 脚本式编程需要编写脚本文件，然后再执行。 

一般采用脚本式编程。（例如：编写一个hello.lua的文件，输入文件内容，并执行lua hell.lua即可）



### 1.4.1 注释

单行注释：两个减号是单行注释

```
--
```

多行注释：

```lua
‐‐[[
    多行注释
    多行注释
‐‐]]
```





### 1.4.2 关键字 

关键字就好比java中的 break if else等等一样的效果。lua的关键字如下：

![image-20210330162135219](D:\h后端\imgs\image-20210330162135219.png)



### 1.4.3 定义变量 

全局变量，默认的情况下，定义一个变量都是全局变量， 

如果要用局部变量 需要声明为local.例如：

```lua
‐‐ 全局变量赋值
a=1
‐‐ 局部变量赋值
local b=2
```

如果变量没有初始化：则 它的值为nil 这和java中的null不同。





### 1.4.4 Lua中的数据类型 

Lua 是动态类型语言，变量不要类型定义,只需要为变量赋值。 值可以存储在变量中，作 为参数传递或结果返回。

 Lua 中有 8 个基本类型分别为：nil、boolean、number、string、userdata、 function、thread 和 table。

![image-20210330162225265](D:\h后端\imgs\image-20210330162225265.png)



### 1.4.5 流程控制 

如下：类似于if else

```lua
‐‐[ 0 为 true ]
if(0) then
	print("0 为 true")
else
	print("0 不为true")
end
```



### 1.4.6 函数 

lua中也可以定义函数，类似于java中的方法。例如：

```lua
‐‐[[ 函数返回两个值的最大值 ‐‐]]
function max(num1, num2)
    if (num1 > num2) then
        result = num1;
    else
        result = num2;
    end
        return result;
    end
‐‐ 调用函数
print("两值比较最大值为 ",max(10,4))
print("两值比较最大值为 ",max(5,6))

```

执行之后的结果：

```
两值比较最大值为 10
两值比较最大值为 6
```



### 1.4.7 require 函数 

require 用于 引入其他的模块，类似于java中的类要引用别的类的效果。 

用法：

```lua
require "<模块名>"
```





# nginx

*Nginx* (engine x) 是一个高性能的[HTTP](https://baike.baidu.com/item/HTTP)和[反向代理](https://baike.baidu.com/item/反向代理/7793488)web服务器，同时也提供了IMAP/POP3/SMTP[服务](https://baike.baidu.com/item/服务/100571)。Nginx是由伊戈尔·赛索耶夫为[俄罗斯](https://baike.baidu.com/item/俄罗斯/125568)访问量第二的Rambler.ru站点（俄文：Рамблер）开发的，第一个公开版本0.1.0发布于2004年10月4日。

其将[源代码](https://baike.baidu.com/item/源代码/3814213)以类[BSD许可证](https://baike.baidu.com/item/BSD许可证/10642412)的形式发布，因它的稳定性、丰富的功能集、示例配置文件和低系统资源的消耗而[闻名](https://baike.baidu.com/item/闻名/2303308)。2011年6月1日，nginx 1.0.4发布。

Nginx是一款[轻量级](https://baike.baidu.com/item/轻量级/10002835)的[Web](https://baike.baidu.com/item/Web/150564) 服务器/[反向代理](https://baike.baidu.com/item/反向代理/7793488)服务器及[电子邮件](https://baike.baidu.com/item/电子邮件/111106)（IMAP/POP3）代理服务器，在BSD-like 协议下发行。其特点是占有内存少，[并发](https://baike.baidu.com/item/并发/11024806)能力强，事实上nginx的并发能力在同类型的网页服务器中表现较好，中国大陆使用nginx网站用户有：百度、[京东](https://baike.baidu.com/item/京东/210931)、[新浪](https://baike.baidu.com/item/新浪/125692)、[网易](https://baike.baidu.com/item/网易/185754)、[腾讯](https://baike.baidu.com/item/腾讯/112204)、[淘宝](https://baike.baidu.com/item/淘宝/145661)等。





