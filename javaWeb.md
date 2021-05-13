



![image-20201225160604164](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201225160604164.png)



![image-20210126173015727](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210126173015727.png)





# HTML

	1. web概念概述
	2. HTML



## web概念概述



JavaWeb：使用Java语言开发基于互联网的项目



### 软件架构：

### 1 C/S:

Client/Server 客户端/服务器端

* 在用户本地有一个客户端程序，在远程有一个服务器端程序
* 如：QQ，迅雷...
* 优点：
	1. 用户体验好
* 缺点：
	1. 开发、安装，部署，维护 麻烦



### 2 B/S:

 Browser/Server 浏览器/服务器端

* 只需要一个浏览器，用户通过不同的网址(URL)，客户访问不同的服务器端程序
* 优点：
	1. 开发、安装，部署，维护 简单
* 缺点：
	1. 如果应用过大，用户的体验可能会受到影响
	2. 对硬件要求过高



### B/S架构详解

资源分类：

![image-20201118151359125](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201118151359125.png)



1. 静态资源：
	* 使用静态网页开发技术发布的资源。
	* 特点：
		* 所有用户访问，得到的结果是一样的。
		* 如：文本，图片，音频、视频, HTML,CSS,JavaScript
		* 如果用户请求的是静态资源，那么服务器会直接将静态资源发送给浏览器。浏览器中内置了静态资源的解析引擎，可以展示静态资源
2. 动态资源：
	* 使用动态网页及时发布的资源。
	* 特点：
		* 所有用户访问，得到的结果可能不一样。
		* 如：jsp/servlet,php,asp...
		* 如果用户请求的是动态资源，那么服务器会执行动态资源，转换为静态资源，再发送给浏览器



我们要学习动态资源，必须先学习静态资源！

* 静态资源：
	* HTML：用于搭建基础网页，展示页面的内容
	* CSS：用于美化页面，布局页面
	* JavaScript：控制页面的元素，让页面有一些动态的效果





## HTML

### 1 概念：

​	是最基础的网页开发语言

* Hyper Text Markup Language 超文本标记语言
	* 超文本:
		
		* 超文本是用超链接的方法，将各种不同空间的文字信息组织在一起的网状文本.
		
		  ![image-20201118152035540](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201118152035540.png)
	* 标记语言:
		* 由标签构成的语言。<标签名称> 如 html，xml
		* 标记语言不是编程语言

 





### 2 快速入门：

* 语法：

  1.html文档后缀名 .html 或者 .htm

  2.标签分为

  ​       (1) 围堵标签：有开始标签和结束标签。如

  ```html
  <html> 
      <head>
          <title>title</title>
      </head>
  </html>
  ```

  ​        (2)自闭和标签：开始标签和结束标签在一起。如 

  ```html
  <br/>
  ```

  3.标签可以嵌套：
  需要正确嵌套，不能你中有我，我中有你

  ```
  错误：<a><b></a></b>
  正确：<a><b></b></a>
  ```

  4.在开始标签中可以定义属性。属性是由键值对构成，值需要用引号(单双都可)引起来

  5.html的标签不区分大小写，但是建议使用小写。





代码：

```html
<html>
	<head>
		<title>title</title>
	</head>
	
	<body>
		<font color = 'red'> HelloWrold</font><br/>
		<font color = 'green'> HelloWrold</font>
	</body>
</html>
```





### 3.标签学习：

#### (1)文件标签：

构成html最基本的标签

- html:html文档的根标签
- head：头标签。用于指定html文档的一些属性。引入外部的资源
- title：标题标签。
- body：体标签

* !DOCTYPE html

  <!DOCTYPE html>：html5中定义该文档是html文档

#### (2)文本标签：

和文本有关的标签

* 注释：<!-- 注释内容 -->

* h1  to  h6
	<h1> to <h6>：标题标签
				* h1~h6:字体大小逐渐递减
	
* p

  <p>：段落标签

* <br>：换行标签

* hr
	<hr>：展示一条水平线
	* 属性：
		* color：颜色
		* width：宽度
		* size：高度
		* align：对其方式
			* center：居中
			* left：左对齐
			* right：右对齐
	
* <b>：字体加粗

* <i>：字体斜体

* <font>:字体标签

* center
	<center>:文本居中
	* 属性：
		* color：颜色
		* size：大小
	* face：字体
	
* 属性定义：
	* color：
		1. 英文单词：red,green,blue
		2. rgb(值1，值2，值3)：值的范围：0~255  如  rgb(0,0,255)
		3. #值1值2值3：值的范围：00~FF之间。如： #FF00FF
	* width：
		1. 数值：width='20' ,数值的单位，默认是 px(像素)
		2. 数值%：占比相对于父元素的比例

![image-20201118200020968](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201118200020968.png)



	3. 标签学习：
		1. 文件标签：构成html最基本的标签
			* html:html文档的根标签
			* head：头标签。用于指定html文档的一些属性。引入外部的资源
			* title：标题标签。
			* body：体标签
			* <!DOCTYPE html>：html5中定义该文档是html文档
		2. 文本标签：和文本有关的标签
			* 注释：<!-- 注释内容 -->
			* <h1> to <h6>：标题标签
				* h1~h6:字体大小逐渐递减
			* <p>：段落标签
			* <br>：换行标签
			* <hr>：展示一条水平线
				* 属性：
					* color：颜色
					* width：宽度
					* size：高度
					* align：对其方式
						* center：居中
						* left：左对齐
						* right：右对齐
			* <b>：字体加粗
			* <i>：字体斜体
			* <font>:字体标签
			* <center>:文本居中
				* 属性：
					* color：颜色
					* size：大小
					* face：字体
	
			* 属性定义：
				* color：
					1. 英文单词：red,green,blue
					2. rgb(值1，值2，值3)：值的范围：0~255  如  rgb(0,0,255)
					3. #值1值2值3：值的范围：00~FF之间。如： #FF00FF
				* width：
					1. 数值：width='20' ,数值的单位，默认是 px(像素)
					2. 数值%：占比相对于父元素的比例


​			





```html
* 案例：公司简介
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>公司简介</title>
</head>
<body>
<h1><b>公司简介</b></h1>
    <hr color="#00FF00">
    <p><font color="red"> "中关村黑马程序员训练营"</font>

    是由<b>传智播客</b>联合中关村软件园、CSDN，并委托传智播客进行教学实施的软件开发高端培训机构，致力于服务各大软件企业，解决当前软件开发技术飞速发展， 而企业招不到优秀人才的困扰。
    </p>
    <p>
        目前，“中关村黑马程序员训练营”已成长为行业“学员质量好、课程内容深、企业满意”的移动开发高端训练基地， 并被评为中关村软件园重点扶持人才企业。
    </p>
    <p>
    黑马程序员的学员多为大学毕业后，有理想、有梦想，想从事IT行业，而没有环境和机遇改变自己命运的年轻人。 黑马程序员的学员筛选制度，远比现在90%以上的企业招聘流程更为严格。任何一名学员想成功入学“黑马程序员”， 必须经历长达2个月的面试流程，这些流程中不仅包括严格的技术测试、自学能力测试，还包括性格测试、压力测试、 品德测试等等测试。毫不夸张地说，黑马程序员训练营所有学员都是精挑细选出来的。百里挑一的残酷筛选制度确 保学员质量，并降低企业的用人风险。
    中关村黑马程序员训练营不仅着重培养学员的基础理论知识，更注重培养项目实施管理能力，并密切关注技术革新， 不断引入先进的技术，研发更新技术课程，确保学员进入企业后不仅能独立从事开发工作，更能给企业带来新的技术体系和理念。
    </p>
    <p>
    一直以来，黑马程序员以技术视角关注IT产业发展，以深度分享推进产业技术成长，致力于弘扬技术创新，倡导分享、 开放和协作，努力打造高质量的IT人才服务平台。
    </p>
    <hr color="#00FF00">
<center>
    <font color="#f5f5dc">江苏传智播客教育科技股份有限公司<br>
        版权所有Copyright 2006-2018, All Rights Reserved 苏ICP备16007882</font>
</center>
</body>
</html>
```





#### (3)图片标签：

自闭和标签

* img：展示图片
			* 属性：
				* src：指定图片的位置

```html
* 代码：
			 <!--展示一张图片 img-->

		    <img src="image/jingxuan_2.jpg" align="right" alt="古镇" width="500" height="500"/>
		
		    <!--
		        相对路径
		            * 以.开头的路径
		                * ./：代表当前目录  ./image/1.jpg（不写默认就是./）
		                * ../:代表上一级目录
		     -->
		
		    <img src="./image/jiangwai_1.jpg">
		
		    <img src="../image/jiangwai_1.jpg">
```



#### (4)列表标签：

* 有序列表：

1. ol:
2. li:

* 无序列表：

1. ul:
2. li:



#### (5)链接标签：

* a:定义一个超链接
   * 属性：

      href：指定访问资源的URL(统一资源定位符)

      target：指定打开资源的方式
      * _self:默认值，在当前页面打开
      * _blank：在空白页面打开



```html
* 代码：
			 <!--超链接  a-->

		    <a href="http://www.itcast.cn">点我</a>
		    <br>
		
		    <a href="http://www.itcast.cn" target="_self">点我</a>
		    <br>
		    <a href="http://www.itcast.cn" target="_blank">点我</a>
		
		    <br>
		
		    <a href="./5_列表标签.html">列表标签</a><br>
		    <a href="mailto:itcast@itcast.cn">联系我们</a>
		
		    <br>
		    <a href="http://www.itcast.cn"><img src="image/jiangwai_1.jpg"></a>
```





#### (6)div和span：

- div:每一个div占满一整行。块级标签
- span：文本信息在一行展示，行内标签 内联标签

（以后和css结合的标签，啥样式都没有，div就是有空行）



#### (7)语义化标签：

html5中为了提高程序的可读性，提供了一些标签。

```html
1. <header>：页眉
2. <footer>：页脚
```



#### (8)表格标签：

​	

![image-20201119103717644](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201119103717644.png)

			* table：定义表格
				* width：宽度
				* border：边框
				* cellpadding：定义内容和单元格的距离
				* cellspacing：定义单元格之间的距离。如果指定为0，则单元格的线会合为一条、
				* bgcolor：背景色
				* align：对齐方式
			* tr：定义行
				* bgcolor：背景色
				* align：对齐方式
			* td：定义单元格
				* colspan：合并列
				* rowspan：合并行
			* th：定义表头单元格
			* <caption>：表格标题
			* <thead>：表示表格的头部分
			* <tbody>：表示表格的体部分
			* <tfoot>：表示表格的脚部分

案例

```html
<table border="1" width="50%" cellpadding="0" cellspacing="0" bgcolor="#faebd7" align="center">
        <tr>
            <th rowspan="2">编号</th>
            <th>姓名</th>
            <th>成绩</th>
        </tr>

        <tr>
            <td>小龙女</td>
            <td>100</td>
        </tr>

        <tr>
            <td>2</td>
            <td colspan="2">杨过</td>
        </tr>

    </table>
```



####  (9)HTML标签：表单标签



##### 表单：

* 概念：用于采集用户输入的数据的。用于和服务器进行交互。

* **form**：用于定义表单的。可以定义一个范围，范围代表采集用户数据的范围

     * 属性：
       * action：指定提交数据的URL
       * method:指定提交方式
         * 分类：一共7种，2种比较常用
           * get：
             1. 请求参数会在地址栏中显示。会封装到请求行中(HTTP协议后讲解)。
             2. 请求参数大小是有限制的。
             3. 不太安全。
           * post：
             2. 请求参数不会再地址栏中显示。会封装在请求体中(HTTP协议后讲解)
             3. 请求参数的大小没有限制。
             4. 较为安全。

  表单项中的数据要想被提交：必须指定其name属性



```html
<form action="#" method="post">
    用户名：<input type="text" name="username"><br>
    密码：<input type="password"><br>
    <input type="submit" value="登录">
</form>
```



##### 表单项标签：



```html
<form action="#" method="post">
    <label for="username">用户名：</label>
    <input type="text" name="username" placeholder="请输入用户名" id="username"><br>
    密码：<input type="password"><br>

    性别: <input type="radio" name="gender" value="male" checked> 男
         <input type="radio" name="gender" value="female"> 女
    <br>

    爱好：<input type="checkbox" name="hobby" value="shopping"> 逛街
    <input type="checkbox" name="hobby" value="java"> java
    <input type="checkbox" name="hobby" value="gama"> 游戏
    <br>
    
    <input type="submit" value="登录">
</form>
```



##### input：

input：可以通过type属性值，改变元素展示的样式

**type属性：**

- text：文本输入框，默认值
- placeholder：指定输入框的提示信息，当输入框的内容发生变化，会自动清空提示信息	
- password：密码输入框
- radio:单选框

注意：

1. 要想让多个单选框实现单选的效果，则多个单选框的name属性值必须一样。
2. 一般会给每一个单选框提供value属性，指定其被选中后提交的值
3. checked属性，可以指定默认值



* checkbox：复选框

注意：

1. 一般会给每一个单选框提供value属性，指定其被选中后提交的值
2. checked属性，可以指定默认值



- file：文件选择框
- hidden：隐藏域，用于提交一些信息。

**按钮：**

- submit：提交按钮。可以提交表单

- button：普通按钮

- image：图片提交按钮

  src属性指定图片的路径	

- label：指定输入项的文字描述信息

注意：

label的for属性一般会和 input 的 id属性值 对应。如果对应了，则点击label区域，会让input输入框获取焦点。





```html
省份 <select name="province" id="">
<option value="1">湖北</option>
<option value="2">河南</option>
</select>
```

##### select: 

select: 下拉列表

子元素：option，指定列表项



##### textarea

textarea：文本域

* cols：指定列数，每一行有多少个字符
* rows：默认多少行。

```html
自我描述
<textarea name="" id="1" cols="30" rows="20"></textarea>
```









## 案例：旅游网站首页tml>

![image-20201119154232677](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201119154232677.png)





```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>黑马旅游网</title>
</head>
<body>

    <!--采用table来完成布局-->
    <!--最外层的table，用于整个页面的布局-->
    <table width="100%" align="center">
       <!-- 第1行 -->
        <tr>
            <td>
                <img src="image/top_banner.jpg" width="100%" alt="">
            </td>
        </tr>

        <!-- 第2行 -->
        <tr>
            <td>
                <table width="100%" align="center">
                    <tr>
                        <td>
                            <img src="image/logo.jpg" alt="">
                        </td>
                        <td>
                            <img src="image/search.png" alt="">
                        </td>
                        <td>
                            <img src="image/hotel_tel.png" alt="">
                        </td>
                    </tr>
                </table>

            </td>
        </tr>

        <!-- 第3行 -->
        <tr>
            <td>
                <table width="100%" align="center">
                    <tr bgcolor="#ffd700" align="center" height="45" >
                        <td>
                            <a href="">首页</a>
                        </td>

                        <td>
                            门票
                        </td>

                        <td>
                            门票
                        </td>

                        <td>
                            门票
                        </td>

                        <td>
                            门票
                        </td>

                        <td>
                            门票
                        </td>

                        <td>
                            门票
                        </td>

                        <td>
                            门票
                        </td>

                        <td>
                            门票
                        </td>

                        <td>
                            门票
                        </td>
                    </tr>
                </table>
            </td>
        </tr>

        <!-- 第4行 轮播图 -->
        <tr>
            <td>
                <img src="image/banner_3.jpg" alt="" width="100%">
            </td>
        </tr>

        <!-- 第5行 黑马精选-->
        <tr>
            <td>
                <img src="image/icon_5.jpg" alt="">
                黑马精选
                <hr  color="#ffd700" >
            </td>
        </tr>

        <!-- 第6行 -->
        <tr>
            <td>
                <table align="center" width="95%">
                    <tr>
                        <td>

                            <img src="image/jiangxuan_1.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 899</font>
                        </td>

                        <td>

                            <img src="image/jiangxuan_1.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 899</font>
                        </td>

                        <td>

                            <img src="image/jiangxuan_1.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 899</font>
                        </td>

                        <td>

                            <img src="image/jiangxuan_1.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 899</font>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>

        <!-- 第7行 国内游 -->
        <tr>
            <td>
                <img src="image/icon_6.jpg" alt="">
                国内游
                <hr  color="#ffd700" >
            </td>
        </tr>

        <!-- 第8行 -->
        <tr>
            <td>
                <table align="center" width="95%">
                    <tr>
                        <td rowspan="2">
                            <img src="image/guonei_1.jpg" alt="">
                        </td>

                        <td>

                            <img src="image/jiangxuan_2.jpg" alt="" height="100%">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>

                        <td>

                            <img src="image/jiangxuan_2.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>

                        <td>

                            <img src="image/jiangxuan_2.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>
                    </tr>

                    <tr>
                        <td>

                            <img src="image/jiangxuan_2.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>

                        <td>

                            <img src="image/jiangxuan_2.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>

                        <td>

                            <img src="image/jiangxuan_2.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>


                    </tr>
                </table>
            </td>
        </tr>

        <!-- 第9行 境外游 -->
        <tr>
            <td>
                <img src="image/icon_7.jpg" alt="">
                境外游
                <hr  color="#ffd700" >
            </td>
        </tr>

        <!-- 第10行 -->
        <tr>
            <td>
                <table align="center" width="95%">
                    <tr>
                        <td rowspan="2">
                            <img src="image/jiangwai_1.jpg" alt="">
                        </td>

                        <td>

                            <img src="image/jiangxuan_3.jpg" alt="" height="100%">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>

                        <td>

                           <img src="image/jiangxuan_3.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>

                        <td>

                           <img src="image/jiangxuan_3.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>
                    </tr>

                    <tr>
                        <td>

                           <img src="image/jiangxuan_3.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>

                        <td>

                           <img src="image/jiangxuan_3.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>

                        <td>

                           <img src="image/jiangxuan_3.jpg" alt="">
                            <p>上海飞三亚五天4晚自由行(春节销售+亲子+蜜月+自由行)</p>
                            <font color="red">&yen; 699</font>
                        </td>


                    </tr>
                </table>
            </td>
        </tr>
        <!-- 第11行 -->
        <tr>
            <td>
                <img src="image/footer_service.png" alt="" width="100%">
            </td>
        </tr>

        <!-- 第12行 -->
        <tr>
            <td align="center" bgcolor="#ffd700" height="40">
                <font color="gray" size="2">
                江苏传智播客教育科技股份有限公司
                版权所有Copyright 2006-2018&copy;, All Rights Reserved 苏ICP备16007882
                </font>
            </td>
        </tr>
        
    </table>


</body>
</html>
```



# CSS

	CSS：







## CSS：页面美化和布局控制



#### 概念： 

Cascading Style Sheets 层叠样式表

* 层叠：多个样式可以作用在同一个html的元素上，同时生效



#### 好处：

1. 功能强大
2. 将内容展示和样式控制分离
	* 降低耦合度。解耦
	* 让分工协作更容易
	* 提高开发效率





#### CSS的使用：

CSS的使用：CSS与html结合方式

1. 内联样式
	 * 在标签内使用style属性指定css代码
	 * 如：<div style="color:red;">hello css</div>
2. 内部样式
	* 在head标签内，定义style标签，style标签的标签体内容就是css代码
	
	* 如：
		<style>
	        div{
	            color:blue;
	        }
	  </style>
	  
		body内
		
		<div>hello css</div>
3. 外部样式
	1. 定义css资源文件。
	2. 在head标签内，定义link标签，引入外部的资源文件
	
	* 如：
	
	  a.css文件：
	  		div{
	  		    color:green;
	  		}
	  	<link rel="stylesheet" href="css/a.css">

	<div>hello css</div>
	<div>hello css</div>

注意：
* 1,2,3种方式 css作用范围越来越大
* 1方式不常用，后期常用2,3
* 3种格式可以写为：
	<style>
        @import "css/a.css";
    </style>

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
<!--    <style>-->
<!--        div{-->
<!--            color: yellow;-->
<!--        }-->
<!--    </style>-->
<!--    <link rel="stylesheet" href="../a.css">-->
</head>
<body>

    <div style="color: yellow"> hello </div>
    <div>hello</div>
</body>
</html>
```

[]()





#### css语法：

* 格式：
	选择器 {
		属性名1:属性值1;
		属性名2:属性值2;
		...
	}
* 选择器:筛选具有相似特征的元素
* 注意：
	* 每一对属性需要使用；隔开，最后一对属性可以不加；



#### 选择器：

筛选具有相似特征的元素

* 分类：
	1. 基础选择器
		1. id选择器：选择具体的id属性值的元素.建议在一个html页面中id值唯一
	      
	        * 语法：#id属性值{}
	    2. 元素选择器：选择具有相同标签名称的元素
	        * 语法： 标签名称{}
	        * 注意：id选择器优先级高于元素选择器
	    3. 类选择器：选择具有相同的class属性值的元素。
	        * 语法：.class属性值{}
	        
	        * 注意：类选择器选择器优先级高于元素选择器
	        
	          ```html
	          <!DOCTYPE html>
	          <html lang="en">
	          <head>
	              <meta charset="UTF-8">
	              <title>Title</title>
	              <style>
                  #div1{
	                      color:red;
	                  }
                  div{
	                      color: blue;
	                  }
	                  .cls1{
	                      color: darkorange;
	                  }
	              </style>
	          </head>
	          <body>
	              <div>111111</div>
	              <div id="div1">111111</div>
	              <div class="cls1">11111</div>
	          </body>
	          </html>
	          ```
	        
	   
	2. 扩展选择器：
		1. 选择所有元素：
			* 语法： *{}
		2. 并集选择器：
			* 选择器1,选择器2{}
		
		3. 子选择器：筛选选择器1元素下的选择器2元素
			* 语法：  选择器1 选择器2{}
		4. 父选择器：筛选选择器2的父元素选择器1
			* 语法：  选择器1 > 选择器2{}
	
		5. 属性选择器：选择元素名称，属性名=属性值的元素
			* 语法：  元素名称[属性名="属性值"]{}
	
		6. 伪类选择器：选择一些元素具有的状态
			* 语法： 元素:状态{}
			* 如： <a>
				* 状态：
					* link：初始化的状态
					* visited：被访问过的状态
					* active：正在访问状态
					* hover：鼠标悬浮状态

```html 
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        div p{
            color:blue;
        }
        
        div > p{
            border: 1px solid;
        }
        
        input[type='text'] {
            border: 2px solid;
        }
        a:link{
            color: blueviolet;
        }
        a:hover{
            color: pink;
        }
        a:active{
            color: yellow;
        }
        a:visited{
            color: red;
        }
    </style>
</head>
<body>
    <div>
        <p>传智播客</p>
    </div>
    <p>黑马程序员</p>
    <div>啦啦啦</div>

    <input type="text">
    <input type="password">

    <br>
    <a href="#">略略略</a>

</body>
```









#### 属性

1. 字体、文本
	* font-size：字体大小
	* color：文本颜色
	* text-align：对其方式
	* line-height：行高 
2. 背景
	* background：
3. 边框
	* border：设置边框，符合属性
4. 尺寸
	* width：宽度
	* height：高度
5. 盒子模型：控制布局
	* margin：外边距
	* padding：内边距
		* 默认情况下内边距会影响整个盒子的大小
		* box-sizing: border-box;  设置盒子的属性，让width和height就是最终盒子的大小

	* float：浮动
		* left
		* right





盒子边框

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        div{
            border: 1px solid red;
        }

        .div1{
            width: 100px;
            height: 100px;
            margin: 50px;
        }

        .div2{
            width: 200px;
            height: 200px;
        }
        
        .div2{
            width: 200px;
            height: 200px;
            padding: 50px;
            /*设置盒子属性，让width和height就是盒子最终的大小*/
            box-sizing: border-box;
        }
        
    </style>

</head>
<body>
<div class="div2">
    <div class="div1"></div>
</div>

</body>
</html>
```













![image-20201124141751187](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201124141751187.png)













```html
<style>
        p{
            color: red;
            font-size: 30px;
            text-align: center;
            line-height: 200px;
            border: 1px solid red;
        }
</style>


```





## 案例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        *{
            margin: 0px;
            padding: 0px;
            box-sizing: border-box;
        }

        body{
            background: url("../register_bg.png") no-repeat center;
        }

        .rg_layout{
            width: 900px;
            height: 500px;
            border: 5px solid #EEEEEE;
            background-color: white;
            margin: auto;
            /*margin-top: 15px;*/
        }

        .rg_left{
            /*border: 1px solid red;*/
            float: left;
        }

        .rg_left > p:first-child{
            color: blueviolet;
            font-size: 20px;
        }

        .rg_left > p:last-child{
            color: seagreen;
            font-size: 15px;
        }

        .rg_center{
            /*border: 1px solid red;*/
            float: left;
            width: 450px;
        }

        .rg_right{
            /*border: 1px solid red;*/
            float: right;
        }
        
        .rg_right > p:first-child{
            font-size: 15px;
        }

        .rg_right p a {
            color: pink;
        }

        .td_left{
            width: 100px;
            height: 45px;
            text-align: right;
        }

        .td_right{
            padding-left: 50px;
        }

        #username,#password,#email,#name,#tel,#birthday{
            width: 251px;
            height: 32px;
            border: 1px solid #A6A6A6;
            border-radius: 5px;
            padding-left: 10px;
        }

        #img-check{
            height: 32px;
            vertical-align: center;
        }

        #btn_sub{
            width: 150px;
            height: 40px;
            background-color: yellow;
            border: yellow;
        }
    </style>


</head>
<body>
    <div class="rg_layout">
        <div class="rg_left">
            <p>新用户注册</p>
            <p>USER REGISTER</p>
        </div>
        <div class="rg_center">
            <form action="#" method="get">
                <table>
                    <!--        用户名-->
                    <tr>
                        <td class="td_left">
                            <label for="username">用户名</label>
                        </td>
                        <td class="td_right">
                            <input type="text" name="username" placeholder="请输入用户名" id="username">
                        </td>
                    </tr>
                    <!--        密码-->
                    <tr>
                        <td class="td_left"><label for="password">密码</label></td>
                        <td class="td_right">
                            <input type="text" name="密码" placeholder="请输入密码" id="password">
                        </td>
                    </tr>
                    <!--        email-->
                    <tr>
                        <td class="td_left"><label for="email">email</label></td>
                        <td class="td_right">
                            <input type="email" name="email" placeholder="请输入邮箱" id="email">
                        </td>
                    </tr>

                    <!--        姓名-->
                    <tr>
                        <td class="td_left"><label for="name">姓名</label></td>
                        <td class="td_right">
                            <input type="text" name="name" placeholder="请输入姓名" id="name">
                        </td>
                    </tr>

                    <!--        手机号-->
                    <tr>
                        <td class="td_left"><label for="tel">电话</label></td>
                        <td class="td_right">
                            <input type="tel" name="phone" placeholder="请输入电话" id="tel">
                        </td>
                    </tr>

                    <!--        性别-->
                    <tr>
                        <td class="td_left">性别</td>
                        <td class="td_right">
                            <label>
                                <input type="radio" name="gender" value="male"  checked>男
                                <input type="radio" name="gender" value="female">女
                            </label>
                        </td>
                    </tr>

                    <!--        出生日期-->
                    <tr>
                        <td class="td_left"><label for="birthday">出生日期</label></td>
                        <td class="td_right">
                                <input type="date" name="birthday" id="birthday">
                        </td>
                    </tr>
                    <!--        验证码-->
                    <tr>
                        <td class="td_left"><label for="checkcode">验证码</label></td>
                        <td class="td_right">
                            <input type="text" id="checkcode" name="checkcode" >
                            <img src="../../day28/image/logo.jpg" alt="验证码" id="img-check">
                        </td>
                    </tr>

                    <tr>
                        <td align="center" colspan="2">
                            <input type="submit" value="注册" id="btn_sub">
                        </td>
                    </tr>

                </table>
            </form>
        </div>
        <div class="rg_right">
            <p>已有账户 <a href="#">立即登录</a> </p>
        </div>
    </div>


</body>
</html>
```





# JavaScript基础

	1. JavaScript基础





## JavaScript介绍：

#### 概念：	

一门客户端脚本语言

* 运行在客户端浏览器中的。每一个浏览器都有JavaScript的解析引擎
* 脚本语言：不需要编译，直接就可以被浏览器解析执行了

#### 功能：

* 可以来增强用户和html页面的交互过程，可以来控制html元素，让页面有一些动态的效果，增强用户的体验。



#### JavaScript发展史：

1. 1992年，Nombase公司，开发出第一门客户端脚本语言，专门用于表单的校验。命名为 ： C--	，后来更名为：ScriptEase
2. 1995年，Netscape(网景)公司，开发了一门客户端脚本语言：LiveScript。后来，请来SUN公司的专家，修改LiveScript，命名为JavaScript
3. 1996年，微软抄袭JavaScript开发出JScript语言
4. 1997年，ECMA(欧洲计算机制造商协会)，制定出客户端脚本语言的标准：ECMAScript，就是统一了所有客户端脚本语言的编码方式。

* JavaScript = **ECMAScript** + **JavaScript**自己特有的东西(**BOM**+**DOM**)



#### ECMAScript：

客户端脚本语言的标准

#### 1.基本语法：

##### (1)与html结合方式

1. 内部JS：
	* 定义<script>，标签体内容就是js代码
2. 外部JS：
	* 定义<script>，通过src属性引入外部的js文件

* 注意：
	1. <script>可以定义在html页面的任何地方。但是定义的位置会影响执行顺序。
	2. <script>可以定义多个。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
<!--    内部js-->
    <script>
        alert("hello world")
    </script>

<!--    外部js-->
    <script src="../js/a.js"></script>

</head>
<body>
    <input type="text">
    <script>
        alert("bye world")
    </script>
</body>
</html>
```





##### (2)注释

1. 单行注释：//注释内容
2. 多行注释：/*注释内容*/





##### (3)数据类型：

1. 原始数据类型(基本数据类型)：
	1. number：数字。 整数/小数/NaN(not a number 一个不是数字的数字类型)
	2. string：字符串。 字符串  "abc" "a" 'abc'
	3. boolean: true和false
	4. null：一个对象为空的占位符
	5. undefined：未定义。如果一个变量没有给初始化值，则会被默认赋值为undefined
	
2. 引用数据类型：对象



##### (4)变量

* 变量：一小块存储数据的内存空间
* Java语言是强类型语言，而JavaScript是弱类型语言。
	* 强类型：在开辟变量存储空间时，定义了空间将来存储的数据的数据类型。只能存储固定类型的数据
	* 弱类型：在开辟变量存储空间时，不定义空间将来的存储数据类型，可以存放任意类型的数据。
* 语法：
	* var 变量名 = 初始化值;

* typeof运算符：获取变量的类型。
	* 注：null运算后得到的是object





##### (5)运算符

1. 一元运算符：只有一个运算数的运算符
	
	++，-- ， +(正号)  
	
	* ++ --: 自增(自减)
		* ++(--) 在前，先自增(自减)，再运算
   	* ++(--) 在后，先运算，再自增(自减)
   * +(-)：正负号
    * 注意：在JS中，如果运算数不是运算符所要求的类型，那么js引擎会自动的将运算数进行类型转换
            * 其他类型转number：
                * string转number：按照字面值转换。如果字面值不是数字，则转为NaN（不是数字的数字）
                
                * boolean转number：true转为1，false转为0
                
                  ```javascript
                  var b = +"123";
                  alert(b+1) //不是1231，而是124
                  
                  var b = +"abc";
                  alert(typeof(b));  //number
                  alert(b) //NaN
                  ```
                
                  
   
2. 算数运算符

  ```
  + - * / %
  ```

  

3. 赋值运算符

  ```
  = += -+  ...
  ```

  

4. 比较运算符
  > < >= <= == ===(全等于)
  * 比较方式
         1. 类型相同：直接比较
             * 字符串：按照字典顺序比较。按位逐一比较，直到得出大小为止。
             2. 类型不同：先进行类型转换，再比较
             * ===：全等于。在比较之前，先判断类型，如果类型不一样，则直接返回false



```javascript
 <script>
        document.write((3 > 1) + "<br>");  //true
        // 字符串比较
        // 字符串：按照字典顺序比较，按位逐一比较，直到得出大小为止
        document.write(("abc" > "acb") + "<br>")   //false
        // 先将字符串转为数字，然后比较
        document.write(("123" == 123) + "<br>")   //true
        // === 全等于。 在比较之前，先判断类型，如果类型不一样，则直接返回false
        document.write(("123" === 123) + "<br>");  //false
</script>
```





5.逻辑运算符
		**&&  ||   !**
			其他类型转boolean：

                1. number：0或NaN为假，其他为真(类似c++)
                2. string：除了空字符串("")，其他都是true
                3. null&undefined:都是false
                4. 对象都为true



```javascript
// java防止空指针异常
if( obj != null) {
    ...
}
    
//javascript可以这样(类似c)
if(obj) {
    ...
}
```



6.三元运算符
? : 表达式
var a = 3;
   var b = 4;

   var c = a > b ? 1:0;

 * 语法：
   * 表达式? 值1:值2;
     * 判断表达式的值，如果是true则取值1，如果是false则取值2；



```javascript
var a = 3;
var b = 4;
var c = a > b ? 1 : 0;
```





##### (6)流程控制语句：

1.if...else...

2.switch:

* 在java中，switch语句可以接受的数据类型： byte int short char,枚举(1.5) ,String(1.7)

  switch(变量):
  case 值:

* 在JS中,switch语句可以接受任意的原始数据类型

  ```javascript
  <script>
          var a = 2;
          switch(a) {
              case 1:
                  document.write("number");
                  break;
              case "abc":
                  document.write("abc");
              case null:
                  break;
              case undefined:
                  break;
          }
  </script>
  ```

  

3. while

4. do...while

5. for

   

##### (7)JS特殊语法：

1. 语句以;结尾，如果一行只有一条语句则 ;可以省略 (不建议)
2. 变量的定义使用var关键字，也可以不使用
		* 用： 定义的变量是局部变量
   * 不用：定义的变量是全局变量(不建议)



##### (8)练习




```html
8. 练习：99乘法表
		<style>
        td{
            border: 1px solid;
        }
    </style>

    <script>
        document.write("<table align='center' '>")
        for (var i = 1 ; i <= 9; i++) {
            document.write("<tr>")
            for(var j = 1 ; j <= i  ; j++) {
                var temp = i * j ;
                document.write("<td>")
                document.write("i"+"*"+"j"+"="+temp+"&nbsp;&nbsp;&nbsp;&nbsp;");
                document.write("</td>")
            }
            // document.write("<br>")
            document.write("</tr>")
        }
        document.write("</table>")
    </script>
```


​			








​	





#### 2.基本对象：

##### (1)Function：函数(方法)对象

###### 1). 创建：

1.var fun = new Function(形式参数列表,方法体);  //忘掉吧

2.function 方法名称(形式参数列表){
      方法体
    }

```javascript
//方法定义时形参的类型不用写，比如a前面的var
function fun2(a, b) {
    alert(a+b);
}

fun2(2, 3);
```



3. var 方法名 = function(形式参数列表){
   ​       	 方法体
    	  }

```javascript
var fun3 = function(a, b) {
    alert(a+b);
}

fun3(3,4);
```



###### 2)方法：

###### 3)属性：

​		length:代表形参的个数





###### 4)特点：

1. 方法定义是，形参的类型不用写,返回值类型也不写。
2. 方法是一个对象，如果定义名称相同的方法，会覆盖
3. 在JS中，**方法的调用只与方法的名称有关，和参数列表无关**
4. 在方法声明中有一个隐藏的内置对象（数组），arguments,封装所有的实际参数



```javascript
//求任意个数的和
function add() {
    var sum = 0;
    for(var i = 0 ; i < arguments.length ; i++ ) {
        sum += arguments[i];
    }
    return sum;
}

add(1, 2, 3); //可以传入任意个数的数
```



###### 5)调用：

方法名称(实际参数列表);



##### (2)Array:数组对象

1. 创建：
    1. var arr = new Array(元素列表);
    
    2. var arr = new Array(默认长度);
    
    3. var arr = [元素列表];
    
       ```javascript
       var arr1 = new Array(1, 2, 3);
       var arr2 = new Array(5);
       var arr3 = new [1,2,3,4];
       var arr4 = new Array();
       
       ```
    
       
    
    
    
2. 方法
    join(参数):将数组中的元素按照指定的分隔符拼接为字符串
    push()	向数组的末尾添加一个或更多元素，并返回新的长度。
    
    ```javascript
    //默认数组的拼接符是，可以勇join修改
    document.write(arr.join("--"));
    
    //push()往尾部添加元素
    ```
    
    
    
3. 属性
    length:数组的长度

4. 特点：
    1. JS中，数组元素的类型可变的。

    2. JS中，数组长度可变的。(没有索引越界异常)

       

```
var arr = [1,"abc",true];
```







##### (3)Boolean

基本类型boolean的包装类





##### (4)Date：日期对象

1. 创建：
    var date = new Date();

    
    
2. 方法：

    * toLocaleString()：返回当前date对象对应的时间本地字符串格式

    * getTime():获取毫秒值。返回当前如期对象描述的时间到1970年1月1日零点的毫秒值差

```javascript
var date = new Date();

document.write(date); //默认美国的时间格式
document.write(date.toLocaleString()); //当地的（中国）
document.write(date.getTime()); 

```





##### (5)Math：数学对象

1. 创建：
    * 特点：Math对象不用创建，直接使用。  Math.方法名();

2. 方法：
    random():返回 0 ~ 1 之间的随机数。 含0不含1
    ceil(x)：对数进行上舍入。
    floor(x)：对数进行下舍入。
    round(x)：把数四舍五入为最接近的整数。
3. 属性：
    PI

```javascript
//Math对象不用创建，直接使用
document.write(Math.PI);
//产生1-100的随机整数
var number = Math.floor((Math.random * 100) + 1);
```





##### (6)Number

number的包装类



##### (7)String

string的包装类



##### (8)RegExp：正则表达式对象

![image-20201125161759464](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201125161759464.png)

即是规定 期望的表达式规则



###### 正则表达式

1. 正则表达式：定义字符串的组成规则。
  1. 单个字符:[]

    	如：一个字符a： [a]

  	​		a到b字符： [ab] 
  	​		a到z A到Z 0到9：[a-zA-Z0-9_]

 	* 特殊符号代表特殊含义的单个字符:
			\d:单个数字字符 [0-9]
        		\w:单个单词字符[a-zA-Z0-9_]


  	
  2. 量词符号：

    ?：表示出现0次或1次
    *：表示出现0次或多次
    +：出现1次或多次
    {m,n}:表示 m<= 数量 <= n
    
    ​	* m如果缺省： {,n}:最多n次
    
    ​	* n如果缺省：{m,} 最少m次
    
    ```javascript
    //例如要求1.长度6-12位  2.单词字符组成
    
    \w{6,12}
    ```


​    

  3. 开始结束符号

    * ^:开始
    * $:结束



###### 正则对象

(和java、c++中通用)

2. 正则对象：

   1.创建

   var reg = new RegExp("正则表达式");

   var reg = /正则表达式/;

   2.方法	

   ​	test(参数):验证指定的字符串是否符合正则定义的规范	



```javascript
//1、
var reg = new RegExp("\\w(6,12)");
//2、常用
var reg2 = /w{6,12}/


//test
var username = "zhangsan";
var flag = reg2.test(username);
alert(flag);
```







##### (9)Global

1. 特点：全局对象，这个Global中封装的方法不需要对象就可以直接调用。  方法名();

2. 方法：
    **encodeURI():**url编码
    **decodeURI():**url解码

    **encodeURIComponent():**url编码,编码的字符更多
    **decodeURIComponent():**url解码

    **parseInt():**将字符串转为数字

    ​	* 逐一判断每一个字符是否是数字，直到不是数字为止，将前边数字部分转为number

    

    **isNaN():**判断一个值是否是NaN

        * NaN六亲不认，连自己都不认。NaN参与的==比较全部为false（NaN==NaN结构是false）

    **eval():**讲 JavaScript 字符串，并把它作为脚本代码来执行。

 3. URL编码
    传智播客 =  %E4%BC%A0%E6%99%BA%E6%92%AD%E5%AE%A2

* BOM

* DOM







# JavaScript高级

	1. JavaScript：
		1. ECMAScript：
		2. BOM：
		3. DOM：
			1. 事件



## DOM介绍

简单学习：为了满足案例要求

	* 功能：控制html文档的内容
	* 获取页面标签(元素)对象：Element
		* document.getElementById("id值"):通过元素的id获取元素对象
	
	* 操作Element对象：
		1. 修改属性值：
			1. 明确获取的对象是哪一个？
			2. 查看API文档，找其中有哪些属性可以设置
		2. 修改标签体内容：
			* 属性：innerHTML
			1. 获取元素对象
			2. 使用innerHTML属性修改标签体内容





## 事件简单学习

* 功能： 某些组件被执行了某些操作后，触发某些代码的执行。
	* 造句：  xxx被xxx,我就xxx
		* 我方水晶被摧毁后，我就责备对友。
		* 敌方水晶被摧毁后，我就夸奖自己。

* 如何绑定事件
	1. 直接在html标签上，指定事件的属性(操作)，属性值就是js代码
		1. 事件：onclick--- 单击事件

	2. 通过js获取元素对象，指定事件属性，设置一个函数







```html


	* 代码：
		<body>
			<img id="light" src="img/off.gif"  onclick="fun();">
			<img id="light2" src="img/off.gif">
			
			<script>
			    function fun(){
			        alert('我被点了');
			        alert('我又被点了');
			    }
			
			    function fun2(){
			        alert('咋老点我？');
			    }
			
			    //1.获取light2对象
			    var light2 = document.getElementById("light2");
			    //2.绑定事件
			    light2.onclick = fun2;
```


​				

```html
			</script>
		</body>

* 案例1：电灯开关
	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <title>电灯开关</title>
	
	</head>
	<body>
	
	<img id="light" src="img/off.gif">
	
	<script>
	    /*
	        分析：
	            1.获取图片对象
	            2.绑定单击事件
	            3.每次点击切换图片
	                * 规则：
	                    * 如果灯是开的 on,切换图片为 off
	                    * 如果灯是关的 off,切换图片为 on
	                * 使用标记flag来完成
	
	     */
	
	    //1.获取图片对象
	    var light = document.getElementById("light");
	
	    var flag = false;//代表灯是灭的。 off图片
	
	    //2.绑定单击事件
	    light.onclick = function(){
	        if(flag){//判断如果灯是开的，则灭掉
	            light.src = "img/off.gif";
	            flag = false;
	
	        }else{
	            //如果灯是灭的，则打开
	
	            light.src = "img/on.gif";
	            flag = true;
	        }
```


​		

		    }
		    
		</script>
		</body>
		</html>





## BOM:

### (1)概念

1. 概念：Browser Object Model 浏览器对象模型
	* 将浏览器的各个组成部分封装成对象。



![image-20201202150250668](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201202150250668.png)





### (2)组成

2. 组成：
	* Window：窗口对象
	* Navigator：浏览器对象(不常用)
	* Screen：显示器屏幕对象（不常用）
	* History：历史记录对象
	* Location：地址栏对象

（实际上还有document对象，由于太重要了，单独划为DOM讲解）





### (3)Window：窗口对象

3. Window：窗口对象

    ​    

    1. 创建

        Window对象不需要创建可以直接使用 window使用。 window.方法名();window引用可以省略。  

        方法名();

        

    2. 方法
         1. 与弹出框有关的方法：
            **alert()**	显示带有一段消息和一个确认按钮的警告框。
            **confirm()**	显示带有一段消息以及确认按钮和取消按钮的对话框。

            ​		* 如果用户点击确定按钮，则方法返回true

            ​		* 如果用户点击取消按钮，则方法返回false

            

            **prompt()**	显示可提示用户输入的对话框。

              * 返回值：获取用户输入的值

                

         2. 与打开关闭有关的方法：
            **close()**	关闭浏览器窗口。

            ​					谁调用我 ，我关谁
            **open()**	打开一个新的浏览器窗口

              				返回新的Window对象

            

            实际上，默认的window窗口为就是window，我们可以对新open的窗口对象命名（newWindow）经行操作（close）

            ```html
            <input id="openBut" type="button" value="打开窗口">
                <input id="closeBtn" type="button" value="关闭窗口">
            
                <script>
                    var openBut = document.getElementById("openBut");
                    openBut.onclick = function () {
                        newWindows = open("https://www.baidu.com")
                    }
            
                    var closeBut = document.getElementById("closeBtn");
                    closeBut.onclick = function () {
                        newWindows.close();
                    }
                    
                    
                </script>
            ```

            

            

            

            

            

            

            

         3. 与定时器有关的方式

            * setTimeout()	在指定的毫秒数后调用函数或计算表达式。

              ```javascript
              setTimeout("alert('boom');",3000);
              //3000毫秒后执行js
              setTimeout("fun();",3000);
              setTimeout("fun;",3000);
              ```

              

            参数：

            ​	1）js代码或者方法对象

            ​	2）毫秒值

            ​	返回值：唯一标识，用于取消定时器

            * clearTimeout()	取消由 setTimeout() 方法设置的 timeout。

              ```javascript
              var id = setTimeout(fun,3000);
              clearTimeout(id);
              function fun(){
                  alert('boom');
              }
              ```

              

            * setInterval()	按照指定的周期（以毫秒计）来调用函数或计算表达式。

              循环定时器~

            * clearInterval()	取消由 setInterval() 设置的 timeout。

            

            轮播图案例

            ```html
            <img id="img1" src="../banner_1.jpg" width="100%">
                <script>
                    var number = 1;
                    function fun() {
                        number++;
                        if(number>3) {
                            number = 1;
                        }
                        var img1 = document.getElementById("img1");
                        //  img1.src="../banner_2.jpg"
                        img1.src="../banner_"+number+".jpg";
                    }
            
                    setInterval(fun,3000);
                </script>
            ```

             

            

            

            

    3. 属性：
        1. 获取其他BOM对象：
            history
            location
            Navigator
            Screen:
            
        2. 获取DOM对象
            document
            
            
            
            **以上对象都是window对象的一部分**
            
            

    4. 特点
        * Window对象不需要创建可以直接使用 window使用。 window.方法名();
        * window引用可以省略。  方法名();









### (4)Location：地址栏对象

Location对象包含有关当前URL的信息。

Location对象是Window对象的一部分，可通过window.location属性来访问

4. Location：地址栏对象
	1. 创建(获取)：
		1. window.location
		2. location

	2. 方法：
		* reload()	重新加载当前文档。**刷新**
	3. 属性
		* href	设置或返回完整的 URL。

```html
<input type="button" id="refresh" value="刷新">
<script>
    var refresh = document.getElementById("refresh");
    refresh.onclick = function () {
        location.reload();
        // 或者去百度
        location.href = "https://www.baidu.com";
    }
    var href = location.href;
    alert(href);

    
    
</script>
```



案例：5s之后跳转百度

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        p{
            text-align: center;
        }
        span{
            color: red;
        }

    </style>
</head>
<body>
<p>
    <span id="time">5</span>秒之后，跳转到百度
</p>

<script>
    var second = 5;
    function fun() {
        second--;
        if(second <= 0) {
            location.href="https://www.baidu.com";
        }
        var time = document.getElementById("time");
        time.innerHTML = second + "";
    }
    setInterval(fun,1000);
</script>

</body>
</html>
```







### HTML DOM search 属性

[HTML DOM Location 对象](https://www.w3school.com.cn/jsref/dom_obj_location.asp)

#### 定义和用法

search 属性是一个可读可写的字符串，可设置或返回当前 URL 的查询部分（问号 ? 之后的部分）。

#### 语法

```
location.search=path_from_questionmark
```

#### 实例

假设当前的 URL 是: http://www.w3school.com.cn/tiy/t.asp?f=hdom_loc_search

```
<html>
<body>

<script type="text/javascript">
document.write(location.search);
</script>

</body>
</html>
```

输出：

```
?f=hdom_loc_search
```

























### (5)History：历史记录对象

history对象包含用户（在当前浏览器窗口中）访问的对象URL





5. History：历史记录对象
    1. 创建(获取)：
        1. window.history
        2. history

    2. 方法：
        * back()	加载 history 列表中的前一个 URL。
        * forward()	加载 history 列表中的下一个 URL。
        * go(参数)	加载 history 列表中的某个具体页面。
            * 参数：
                * 正数：前进几个历史记录
                * 负数：后退几个历史记录
    3. 属性：
        * length	返回当前窗口历史列表中的 URL 数量



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
    <input type="button" id="but" value="获取history数目">
    <a href="test4.html">forward</a>
    <input type="button" id="forward" value="前进">

    <script>
        var but = document.getElementById("but");
        but.onclick = function () {
            var length = history.length;
            alert(length);
        }

        var forward = document.getElementById("forward");
        forward.onclick = function () {
            history.forward();
        }
    </script>
</body>
</html>
```





## DOM：

### (1)概念

1.概念： Document Object Model 文档对象模型

	* 将标记语言文档的各个组成部分，封装为对象。可以使用这些对象，对标记语言文档进行CRUD的动态操作（CRUD create read update delete）





通过 HTML DOM，可访问 JavaScript HTML 文档的所有元素。

当网页被加载时，浏览器会创建页面的文档对象模型（Document Object Model）。 

**HTML DOM** 模型被构造为**对象**的树：

![image-20201203164102021](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201203164102021.png)











* W3C DOM 标准被分为 3 个不同的部分：

	* 核心 DOM - 针对任何结构化文档的标准模型
		
		​	(1)Document：文档对象
		
		​	(2)Element：元素对象
		
		​	(3)Attribute：属性对象
		​    (4)Text：文本对象
		​	(5)Comment:注释对
		
		​	(6)Node：节点对象，其他5个的父对象

	
	
	* XML DOM - 针对 XML 文档的标准模型
	* HTML DOM - 针对 HTML 文档的标准模型







### (2)核心DOM模型

核心DOM模型：
#### Document：文档对象

1. 创建(获取)：在html dom模型中可以使用window对象来获取
	1. window.document
	2. document
2. 方法：
	1. 获取Element对象：
		1. getElementById()	： 根据id属性值获取元素对象。id属性值一般唯一
		2. getElementsByTagName()：根据元素名称获取元素对象们。返回值是一个数组
		3. getElementsByClassName():根据Class属性值获取元素对象们。返回值是一个数组
		4. getElementsByName(): 根据name属性值获取元素对象们。返回值是一个数组
	2. 创建其他DOM对象：
		createAttribute(name)
        	createComment()
        	createElement()
        	createTextNode()
3. 属性



#### Element：元素对象

1. 获取/创建：通过document来获取和创建
2. 方法：
	1. removeAttribute()：删除属性
	2. setAttribute()：设置属性



#### Node：节点对象，其他5个的父对象

* 特点：所有dom对象都可以被认为是一个节点
* 方法：
	* CRUD dom树：
		* appendChild()：向节点的子节点列表的结尾添加新的子节点。
		* removeChild()	：删除（并返回）当前节点的指定子节点。
		* replaceChild()：用新节点替换一个子节点。
* 属性：
	* parentNode 返回节点的父节点。





```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        div{
            border: 1px red solid;
        }
        #div1{
            width: 200px;
            height: 200px;
        }
        #div2{
            width: 100px;
            height: 100px;
        }
    </style>
</head>
<body>
    <div id="div1">
        <div id="div2"> div2</div>
        div1
    </div>
    <a href="javascript:void(0)" id="a1">我是删除子节点</a>
    <a href="javascript:void(0)" id="a2">我是添加子节点</a>
    <script>
        var div1 = document.getElementById("div1");
        var div2 = document.getElementById("div2");
        var a1 = document.getElementById("a1");
        a1.onclick = function () {
            div1.removeChild(div2);
        }
        // 超链接功能：
        //     1、可以被点击：样式
        //     2、点击后跳转到href指定的url
        // 需求：保留1功能，去掉2功能
        // 实现：href="javascript:void(0)


        var a2 = document.getElementById("a2");
        a2.onclick = function () {
            var div3 = document.createElement("div");
            div3.setAttribute("id","div3");
            div1.appendChild(div3);

        }
    </script>
</body>
</html>
```



动态表格之面向对象的思想（下面有HTML的DOM的方法innerHTML）

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>动态表格</title>

    <style>
        table{
            border: 1px solid;
            margin: auto;
            width: 500px;
        }

        td,th{
            text-align: center;
            border: 1px solid;
        }
        div{
            text-align: center;
            margin: 50px;
        }
    </style>

</head>
<body>

<div>
    <input type="text" id="id" placeholder="请输入编号">
    <input type="text" id="name"  placeholder="请输入姓名">
    <input type="text" id="gender"  placeholder="请输入性别">
    <input type="button" value="添加" id="btn_add">

</div>


<table id="table">
    <caption>学生信息表</caption>
    <tr>
        <th>编号</th>
        <th>姓名</th>
        <th>性别</th>
        <th>操作</th>
    </tr>

    <tr>
        <td>1</td>
        <td>令狐冲</td>
        <td>男</td>
        <td><a href="javascript:void(0);" onclick="delTr(this);">删除</a></td>
    </tr>

    <tr>
        <td>2</td>
        <td>任我行</td>
        <td>男</td>
        <td><a href="javascript:void(0);"  onclick="delTr(this);">删除</a></td>
    </tr>

    <tr>
        <td>3</td>
        <td>岳不群</td>
        <td>?</td>
        <td><a href="javascript:void(0);"  onclick="delTr(this);">删除</a></td>
    </tr>


</table>



<script>
    /* 分析：
        1.添加：
            1.给添加按钮绑定单击事件
            2.获取文本框的内容
            3.创建td，设置td的文本为文本框的内容
            4.创建tr
            5.将td添加到tr中
            6.获取table，将tr添加到table中
         2.删除：
            1.确定点击的是哪一个超链接
            2.怎么删除 （removeChild(); 通过父节点删除子节点）
     */
    let btn_add = document.getElementById("btn_add");
    btn_add.onclick = function () {
        let id = document.getElementById("id").value;
        let name = document.getElementById("name").value;
        let gender = document.getElementById("gender").value;

        let td_id = document.createElement("td");
        let text_id = document.createTextNode(id);
        td_id.appendChild(text_id);
        let td_name = document.createElement("td");
        let text_name = document.createTextNode(name);
        td_name.appendChild(text_name);
        let td_gender = document.createElement("td");
        let text_gender = document.createTextNode(gender);
        td_gender.appendChild(text_gender);


        let td_a = document.createElement("td");
        let ele_a = document.createElement("a");
        ele_a.setAttribute("href", "javascript:void(0)")
        ele_a.setAttribute("onclick", "delTr(this)")
        let text_a = document.createTextNode("删除");
        ele_a.appendChild(text_a);
        td_a.appendChild(ele_a);

        let tr = document.createElement("tr");
        tr.appendChild(td_id);
        tr.appendChild(td_name);
        tr.appendChild(td_gender);
        tr.appendChild(td_a);
        let table = document.getElementsByTagName("table")[0];
        table.appendChild(tr);
    }


    function delTr(obj) {
        //onclick="delTr(this) this代表当前超链接对象
        let table = obj.parentNode.parentNode.parentNode;
        let tr = obj.parentNode.parentNode;
        table.removeChild(tr);

    }





    //1.获取btn
    var btn_add = document.getElementById("btn_add");
    //2.绑定单击事件
    btn_add.onclick = function(){
        //获取每一个输入框内容
        var id = document.getElementById("id").value;
        var name = document.getElementById("name").value;
        var gender = document.getElementById("gender").value;

        //获取表格
        var table = document.getElementById("table");

        //创建tr
        var tr = document.createElement("tr");
        //创建td
        var td_id = document.createElement("td");
        var text_id = document.createTextNode(id);
        td_id.appendChild(text_id);
        tr.appendChild(td_id);

        var td_name = document.createElement("td");
        var text_name = document.createTextNode(name);
        td_name.appendChild(text_name);
        tr.appendChild(td_name);

        var td_gender = document.createElement("td");
        var text_gender = document.createTextNode(gender);
        td_gender.appendChild(text_gender);
        tr.appendChild(td_gender);

        var td_option = document.createElement("td");

        var a = document.createElement("a");
        a.setAttribute("href","javascript:void(0);");
        a.setAttribute("onclick","delTr(this)");
        var text_a = document.createTextNode("删除");
        a.appendChild(text_a);
        td_option.appendChild(a);
        tr.appendChild(td_option);

        table.appendChild(tr);

    }

    function delTr(obj){
        var table = obj.parentNode.parentNode.parentNode;
        var tr = obj.parentNode.parentNode;
        table.removeChild(tr);
    }

</script>
</body>
</html>
```









### (3)HTML DOM

什么是 HTML DOM？

HTML DOM 是：

- HTML 的标准对象模型 
- HTML 的标准编程接口 
- W3C 标准 

HTML DOM 定义了所有 HTML 元素的*对象*和*属性*，以及访问它们的*方法*。

*换言之，HTML DOM 是关于如何获取、修改、添加或删除 HTML 元素的标准。*



```html
    <script>
        let div = document.getElementById("div1")
        let innerHTML = div.innerHTML;
        //alert(innerHTML);

        div.innerHTML += "div";
        div.innerHTML += "<input type='text'>";
    </script>
```





* HTML DOM
	1. 标签体的设置和获取：**innerHTML**
	2. 使用html元素对象的属性
	3. 控制元素样式
		1. 使用元素的style属性来设置
			如：
				 //修改样式方式1
		        div1.style.border = "1px solid red";
		        div1.style.width = "200px";
		        //font-size--> fontSize
		        div1.style.fontSize = "20px";
		   
		   样式.style
		   
		   ```html
		       <div id="div1">
		           div
		       </div>
		   
		       <script>
		           let div1 = document.getElementById("div1");
		           div1.onclick = function () {
		               div1.style.border = "1px solid red";
		           }
		           
		           
		       </script>
		   ```
		   
		   
		   
		2. 提前定义好类选择器的样式，通过元素的className属性来设置其class属性值。

```html
    <style>
        .d1{
            border: 1px solid red;
            width: 100px;
            height: 100px;
        }
    </style>
</head>
<body>

    <div id="div1">
        div1
    </div>

    <div id="div2">
        div2
    </div>

    <script>
        let div1 = document.getElementById("div1");
        div1.onclick = function () {
            div1.style.border = "1px solid red";
        }

        let div2 = document.getElementById("div2");
        div2.onclick = function () {
            div2.className = "d1";
        }

    </script>
```







**修改的动态表格（HTML DOM版本）**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>动态表格</title>

    <style>
        table{
            border: 1px solid;
            margin: auto;
            width: 500px;
        }

        td,th{
            text-align: center;
            border: 1px solid;
        }
        div{
            text-align: center;
            margin: 50px;
        }
    </style>

</head>
<body>

<div>
    <input type="text" id="id" placeholder="请输入编号">
    <input type="text" id="name"  placeholder="请输入姓名">
    <input type="text" id="gender"  placeholder="请输入性别">
    <input type="button" value="添加" id="btn_add">

</div>


<table id="table">
    <caption>学生信息表</caption>
    <tr>
        <th>编号</th>
        <th>姓名</th>
        <th>性别</th>
        <th>操作</th>
    </tr>

    <tr>
        <td>1</td>
        <td>令狐冲</td>
        <td>男</td>
        <td><a href="javascript:void(0);" onclick="delTr(this);">删除</a></td>
    </tr>

    <tr>
        <td>2</td>
        <td>任我行</td>
        <td>男</td>
        <td><a href="javascript:void(0);"  onclick="delTr(this);">删除</a></td>
    </tr>

    <tr>
        <td>3</td>
        <td>岳不群</td>
        <td>?</td>
        <td><a href="javascript:void(0);"  onclick="delTr(this);">删除</a></td>
    </tr>


</table>



<script>
    /* 分析：
        1.添加：
            1.给添加按钮绑定单击事件
            2.获取文本框的内容
            3.创建td，设置td的文本为文本框的内容
            4.创建tr
            5.将td添加到tr中
            6.获取table，将tr添加到table中
         2.删除：
            1.确定点击的是哪一个超链接
            2.怎么删除 （removeChild(); 通过父节点删除子节点）
     */
    let btn_add = document.getElementById("btn_add");
    // btn_add.onclick = function () {
    //     let id = document.getElementById("id").value;
    //     let name = document.getElementById("name").value;
    //     let gender = document.getElementById("gender").value;
    //
    //     let td_id = document.createElement("td");
    //     let text_id = document.createTextNode(id);
    //     td_id.appendChild(text_id);
    //     let td_name = document.createElement("td");
    //     let text_name = document.createTextNode(name);
    //     td_name.appendChild(text_name);
    //     let td_gender = document.createElement("td");
    //     let text_gender = document.createTextNode(gender);
    //     td_gender.appendChild(text_gender);
    //
    //
    //     let td_a = document.createElement("td");
    //     let ele_a = document.createElement("a");
    //     ele_a.setAttribute("href", "javascript:void(0)")
    //     ele_a.setAttribute("onclick", "delTr(this)")
    //     let text_a = document.createTextNode("删除");
    //     ele_a.appendChild(text_a);
    //     td_a.appendChild(ele_a);
    //
    //     let tr = document.createElement("tr");
    //     tr.appendChild(td_id);
    //     tr.appendChild(td_name);
    //     tr.appendChild(td_gender);
    //     tr.appendChild(td_a);
    //     let table = document.getElementsByTagName("table")[0];
    //     table.appendChild(tr);
    // }
    btn_add.onclick = function () {
        let id = document.getElementById("id").value;
        let name = document.getElementById("name").value;
        let gender = document.getElementById("gender").value;

        let table = document.getElementsByTagName("table")[0];

        table.innerHTML += "<tr>\n" +
            "        <td>" +id+ "</td>\n" +
            "        <td>" +name+ "</td>\n" +
            "        <td>" +gender+ "</td>\n" +
            "        <td><a href=\"javascript:void(0);\"  onclick=\"delTr(this);\">删除</a></td>\n" +
            "    </tr>"
    }

    function delTr(obj) {
        //onclick="delTr(this) this代表当前超链接对象
        let table = obj.parentNode.parentNode.parentNode;
        let tr = obj.parentNode.parentNode;
        table.removeChild(tr);

    }




</script>
</body>
</html>
```









## 事件监听机制：



### （1）概念

* 概念：某些组件被执行了某些操作后，触发某些代码的执行。	
	* 事件：某些操作。如： 单击，双击，键盘按下了，鼠标移动了
	* 事件源：组件。如： 按钮 文本输入框...
	* 监听器：代码。
	* 注册监听：将事件，事件源，监听器结合在一起。 当事件源上发生了某个事件，则触发执行某个监听器代码。







#### 对事件作出反应

当事件发生时，可以执行 JavaScript，比如当用户点击一个 HTML 元素时。

如需在用户点击某个元素时执行代码，请把 JavaScript 代码添加到 HTML 事件属性中：

onclick=*JavaScript* 

HTML 事件的例子：

- 当用户点击鼠标时 
- 当网页已加载时 
- 当图片已加载时 
- 当鼠标移动到元素上时 
- 当输入字段被改变时 
- 当 HTML 表单被提交时 
- 当用户触发按键时 

在本例中，当用户点击时，会改变 <h1> 元素的内容：



事件对象event

```html
 <script>
        window.onload = function () {
             document.onmousedown = function (event) {
                 alert(event.button);
             }
        }
    </script>
    <input type="text" id="username">
```











### （2）常见的事件

常见的事件：
##### 点击事件：

1. onclick：单击事件
2. ondblclick：双击事件



##### 焦点事件

1. onblur：失去焦点(一般用于表单校验)
2. onfocus:元素获得焦点。

```html
<input type="text" id="username">
    <script>
        let username = document.getElementById("username");
        username.onblur = function () {
            alert("失去焦点了")
        }
    </script>
```



##### 加载事件：

1. onload：一张页面或一幅图像完成加载。（用的多）

   注意顺序！， onload加载完window才会执行function

```html
<script>
        window.onload = function () {
            let username = document.getElementById("username");
            username.onblur = function () {
                alert("失去焦点了")
            }
        }
</script>
    <input type="text" id="username">
```





##### 鼠标事件：

1. onmousedown	鼠标按钮被按下。
2. onmouseup	鼠标按键被松开。
3. onmousemove	鼠标被移动。
4. onmouseover	鼠标移到某元素之上。
5. onmouseout	鼠标从某元素移开。



```html
    <script>
        window.onload = function () {
             document.onmousemove = function () {
                 alert("鼠标移动")
             }
        }
    </script>
    <input type="text" id="username">
```





##### 键盘事件：

1. onkeydown	某个键盘按键被按下。	
2. onkeyup		某个键盘按键被松开。
3. onkeypress	某个键盘按键被按下并松开。



##### 选择和改变

1. onchange	域的内容被改变。
2. onselect	文本被选中。



##### 表单事件：

1. onsubmit	确认按钮被点击。
2. onreset	重置按钮被点击。



```html

// 这里我需要的不是执行的代码，而是最后返回的值 即checkForm的返回值
<form action="#" id="form" onclick="return checkForm();">
    <label for="username"></label><input id="username" name="username" type="text">
    <label for="city"></label><select name="destination" id="city">
        <option >--请选择--</option>
        <option >北京</option>
        <option >武汉</option>
        <option >上海</option>
    </select>
    <input type="submit" value="提交">
</form>

<script>
    // window.onload = function () {
    //     let form = document.getElementById("form");
    //     form.onsubmit = function () { //返回ture返回提交，否则不提交
    //         return false;
    //     }
    //
    // }

    function checkForm() {
        return false;
    }
</script>
```



​		

案例1：表格全选

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>表格全选</title>
    <style>
        table{
            border: 1px solid;
            width: 500px;
            margin-left: 30%;
        }

        td,th{
            text-align: center;
            border: 1px solid;
        }
        div{
            margin-top: 10px;
            margin-left: 30%;
        }

        .over{
            background-color: pink;
        }
        .out{
            background-color: white;
        }
    </style>

    <script>
        window.onload =function () {
            document.getElementById("selectAll").onclick = function () {
                /* 1.全选
                        * 获取所有的checkbox
                        * 遍历cb，设置每一个cb的状态为选中
                * */
                let cbs = document.getElementsByName("cb");
                for (let i = 0; i < cbs.length; i++) {
                    cbs[i].checked = true;
                }
            }

            // 2 全不选
            document.getElementById("unSelectAll").onclick = function () {
                let cbs = document.getElementsByName("cb");
                for (let i = 0; i < cbs.length; i++) {
                    cbs[i].checked = false;
                }
            }

            // 3 反选
            document.getElementById("selectRev").onclick = function () {
                let cbs = document.getElementsByName("cb");
                for (let i = 0; i < cbs.length; i++) {
                    let flag = cbs[i].checked;
                    cbs[i].checked = !flag;
                }
            }

            // 4 第一个cb
            document.getElementById("firstcb").onclick = function () {
                let cbs = document.getElementsByName("cb");
                for (let i = 0; i < cbs.length; i++) {
                    cbs[i].checked = this.checked;
                }
            }

            // 给所有tr绑定鼠标移到元素之上和移出元素之上事情
            let trs = document.getElementsByTagName("tr");
            for (let i = 0; i < trs.length; i++) {
                trs[i].onmouseover = function () {
                    this.className = "over";
                }
                trs[i].onmouseout = function () {
                    this.className = "out";
                }
            }


        }
    </script>

</head>
<body>

<table>
    <caption>学生信息表</caption>
    <tr>
        <th><input type="checkbox" name="cb" id="firstcb"></th>
        <th>编号</th>
        <th>姓名</th>
        <th>性别</th>
        <th>操作</th>
    </tr>

    <tr>
        <td><input type="checkbox" name="cb"></td>
        <td>1</td>
        <td>令狐冲</td>
        <td>男</td>
        <td><a href="javascript:void(0);">删除</a></td>
    </tr>

    <tr>
        <td><input type="checkbox" name="cb"></td>
        <td>2</td>
        <td>任我行</td>
        <td>男</td>
        <td><a href="javascript:void(0);">删除</a></td>
    </tr>

    <tr>
        <td><input type="checkbox" name="cb"></td>
        <td>3</td>
        <td>岳不群</td>
        <td>?</td>
        <td><a href="javascript:void(0);">删除</a></td>
    </tr>

</table>
<div>
    <input type="button" id="selectAll" value="全选">
    <input type="button" id="unSelectAll" value="全不选">
    <input type="button" id="selectRev" value="反选">
</div>
</body>
</html>
```



案例3：表单校验

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>注册页面</title>
    <style>
        * {
            margin: 0px;
            padding: 0px;
            box-sizing: border-box;
        }

        body {
            /*background: url("../banner_1.jpg") no-repeat center;*/
            padding-top: 25px;
        }

        .rg_layout {
            width: 900px;
            height: 500px;
            border: 8px solid #EEEEEE;
            background-color: white;
            /*让div水平居中*/
            margin: auto;
        }

        .rg_left {
            /*border: 1px solid red;*/
            float: left;
            margin: 15px;
        }

        .rg_left > p:first-child {
            color: #FFD026;
            font-size: 20px;
        }

        .rg_left > p:last-child {
            color: #A6A6A6;
            font-size: 20px;

        }

        .rg_center {
            float: left;
            /* border: 1px solid red;*/

        }

        .rg_right {
            /*border: 1px solid red;*/
            float: right;
            margin: 15px;
        }

        .rg_right > p:first-child {
            font-size: 15px;

        }

        .rg_right p a {
            color: pink;
        }

        .td_left {
            width: 100px;
            text-align: right;
            height: 45px;
        }

        .td_right {
            padding-left: 50px;
        }

        #username, #password, #email, #name, #tel, #birthday, #checkcode {
            width: 251px;
            height: 32px;
            border: 1px solid #A6A6A6;
            /*设置边框圆角*/
            border-radius: 5px;
            padding-left: 10px;
        }

        #checkcode {
            width: 110px;
        }

        #img_check {
            height: 32px;
            vertical-align: middle;
        }

        #btn_sub {
            width: 150px;
            height: 40px;
            background-color: #FFD026;
            border: 1px solid #FFD026;
        }

        #td_sub{
            padding-left: 150px;
        }

        .error{
            color:red;
            vertical-align: middle;
        }
    </style>

    <script>
        window.onload = function () {
            /**
             *  分析：
             *      1.给表单绑定onsubmit事件。监听器中判断每一个方法的结果
             *          如果都为true，则监听器方法返回true
             *          如果有一个为false，则监听器返回false
             *      2.定义一些方法分别校验
             *      3.给各个表单绑定onblur事件
             *
             */
            document.getElementById("form").onsubmit = function () {
                return  checkUsername() && checkPassword();
            }
            //给用户名和密码分别绑定离焦事件
            document.getElementById("username").onblur = checkUsername; //此处是函数对象，不带()
            document.getElementById("password").onblur = checkPassword;
            //校验用户名
            function checkUsername() {
                let username = document.getElementById("username").value;
                let reg_username = /^\w{6,12}$/;
                let flag = reg_username.test(username);
                let s_username = document.getElementById("s_username");
                if(flag) {
                    s_username.innerHTML = "正确";
                }else{
                    s_username.innerHTML = "错误";
                }
                return flag;
            }

            function checkPassword() {
                let password = document.getElementById("password").value;
                let reg_password = /^\w{6,12}$/;
                let flag = reg_password.test(password);
                let s_password = document.getElementById("s_password");
                if(flag) {
                    s_password.innerHTML = "正确";
                }else{
                    s_password.innerHTML = "错误";
                }
                return flag;
            }
        }
    </script>



</head>
<body>

<div class="rg_layout">
    <div class="rg_left">
        <p>新用户注册</p>
        <p>USER REGISTER</p>

    </div>

    <div class="rg_center">
        <div class="rg_form">
            <!--定义表单 form-->
            <form action="#" id="form" method="get">
                <table>
                    <tr>
                        <td class="td_left"><label for="username">用户名</label></td>
                        <td class="td_right">
                            <input type="text" name="username" id="username" placeholder="请输入用户名">
                            <span id="s_username" class="error"></span>
                        </td>

                    </tr>

                    <tr>
                        <td class="td_left"><label for="password">密码</label></td>
                        <td class="td_right">
                            <input type="password" name="password" id="password" placeholder="请输入密码">
                            <span id="s_password" class="error"></span>
                        </td>
                    </tr>

                    <tr>
                        <td class="td_left"><label for="email">Email</label></td>
                        <td class="td_right"><input type="email" name="email" id="email" placeholder="请输入邮箱"></td>
                    </tr>

                    <tr>
                        <td class="td_left"><label for="name">姓名</label></td>
                        <td class="td_right"><input type="text" name="name" id="name" placeholder="请输入姓名"></td>
                    </tr>

                    <tr>
                        <td class="td_left"><label for="tel">手机号</label></td>
                        <td class="td_right"><input type="text" name="tel" id="tel" placeholder="请输入手机号"></td>
                    </tr>

                    <tr>
                        <td class="td_left"><label>性别</label></td>
                        <td class="td_right">
                            <input type="radio" name="gender" value="male"> 男
                            <input type="radio" name="gender" value="female"> 女
                        </td>
                    </tr>

                    <tr>
                        <td class="td_left"><label for="birthday">出生日期</label></td>
                        <td class="td_right"><input type="date" name="birthday" id="birthday" placeholder="请输入出生日期">
                        </td>
                    </tr>

                    <tr>
                        <td class="td_left"><label for="checkcode">验证码</label></td>
                        <td class="td_right"><input type="text" name="checkcode" id="checkcode" placeholder="请输入验证码">
                            <img id="img_check" src="img/verify_code.jpg">
                        </td>
                    </tr>


                    <tr>
                        <td colspan="2"  id="td_sub"><input type="submit" id="btn_sub" value="注册"></td>
                    </tr>
                </table>

            </form>


        </div>

    </div>

    <div class="rg_right">
        <p>已有账号?<a href="#">立即登录</a></p>
    </div>


</div>


</body>
</html>
```





# 扩展知识URL&&URI

本文讨论了统一资源定位符(URL)，并解释了他们是什么，以及如何被构建的。

| 前提: | 你首先需要知道[ 互联网是如何工作的](https://developer.mozilla.org/zh-CN/docs/Learn/How_the_Internet_works)，[什么是网络服务器](https://developer.mozilla.org/zh-CN/docs/Learn/Common_questions/What_is_a_web_server) 以及 [网络中超链接的概念](https://developer.mozilla.org/zh-CN/docs/Learn/Common_questions/What_are_hyperlinks)。 |
| :---- | ------------------------------------------------------------ |
| 目标: | 你将会学习到 URL是什么，以及它在网络上是如何工作的 。        |

你可能想到一个URL类似普通信件的地址：协议代表你要使用的邮政服务，域名是城市或者城镇，端口则像邮政编码；路径代表着你的信件所有递送的大楼；参数则提供额外的信息，如大楼所在单元；最后，锚点表示信件的收件人。



## 概述

和 [Hypertext](https://developer.mozilla.org/zh-CN/docs/Glossary/Hypertext) 以及 [HTTP](https://developer.mozilla.org/zh-CN/docs/Glossary/HTTP) 一样，**URL** 是 Web 中的一个核心概念。它是[浏览器](https://developer.mozilla.org/zh-CN/docs/Glossary/浏览器)用来检索 web 上公布的任何资源的机制。

**URL 代表着是统一资源定位符（***Uniform Resource Locator***）**。URL 无非就是一个给定的独特资源在 Web 上的地址。理论上说，每个有效的 URL 都指向一个唯一的资源。这个资源可以是一个 HTML 页面，一个 CSS 文档，一幅图像，等等。而在实际中，也有一些例外，最常见的情况就是一个 URL 指向了不存在的或是被移动过的资源。由于通过 URL 呈现的资源和 URL 本身由 Web 服务器处理，因此 web 服务器的拥有者需要认真地维护资源以及与它关联的URL。

## 自主学习

*还没有可用的资料。[Please, consider contributing](https://developer.mozilla.org/en-US/docs/MDN/Getting_started).*

## 深入探索

### 基础：剖析URL



下面是一些URL的示例：

```html
https://developer.mozilla.org
https://developer.mozilla.org/en-US/docs/Learn/
https://developer.mozilla.org/en-US/search?q=URL
```

您可以将上面的这些网址输进您的浏览器地址栏来告诉浏览器加载相关联的页面（或资源）。

一个URL由不同的部分组成，其中一些是必须的，而另一些是可选的。让我们以下面这个URL为例看看其中最重要的部分：

```html
http://www.example.com:80/path/to/myfile.html?key1=value1&key2=value2#SomewhereInTheDocument
```

- ![Protocol](https://mdn.mozillademos.org/files/15766/mdn-url-protocol@x2_update.png)

  `http` 是协议。它表明了浏览器必须使用何种协议。它通常都是HTTP协议或是HTTP协议的安全版，即HTTPS。Web需要它们二者之一，但浏览器也知道如何处理其他协议，比如`mailto:（打开邮件客户端）或者 ``ftp:（处理文件传输），所以当你看到这些协议时，不必惊讶。`

- ![Domaine Name](https://mdn.mozillademos.org/files/8015/mdn-url-domain@x2.png)

  `www.example.com` 是域名。 它表明正在请求哪个Web服务器。或者，可以直接使用[IP address](https://developer.mozilla.org/zh-CN/docs/Glossary/IP地址), 但是因为它不太方便，所以它不经常在网络上使用。.

- ![Port](https://mdn.mozillademos.org/files/8017/mdn-url-port@x2.png)

  `:80` 是端口。 它表示用于访问Web服务器上的资源的技术“门”。如果Web服务器使用HTTP协议的标准端口（HTTP为80，HTTPS为443）来授予其资源的访问权限，则通常会被忽略。否则是强制性的。

- ![Path to the file](https://mdn.mozillademos.org/files/8019/mdn-url-path@x2.png)

  `/path/to/myfile.html` 是网络服务器上资源的路径。在Web的早期阶段，像这样的路径表示Web服务器上的物理文件位置。如今，它主要是由没有任何物理现实的Web服务器处理的抽象。

- ![Parameters](https://mdn.mozillademos.org/files/8021/mdn-url-parameters@x2.png)

  `?key1=value1&key2=value2` 是提供给网络服务器的额外参数。 这些参数是用 `& `符号分隔的键/值对列表。在返回资源之前，Web服务器可以使用这些参数来执行额外的操作。每个Web服务器都有自己关于参数的规则，唯一可靠的方式来知道特定Web服务器是否处理参数是通过询问Web服务器所有者。

- ![Anchor](https://mdn.mozillademos.org/files/8023/mdn-url-anchor@x2.png)

  `#SomewhereInTheDocument` 是资源本身的另一部分的锚点. 锚点表示资源中的一种“书签”，给浏览器显示位于该“加书签”位置的内容的方向。例如，在HTML文档上，浏览器将滚动到定义锚点的位置;在视频或音频文档上，浏览器将尝试转到锚代表的时间。值得注意的是，＃后面的部分（也称为片段标识符）从来没有发送到请求的服务器。

**Note:** 这里是关于URLs的 [一些额外的部分和一些额外的规则](http://en.wikipedia.org/wiki/Uniform_Resource_Locator) , 但它们对于普通用户或Web开发者不是非常重要。 你不必担心这个，要构筑和使用完全实用的URLs不必了解这些。

你可能想到一个URL类似普通信件的地址：协议代表你要使用的邮政服务，域名是城市或者城镇，端口则像邮政编码；路径代表着你的信件所有递送的大楼；参数则提供额外的信息，如大楼所在单元；最后，锚点表示信件的收件人。

### 如何使用URL



可以直接在浏览器的地址栏里输入任何URL，来获得后台的资源。但是这仅仅是冰山一角。

 [HTML](https://developer.mozilla.org/zh-CN/docs/Glossary/HTML) 语言 — [后续会再来讨论](https://developer.mozilla.org/en-US/docs/Learn/HTML/HTML_tags) — 对URLs有大量的使用:

- 为在其他文档中新建链接，用 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a) ;
- 为将文档与它的相关资源关联，用各种标签如 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link) 或 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/script) ;
- 为显示多媒体如图片 (用 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/img) ), 视频 (用 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/video) ), 声音和音乐 (用 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/audio) ), 等等;
- 为显示其他HTML文档，用 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/iframe) .

其他大量使用URLs的技术如 [CSS](https://developer.mozilla.org/zh-CN/docs/Glossary/CSS) 或 [JavaScript](https://developer.mozilla.org/zh-CN/docs/Glossary/JavaScript), 这些才是Web的中心。

### 绝对URL和相对URL



我们上面看到的是一个绝对的URL，但也有一个叫做相对URL的东西。我们来看看这个区别意味着什么呢？

URL的必需部分在很大程度上取决于使用URL的上下文。在浏览器的地址栏中，网址没有任何上下文，因此您必须提供一个完整的（或绝对的）URL，就像我们上面看到的一样。您不需要包括协议（浏览器默认使用HTTP）或端口（仅当目标Web服务器使用某些异常端口时才需要），但URL的所有其他部分都是必需的。

当文档中使用URL时，例如HTML页面中的内容有所不同。因为浏览器已经有文档自己的URL，它可以使用这些信息来填写该文档中可用的任何URL的缺失部分。我们可以通过仅查看URL的路径部分来区分绝对URL和相对URL。**如果URL的路径部分以“/”字符开头，则浏览器将从服务器的顶部根目录获取该资源，而不引用当前文档给出的上下文**。

我们来看一些例子来使这个更清楚。

#### 绝对URL示例

- 完整网址（与之前使用的网址相同）

  `https://developer.mozilla.org/en-US/docs/Learn`

- 隐去协议

  `//developer.mozilla.org/en-US/docs/Learn`在这种情况下，浏览器将使用与用于加载该URL的文档相同的协议来调用该URL。

- 隐去域名

  `/en-US/docs/Learn`这是HTML文档中绝对URL最常见的用例。浏览器将使用与用于加载托管该URL的文档相同的协议和相同的域名。**注意**：不可能省略该域名而不省略协议。

#### 相对URL示例

为了更好地了解以下示例，我们假设从位于以下URL的文档中调用URL： `https://developer.mozilla.org/en-US/docs/Learn`

- 子资源

  `Skills/Infrastructure/Understanding_URLs `因为该URL不以/开头，浏览器将尝试在包含当前资源的子目录中查找文档。所以在这个例子中，我们真的想要达到这个URL`https://developer.mozilla.org/en-US/docs/Learn/Skills/Infrastructure/Understanding_URLs`

- 回到目录树中

  `../CSS/display`在这种情况下，我们使用从UNIX文件系统世界继承的../写入约定来告诉我们要从一个目录上升的浏览器。在这里，我们要达到以下URL：https://developer.mozilla.org/en-US/docs/Learn/../CSS/display，可以将其简化为：https://developer.mozilla.org/en-US/docs/CSS/display

### 语义 URLs



尽管URL具有非常的技术性，但URL表示一个可读性的网站入口点。它们可以被记住，并且任何人都可以将它们输入浏览器的地址栏。人是Web的核心，因此建立所谓的 *[semantic URLs](http://en.wikipedia.org/wiki/Semantic_URL)* 被认为是最佳实践。语义URL使用具有固有含义的单词，任何人都可以理解，无论他们的技术水平如何。

语言语义当然与电脑无关。您可能经常看到看起来像随机字符混搭的网址。但创建人类可读的URL有很多优点：

- 操作它们更容易
- 它根据用户在哪里，他们在做什么，他们正在阅读或在网络上进行互动来澄清用户的情况。
- 一些搜索引擎可以使用这些语义来改进相关页面的分类。





## URI

URI = Universal Resource Identifier 统一资源**标志符**
URL = Universal Resource Locator 统一资源**定位符**
URN = Universal Resource Name 统一资源**名称**

也就是说，URI分为三种，URL or URN or （URL and URI）
URL代表资源的路径地址，而URI代表资源的名称。
通过URL找到资源是对网络位置进行标识，如：

- **http://example.org/absolute/URI/with/absolute/path/to/resource.txt**
- **ftp://example.org/resource.txt**

通过URI找到资源是通过对名称进行标识，这个名称在某命名空间中，并不代表网络地址，如：

- **urn:issn:1535-3613**





URI = Uniform Resource Identifier 统一资源**标志符**


URL = Uniform Resource Locator 统一资源**定位符**
URN = Uniform Resource Name 统一资源**名称**



**大白话，就是**URI是抽象的定义，不管用什么方法表示，只要能定位一个资源，就叫URI，本来设想的的使用两种方法定位：1，URL，用地址定位；2，URN 用名称定位。

举个例子：去村子找个具体的人（URI），如果用地址：某村多少号房子第几间房的主人 就是URL， 如果用身份证号+名字 去找就是URN了。

结果就是 目前WEB上就URL流行开了，平常见得URI 基本都是URL。





![image-20201225111627573](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201225111627573.png)

##### URI，URL，URN

从上面的那幅图可以看出来，一共有三个不同的概念URI,URL,URN。这讨论这样的问题时，最好的方法就是回到原点啊，这里我们在[RFC 3986: Uniform Resource Identifier (URI): Generic Syntax](http://tools.ietf.org/html/rfc3986)里面收集了点资料：

“A Uniform Resource Identifier (URI) 是一个紧凑的字符串用来标示抽象或物理资源。”

“A URI 可以进一步被分为定位符、名字或两者都是. 术语“Uniform Resource Locator” (URL) 是URI的子集, 除了确定一个资源,还提供一种定位该资源的主要访问机制(如其网络“位置”)。“

那我们无所不知的维基百科把这段消化的很好，并描述的更加形象了









# Bootstrap：

	1. Bootstrap







## 1.概念： 

概念：一个前端开发的框架，Bootstrap，来自 Twitter，是目前很受欢迎的前端框架。Bootstrap 是基于 HTML、CSS、JavaScript 的，它简洁灵活，使得 Web 开发更加快捷。

* 框架:一个半成品软件，开发人员可以在框架基础上，在进行开发，简化编码。
* 好处：
	1. 定义了很多的css样式和js插件。我们开发人员直接可以使用这些样式和插件得到丰富的页面效果。
	2. 响应式布局。
		* 同一套页面可以兼容不同分辨率的设备。

(淘宝不是响应式布局电脑端为：www.taobao.com 手机端为：www.m.taobao.com)

(苹果官网是响应式布局：www.apple.com   任意大小界面访问均可)





## 2.快速入门

1. 下载Bootstrap
2. 在项目中将这三个文件夹复制
3. 创建html页面，引入必要的资源文件






```html
	<!DOCTYPE html>
	<html lang="zh-CN">
	<head>
	    <meta charset="utf-8">
	    <meta http-equiv="X-UA-Compatible" content="IE=edge">
	    <meta name="viewport" content="width=device-width, initial-scale=1">
	    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
	    <title>Bootstrap HelloWorld</title>
	
	    <!-- Bootstrap -->
	    <link href="css/bootstrap.min.css" rel="stylesheet">
	    <!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
	    <script src="js/jquery-3.2.1.min.js"></script>
	    <!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
	    <script src="js/bootstrap.min.js"></script>
	</head>
	<body>
	<h1>你好，世界！</h1>
	
	</body>
	</html>
```


​		



## 响应式布局

* 同一套页面可以兼容不同分辨率的设备。
* 实现：依赖于栅格系统：将一行平均分成12个格子，可以指定元素占几个格子

![image-20201214200030771](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201214200030771.png)





* 步骤：
	1. 定义容器。相当于之前的table、
		* 容器分类：
			1. container：两边留白
			2. container-fluid：每一种设备都是100%宽度
	2. 定义行。相当于之前的tr   样式：row
	3. 定义元素。相当于之前的td，指定该元素在不同的设备上，所占的格子数目。样式：**col-设备代号-格子数目**
		* 设备代号：
			1. xs：超小屏幕 手机 (<768px)：col-xs-12
			2. sm：小屏幕 平板 (≥768px)
			3. md：中等屏幕 桌面显示器 (≥992px)
			4. lg：大屏幕 大桌面显示器 (≥1200px)

	* 注意：
		1. 一行中如果格子数目超过12，则超出部分自动换行。
		2. 栅格类属性可以向上兼容。栅格类适用于与屏幕宽度大于或等于分界点大小的设备。
		3. 如果真实设备宽度小于了设置栅格类属性的设备代码的最小值，会一个元素沾满一整行

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap 101 Template</title>
    <!-- Bootstrap -->
    <link href="../css/bootstrap.min.css" rel="stylesheet">
    <!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
    <script src="../js/jquery-3.2.1.min.js"></script>
    <!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
    <script src="../js/bootstrap.min.js"></script>
    <style>
        .inner{
            border: 1px solid red;
        }
    </style>
</head>
<body>
<div class="container-fluid">
    <div class="row">
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
        <div class="col-lg-1 col-sm-2 inner">栅格</div>
    </div>
</div>
</body>
</html>
```











## CSS样式和JS插件

### 1.全局CSS样式：

* 按钮：class="btn btn-default"
* 图片：
  *  class="img-responsive"：图片在任意尺寸都占100%
  * 图片形状
    ```
    *  <img src="..." alt="..." class="img-rounded">：方形
    *  <img src="..." alt="..." class="img-circle"> ： 圆形
    *  <img src="..." alt="..." class="img-thumbnail"> ：相框
    ```

* 表格
	* table
	* table-bordered
	* table-hover
* 表单
	
	* 给表单项添加：class="form-control" 



### 2.组件：

* 导航条
* 分页条

### 3.插件：

* 轮播图





## 案例

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap 101 Template</title>

    <!-- Bootstrap -->
    <link href="../css/bootstrap.min.css" rel="stylesheet">
    <!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
    <script src="js/jquery-3.2.1.min.js"></script>
    <!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
    <script src="js/bootstrap.min.js"></script>
    <style>
        .paddtop{
            padding-top: 10px;
        }
        .search-a{
            float: left;
            border: 1px solid #ffc900;
            width: 90px;
            height: 35px;
            background-color: #ffc900;
            text-align: center;
            line-height: 35px;
            margin-top: 15px;
        }
        .search-input{
            float: left;
            border: 2px solid #ffc900;
            width: 300px;
            height:35px;
            padding-left: 5px;
            margin-top: 15px;
        }
        .jx{
            border-bottom: 2px solid #ffc900;
            padding: 5px;
        }
        .company{
            height: 40px;
            background-color: #ffc900;
            text-align: center;
            line-height: 40px;
        }
    </style>

</head>
<body>
<!--1、页眉部分-->
    <header class="container-fluid">
        <div class="row">
            <img src="../img/top_banner.jpg" alt="" class="img-responsive">
        </div>

        <div class="row paddtop">
            <div class="col-md-3">
                <img src="../img/logo.jpg" alt="" class="img-responsive">
            </div>
            <div class="col-md-5">
                <input placeholder="请输入线路名称" class="search-input">
                <a href="#" class="search-a">搜索</a>
            </div>
            <div class="col-md-3">
                <img src="../img/hotel_tel.png" alt="" class="img-responsive">
            </div>
        </div>
        <!-- 导航栏-->
        <div class="row">
            <nav class="navbar navbar-default">
                <div class="container-fluid">
                    <!-- Brand and toggle get grouped for better mobile display -->
                    <div class="navbar-header">
                        <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
                            <span class="sr-only">Toggle navigation</span>
                            <span class="icon-bar"></span>
                            <span class="icon-bar"></span>
                            <span class="icon-bar"></span>
                        </button>
                        <a class="navbar-brand" href="#">Brand</a>
                    </div>

                    <!-- Collect the nav links, forms, and other content for toggling -->
                    <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
                        <ul class="nav navbar-nav">
                            <li class="active"><a href="#">Link <span class="sr-only">(current)</span></a></li>
                            <li><a href="#">Link</a></li>
                            <li><a href="#">Link</a></li> <li><a href="#">Link</a></li>
                            <li><a href="#">Link</a></li> <li><a href="#">Link</a></li>
                        </ul>
                    </div><!-- /.navbar-collapse -->
                </div><!-- /.container-fluid -->
            </nav>
        </div>
        <!--        轮播图-->
        <div class="row">
            <div id="carousel-example-generic" class="carousel slide" data-ride="carousel">
                <!-- Indicators -->
                <ol class="carousel-indicators">
                    <li data-target="#carousel-example-generic" data-slide-to="0" class="active"></li>
                    <li data-target="#carousel-example-generic" data-slide-to="1"></li>
                    <li data-target="#carousel-example-generic" data-slide-to="2"></li>
                </ol>

                <!-- Wrapper for slides -->
                <div class="carousel-inner" role="listbox">
                    <div class="item active">
                        <img src="../img/banner_1.jpg" alt="...">
                        <div class="carousel-caption">

                        </div>
                    </div>
                    <div class="item">
                        <img src="../img/banner_2.jpg" alt="...">
                        <div class="carousel-caption">

                        </div>
                    </div>
                    <div class="item">
                        <img src="../img/banner_3.jpg" alt="...">
                        <div class="carousel-caption">

                        </div>
                    </div>

                </div>

                <!-- Controls -->
                <a class="left carousel-control" href="#carousel-example-generic" role="button" data-slide="prev">
                    <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
                    <span class="sr-only">Previous</span>
                </a>
                <a class="right carousel-control" href="#carousel-example-generic" role="button" data-slide="next">
                    <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
                    <span class="sr-only">Next</span>
                </a>
            </div>
        </div>

    </header>
<!--2、主体部分-->
    <div class="container">
        <div class="row jx">
            <img src="../img/icon_5.jpg" alt="">
            <span>黑马精选</span>
        </div>
        <div class="row paddtop">
            <div class="col-md-3">
                <div class="thumbnail">
                    <img src="../img/jiangxuan_3.jpg" alt="">
                    <p>上海飞三亚</p>
                    <font color="red">￥ 699</font>
                </div>
            </div>
            <div class="col-md-3">
                <div class="thumbnail">
                    <img src="../img/jiangxuan_3.jpg" alt="">
                    <p>上海飞三亚</p>
                    <font color="red">￥ 699</font>
                </div>
            </div>
            <div class="col-md-3">
                <div class="thumbnail">
                    <img src="../img/jiangxuan_3.jpg" alt="">
                    <p>上海飞三亚</p>
                    <font color="red">￥ 699</font>
                </div>
            </div>
            <div class="col-md-3">
                <div class="thumbnail">
                    <img src="../img/jiangxuan_3.jpg" alt="">
                    <p>上海飞三亚</p>
                    <font color="red">￥ 699</font>
                </div>
            </div>
        </div>
        <div class="row jx">
            <img src="../img/icon_6.jpg" alt="">
            <span>国内游</span>
        </div>
        <div class="row paddtop">
            <div class="col-md-4">
                <img src="../img/guonei_1.jpg" alt="">
            </div>
            <div class="col-md-8">
                <div class="row">
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="../img/jiangxuan_3.jpg" alt="">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">￥ 699</font>
                        </div>
                    </div>
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="../img/jiangxuan_3.jpg" alt="">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">￥ 699</font>
                        </div>
                    </div>
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="../img/jiangxuan_3.jpg" alt="">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">￥ 699</font>
                        </div>
                    </div>
                </div>
                <div class="row">
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="../img/jiangxuan_3.jpg" alt="">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">￥ 699</font>
                        </div>
                    </div>
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="../img/jiangxuan_3.jpg" alt="">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">￥ 699</font>
                        </div>
                    </div>
                    <div class="col-md-4">
                        <div class="thumbnail">
                            <img src="../img/jiangxuan_3.jpg" alt="">
                            <p>上海直飞三亚5天4晚自由行(春节预售+亲子/蜜月/休闲游首选+豪华酒店任选+接送机)</p>
                            <font color="red">￥ 699</font>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
<!--3、页脚部分-->
    <footer class="container-fluid">

    <div class="row">
        <img src="img/footer_service.png" class="img-responsive">
    </div>
    <div class="row company">
        江苏传智播客教育科技股份有限公司 版权所有Copyright 2006-2018, All Rights Reserved 苏ICP备16007882
    </div>

    </footer>
</body>
</html>
```


​	


​	

# Xml

	1. XML
		1. 概念
		2. 语法
		3. 解析







## 概念：

概念：Extensible Markup Language 可扩展标记语言

* 可扩展：标签都是自定义的。 <user>  <student>

* 功能
	* 存储数据
		1. 配置文件
		2. 在网络中传输
* xml与html的区别
	1. xml标签都是自定义的，html标签是预定义。
	2. xml的语法严格，html语法松散
	3. xml是存储数据的，html是展示数据

* w3c:万维网联盟



## 语法


### 基本语法：

1. xml文档的后缀名 .xml

2. xml第一行必须定义为文档声明

3. xml文档中有且仅有一个根标签

4. 属性值必须使用引号(单双都可)引起来

5. 标签必须正确关闭

6. xml标签名称区分大小写

   

### 快速入门：

```xml
<?xml version='1.0' ?>
<users>
	<user id='1'>
		<name>zhangsan</name>
		<age>23</age>
		<gender>male</gender>
		<br/>
	</user>
	

<user id='2'>
	<name>lisi</name>
	<age>24</age>
	<gender>female</gender>
</user>

</users>
```



### 组成部分：

#### 1.文档声明

1. 格式：<?xml 属性列表 ?>
2. 属性列表：
	* version：版本号，必须的属性
	* encoding：编码方式。告知解析引擎当前文档使用的字符集，默认值：ISO-8859-1
	* standalone：是否独立
		* 取值：
			* yes：不依赖其他文件
			* no：依赖其他文件



#### 2.指令(了解)：结合css的

```xml
<?xml-stylesheet type="text/css" href="a.css" ?>
```





#### 3.标签：标签名称自定义的

* 规则：
	* 名称可以包含字母、数字以及其他的字符 
	* 名称不能以数字或者标点符号开始 
	* 名称不能以字母 xml（或者 XML、Xml 等等）开始 
	* 名称不能包含空格 



#### 4.属性：

​      id属性值唯一



#### 5.文本：

* CDATA区：在该区域中的数据会被原样展示
	* 格式：  <![CDATA[ 数据 ]]>







### 约束

![image-20201216165331296](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201216165331296.png)

约束：规定xml文档的书写规则
* 作为框架的使用者(程序员)： 

  1.能够在xml中引入约束文档

  2能够简单的读懂约束文档.



分类：

1.DTD:一种简单的约束技术

2.Schema:一种复杂的约束技术



#### DTD：

​	引入dtd文档到xml文档中

		*  内部dtd：将约束规则定义在xml文档中

<!DOCTYPE 根标签名 [约束]>

		*  外部dtd：将约束的规则定义在外部的dtd文件中

​			 * 本地：<!DOCTYPE 根标签名 SYSTEM "dtd文件的位置">

​			  * 网络：<!DOCTYPE 根标签名 PUBLIC "dtd文件名字" "dtd文件的位置URL">



#### Schema:

引入：
1.填写xml文档的根元素
2.引入xsi前缀.  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
3.引入xsd文件命名空间.  xsi:schemaLocation="http://www.itcast.cn/xml  student.xsd"
4.为每一个xsd约束声明一个前缀,作为标识  xmlns="http://www.itcast.cn/xml" 

```
<students   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns="http://www.itcast.cn/xml"
	xsi:schemaLocation="http://www.itcast.cn/xml  student.xsd">
```





​	







### 解析

解析：操作xml文档，将文档中的数据读取到内存中
* 操作xml文档
	1. 解析(读取)：将文档中的数据读取到内存中
	2. 写入：将内存中的数据保存到xml文档中。持久化的存储

* 解析xml的方式：
	1. DOM：**将标记语言文档一次性加载进内存，在内存中形成一颗dom树**(面试可能考)
		* 优点：操作方便，可以对文档进行CRUD的所有操作
		* 缺点：占内存
	2. SAX：**逐行读取，基于事件驱动的。**
		* 优点：不占内存。
		* 缺点：只能读取，不能增删改


​		

* xml常见的解析器：

   ​	1.JAXP：sun公司提供的解析器，支持dom和sax两种思想

   ​	2.DOM4J：一款非常优秀的解析器

   ​	3.Jsoup：jsoup 是一款Java 的HTML解析器，可直接解析某个URL地址、HTML文本内容。它提供了一套非常省力的API，可通过DOM，CSS以及类似于jQuery的操作方法来取出和操作数据。

   ​	4.PULL：Android操作系统内置的解析器，sax方式的。



### Jsoup解析器（适合爬虫）

Jsoup：jsoup 是一款Java 的HTML解析器，可直接解析某个URL地址、HTML文本内容。它提供了一套非常省力的API，可通过DOM，CSS以及类似于jQuery的操作方法来取出和操作数据。

快速入门：
* 步骤：
   1. 导入jar包
   2. 获取Document对象
   3. 获取对应的标签Element对象
   4. 获取数据



```Xml
public class jsoupDemo1 {
    public static void main(String[] args) throws IOException {
        //2 根据xml文档获取document对象
        //2.1 获取路径
        // String path = jsoupDemo1.class.getClassLoader().getResource("student.xml").getPath();

        //2.2 解析xml文档，加载进内存，获取DOM树---->Document
        String path = "D:\\java学习\\java练习\\day32_Xml\\src\\itcast\\xml\\schema\\student.xml";
        Document document = Jsoup.parse(new File(path), "utf-8");
        System.out.println(path);
        //3 获取元素对象
        Elements elements = document.getElementsByTag("name");
        System.out.println(elements.size());
        Element element = elements.get(0);
        String name = element.text();
        System.out.println(name);

    }
}

```





### 对象的使用



![image-20201217104429717](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201217104429717.png)



#### Jsoup

Jsoup：工具类，可以解析html或xml文档，返回Document

parse：解析html或xml文档，返回Document
* parse(File in, String charsetName)：解析xml或html文件的。

* parse(String html)：解析xml或html字符串

* parse(URL url, int timeoutMillis)：通过网络路径获取指定的html或xml的文档对象

```xml
public static void main(String[] args) throws IOException {
        // 第一种解析 .xml文件 parse(File in, String charsetName)：解析xml或html文件的。
        // 最常用
        String path = "D:\\java学习\\java练习\\day32_Xml\\src\\itcast\\xml\\schema\\student.xml";
        Document document = Jsoup.parse(new File(path), "utf-8");
        System.out.println(path);
        //3 获取元素对象
        Elements elements = document.getElementsByTag("name");
        System.out.println(elements.size());
        Element element = elements.get(0);
        String name = element.text();
        System.out.println(name);
        // 第二种 解析xml 字符串 parse(String html)：解析xml或html字符串
        String str = "<?xml version=\"1.0\" encoding=\"UTF-8\" ?>\n" +
                "\n" +
                " <students >\n" +
                " \t<student number=\"heima_0001\">\n" +
                " \t\t<name>tom</name>\n" +
                " \t\t<age>18</age>\n" +
                " \t\t<sex>male</sex>\n" +
                " \t</student>\n" +
                "\t\t \n" +
                " </students>";
        Document document02 = Jsoup.parse(str);
        System.out.println(document02);
        //第三种  parse(URL url, int timeoutMillis)：通过网络路径获取指定的html或xml的文档对象
        URL url = new URL("https://www.bilibili.com/");
        Document document03 = Jsoup.parse(url, 1000);
        System.out.println(document03);
    }
```





#### Document

2.Document：文档对象。代表内存中的dom树

* 获取Element对象
	* getElementById(String id)：根据id属性值获取唯一的element对象
	* getElementsByTag(String tagName)：根据标签名称获取元素对象集合
	* getElementsByAttribute(String key)：根据属性名称获取元素对象集合
	* getElementsByAttributeValue(String key, String value)：根据对应的属性名和属性值获取元素对象集合

```xml
public static void main(String[] args) throws IOException {
        String path = "D:\\java学习\\java练习\\day32_Xml\\src\\itcast\\xml\\schema\\student.xml";
        Document document = Jsoup.parse(new File(path), "utf-8");
        // 1.通过标签获取
        Elements student = document.getElementsByTag("student");
        System.out.println(student);
        System.out.println("------------------------");
        // 2.通过id获取属性
        Elements attribute = document.getElementsByAttribute("id");
        System.out.println(attribute);
        System.out.println("------------------------");
        // 3.根据对应的属性名和属性值获取元素对象集合
        Elements elementsByAttributeValue = document.getElementsByAttributeValue("number", "heima_0001");
        System.out.println(elementsByAttributeValue);
        System.out.println("------------------------");
        // 4.通过对于的id值来获取
        Element elementById = document.getElementById("itcast");
        System.out.println(elementById);

    }
```











#### Elements

3. Elements：元素Element对象的集合。可以当做 ArrayList<Element>来使用



#### Element

4. Element：元素对象

     1.获取子元素对象

     * getElementById(String id)：根据id属性值获取唯一的element对象

     * getElementsByTag(String tagName)：根据标签名称获取元素对象集合

     * getElementsByAttribute(String key)：根据属性名称获取元素对象集合

     * getElementsByAttributeValue(String key, String value)：根据对应的属性名和属性值获取元素对象集合 

     2.获取属性值.

     * String attr(String key)：根据属性名称获取属性值（元素名.attr）

     3.获取文本内容

     * String text():获取纯文本内容
     * String html():获取标签体的所有内容(包括字标签的字符串内容)

```xml
public static void main(String[] args) throws IOException {
        String path = "D:\\java学习\\java练习\\day32_Xml\\src\\itcast\\xml\\schema\\student.xml";
        Document document = Jsoup.parse(new File(path), "utf-8");
        // 1.通过标签获取
        Elements student = document.getElementsByTag("student");
        Element element = student.get(0);
        String attr = element.attr("number");
        System.out.println(attr);

        Elements name = element.getElementsByTag("name");
        String text = name.text();
        System.out.println(text);
    }
```









#### Node

5. Node：节点对象
	* 是Document和Element的父类(定义了一些公用的方法)





### 快捷查询方式：

![image-20201217104845240](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201217104845240.png)

#### 1.selector:选择器

selector:选择器
* 使用的方法：Elements	select(String cssQuery)
	* 语法：参考Selector类中定义的语法

主要查api

```xml
public static void main(String[] args) throws IOException {
        String path = "D:\\java学习\\java练习\\day32_Xml\\src\\itcast\\xml\\schema\\student.xml";
        Document document = Jsoup.parse(new File(path), "utf-8");

        Elements select = document.select("student[number=\"heima_0001\"]");
        System.out.println(select);
        System.out.println("-----------------------------------");
        Elements select1 = document.select("student[number=\"heima_0001\"] > age");
        System.out.println(select1);
    }
```







#### 2.XPath

XPath：XPath即为XML路径语言，它是一种用来确定XML（标准通用标记语言的子集）文档中某部分位置的语言
* 使用Jsoup的Xpath需要额外导入jar包。
* 查询w3cshool参考手册，使用xpath的语法完成查询



​			

```xml
public static void main(String[] args) throws IOException, XpathSyntaxErrorException {
        String path = "D:\\java学习\\java练习\\day32_Xml\\src\\itcast\\xml\\schema\\student.xml";
        Document document = Jsoup.parse(new File(path), "utf-8");

        JXDocument jxDocument = new JXDocument(document);

        // 1 查询所有的student标签
        List<JXNode> jxNodes = jxDocument.selN("//student");
        for (JXNode jxNode : jxNodes) {
            System.out.println(jxNode);
        }
        System.out.println("---------------------------");

        // 2 查询student下所有name标签
        List<JXNode> jxNodes2 = jxDocument.selN("//student/name");
        for (JXNode jxNode : jxNodes2) {
            System.out.println(jxNode);
        }
        System.out.println("---------------------------");

        // 3 查询student标签下带有id属性的name标签
        List<JXNode> jxNodes3 = jxDocument.selN("//student/name[@id]");
        for (JXNode jxNode : jxNodes3) {
            System.out.println(jxNode);
        }
        System.out.println("---------------------------");

        List<JXNode> jxNodes4 = jxDocument.selN("//student/name[@id='itcast']");
        for (JXNode jxNode : jxNodes4) {
            System.out.println(jxNode);
        }
        System.out.println("---------------------------");

    }
```




​	

# Servlet入门学习

	1. web相关概念回顾
	2. web服务器软件：Tomcat
	3. Servlet入门学习



## web相关概念回顾

1. 软件架构
	1. C/S：客户端/服务器端
	2. B/S：浏览器/服务器端

2. 资源分类
	1. 静态资源：所有用户访问后，得到的结果都是一样的，称为静态资源.静态资源可以直接被浏览器解析
		* 如： html,css,JavaScript
	2. 动态资源:每个用户访问相同资源后，得到的结果可能不一样。称为动态资源。动态资源被访问后，需要先转换为静态资源，在返回给浏览器
		* 如：servlet/jsp,php,asp....

3. 网络通信三要素
	1. IP：电子设备(计算机)在网络中的唯一标识。
	2. 端口：应用程序在计算机中的唯一标识。 0~65536
	3. 传输协议：规定了数据传输的规则
		1. 基础协议：
			1. tcp:安全协议，三次握手。 速度稍慢
			2. udp：不安全协议。 速度快



![image-20201217143056607](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201217143056607.png)









## web服务器软件：

* 服务器：安装了服务器软件的计算机
* 服务器软件：接收用户的请求，处理请求，做出响应
* web服务器软件：接收用户的请求，处理请求，做出响应。
	* 在web服务器软件中，可以部署web项目，让用户通过浏览器来访问这些项目
	* web容器



* 常见的java相关的web服务器软件：
	* webLogic：oracle公司，大型的JavaEE服务器，支持所有的JavaEE规范，收费的。
	* webSphere：IBM公司，大型的JavaEE服务器，支持所有的JavaEE规范，收费的。
	* JBOSS：JBOSS公司的，大型的JavaEE服务器，支持所有的JavaEE规范，收费的。
	* Tomcat：Apache基金组织，中小型的JavaEE服务器，仅仅支持少量的JavaEE规范servlet/jsp。开源的，免费的。



* JavaEE：Java语言在企业级开发中使用的技术规范的总和，一共规定了13项大的规范







## Tomcat

目录结构：

![image-20201217145203738](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201217145203738.png)



![image-20201219122943097](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201219122943097.png)



![image-20201219122818468](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201219122818468.png)



Tomcat：web服务器软件
1. 下载：http://tomcat.apache.org/

2. 安装：解压压缩包即可。
	
	* 注意：安装目录建议不要有中文和空格
	
3. 卸载：删除目录就行了

4. 启动：
	* bin/startup.bat ,双击运行该文件即可
	* 访问：浏览器输入：http://localhost:8080 回车访问自己（或者http://127.0.0.1:8080）
					  http://别人的ip:8080 访问别人（cmd下：ipconfig查询ip地址）
	
	* 可能遇到的问题：
		1. 黑窗口一闪而过：
			* 原因： 没有正确配置JAVA_HOME环境变量
			* 解决方案：正确配置JAVA_HOME环境变量

		2. 启动报错：
			1. 暴力：找到占用的端口号，并且找到对应的进程，杀死该进程
				
				* netstat -ano
			2. 温柔：修改自身的端口号
				* conf/server.xml
	     	* <Connector port="8888" protocol="HTTP/1.1"
	               connectionTimeout="20000"
			          redirectPort="8445" />
				* 一般会将tomcat的默认端口号修改为80。80端口号是http协议的默认端口号。
					
					* 好处：在访问时，就不用输入端口号
					
					
	
5. 关闭：
	1. 正常关闭：
		* bin/shutdown.bat
		* ctrl+c
	2. 强制关闭：
		
		* 点击启动窗口的×
		
		
	
6. 配置:
  * 部署项目的方式：
  	1. 直接将项目放到webapps目录下即可。
  		* /hello：项目的访问路径-->虚拟目录

  		![image-20201217155353335](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201217155353335.png)

  		* 简化部署：将项目打成一个war包，再将war包放置到webapps目录下。
        			* war包会自动解压缩

  	2. 配置conf/server.xml文件



  		* docBase:项目存放的路径
  	* path：虚拟目录

  	3. **在conf\Catalina\localhost创建任意名称的xml文件。在文件中编写**(推荐)

    	  <Context docBase="D:\hello" />

  	  ![image-20201217160032030](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201217160032030.png)
  	
  	  * 虚拟目录：xml文件的名称








  * 静态项目和动态项目：
  	* 目录结构
        		* java动态项目的目录结构：

    			-- 项目的根目录
    				-- WEB-INF目录：
    					-- web.xml：web项目的核心配置文件
    					-- classes目录：放置字节码文件的目录
    					-- lib目录：放置依赖的jar包
  *  将Tomcat集成到IDEA中，并且创建JavaEE的项目，部署项目。













## Servlet：  server applet（核心）



![image-20201217212152204](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201217212152204.png)



### 1.概念

* 概念：运行在服务器端的小程序
	* Servlet就是一个接口，定义了Java类被浏览器访问到(tomcat识别)的规则。
	* 将来我们自定义一个类，实现Servlet接口，复写方法。



### 2.快速入门

* 快速入门：
	1. 创建JavaEE项目
	2. 定义一个类，实现Servlet接口
		
		* public class ServletDemo1 implements Servlet
	3. 实现接口中的抽象方法
	4. 配置Servlet
		 在web.xml中配置：
	    <!--配置Servlet -->
	    <servlet>
	        <servlet-name>demo1</servlet-name>
	        <servlet-class>cn.itcast.web.servlet.ServletDemo1</servlet-class>
	    </servlet>
	
	    <servlet-mapping>
	        <servlet-name>demo1</servlet-name>
	        <url-pattern>/demo1</url-pattern>
	    </servlet-mapping>



### 3.执行原理

* 执行原理：
	1. 当服务器接受到客户端浏览器的请求后，会解析请求URL路径，获取访问的Servlet的资源路径
	2. 查找web.xml文件，是否有对应的<url-pattern>标签体内容。
	3. 如果有，则在找到对应的<servlet-class>全类名
	4. tomcat会将字节码文件加载进内存，并且创建其对象
	5. 调用其方法

![image-20201218110047512](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201218110047512.png)







### 4.Servlet中的生命周期方法

Servlet中的生命周期方法：

![image-20201218121515315](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201218121515315.png)





#### init

1. 被创建：执行**init**方法，只执行**一次**
  * Servlet什么时候被创建？
    * 默认情况下，第一次被访问时，Servlet被创建
    * 可以配置执行Servlet的创建时机。
      * 在<servlet>标签下配置

        1.第一次被访问时，创建

              *  <load-on-startup>的值为负数

        2.在服务器启动时，创建

              *  <load-on-startup>的值为0或正整数

![image-20201218122704832](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201218122704832.png)







  * Servlet的init方法，只执行一次，说明一个Servlet在内存中只存在一个对象，Servlet是单例的
* 多个用户同时访问时，可能存在**线程安全**问题。
    		* 解决：尽量不要在Servlet中定义成员变量。即使定义了成员变量，也不要对修改值



#### **service**

2. 提供服务：执行**service**方法，执行**多次**

     ![image-20201218121545565](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201218121545565.png)

     * 每次访问Servlet时，Service方法都会被调用一次。



#### **destroy**

2. 被销毁：执行**destroy**方法，只执行**一次**

     ![image-20201218121615534](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201218121615534.png)

     * Servlet被销毁时执行。服务器关闭时，Servlet被销毁
        		* 只有服务器正常关闭时，才会执行destroy方法。
           		* destroy方法在Servlet被销毁之前执行，一般用于释放资源



​		4.getServletConfig （了解）

![image-20201218122342526](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201218122342526.png)



​		5.getServletInfo()(了解)

​			![image-20201218122432790](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201218122432790.png)







### 5.Servlet3.0 注解配置

* Servlet3.0：
	* 好处：
		* 支持注解配置。可以不需要web.xml了。

	* 步骤：
		1. 创建JavaEE项目，选择Servlet的版本3.0以上，可以不创建web.xml
		2. 定义一个类，实现Servlet接口
		3. 复写方法
		4. 在类上使用@WebServlet注解，进行配置
			* @WebServlet("资源路径")



注解写法

（1）

```java
@WebServlet(urlPatterns = "/demo1")
```

（2）

```java
@WebServlet(value = "/demo1")
```

（3）

```
@WebServlet("/demo1")
```




				@Target({ElementType.TYPE})
				@Retention(RetentionPolicy.RUNTIME)
				@Documented
				public @interface WebServlet {
				    String name() default "";//相当于<Servlet-name>
				
				    String[] value() default {};//代表urlPatterns()属性配置
				
				    String[] urlPatterns() default {};//相当于<url-pattern>
				
				    int loadOnStartup() default -1;//相当于<load-on-startup>
				
				    WebInitParam[] initParams() default {};
				
				    boolean asyncSupported() default false;
				
				    String smallIcon() default "";
				
				    String largeIcon() default "";
				
				    String description() default "";
				
				    String displayName() default "";
				}





## IDEA与tomcat的相关配置

1. IDEA会为每一个tomcat部署的项目单独建立一份配置文件
	* 查看控制台的log：Using CATALINA_BASE:   "C:\Users\fqy\.IntelliJIdea2018.1\system\tomcat\_itcast"
2. 工作空间项目    和     tomcat部署的web项目
	* tomcat真正访问的是“tomcat部署的web项目”，"tomcat部署的web项目"对应着"工作空间项目" 的web目录下的所有资源
	* WEB-INF目录下的资源不能被浏览器直接访问。
3. 断点调试：使用"小虫子"启动 dubug 启动













# Servlet&HTTP&Request

```java
1. Servlet
2. HTTP协议
3. Request



request.setCharacterEncoding("utf-8");
response.setContentType("text/html;charset=utf-8");
response.setContentType("application/json;charset=utf-8");
```



## Servlet：

```java
1. 概念
2. 步骤
3. 执行原理
4. 生命周期
5. Servlet3.0 注解配置
```



### 6.Servlet的体系结构	

6. Servlet的体系结构	
	Servlet -- 接口
		|
	GenericServlet -- 抽象类
		|
	HttpServlet  -- 抽象类

	* GenericServlet：将Servlet接口中其他的方法做了默认空实现，只将service()方法作为抽象
		

![image-20201218161806327](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201218161806327.png)
		
		* 将来定义Servlet类时，可以继承GenericServlet，实现service()方法即可


​	
​	
​	
​	
​	* **HttpServlet**：对http协议的一种封装，简化操作<font color= "red">**(真正用的！！！！！！！不需要判断get和post)**</font>
​		1. 定义类继承HttpServlet
​		2. 复写doGet/doPost方法

![image-20201218162027303](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201218162027303.png)

```java
@WebServlet("/demo3")
public class Dome03 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("doGet");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("doPost");
    }
}
```







### 7.Servlet相关配置

7. Servlet相关配置
	1. urlpartten:Servlet访问路径
		1. 一个Servlet可以定义多个访问路径 ： @WebServlet({"/d4","/dd4","/ddd4"})
		2. 路径定义规则：
			1. /xxx：路径匹配
			2. /xxx/xxx:多层路径，目录结构
			3. /xxx/*  : xxx下的所有均可
			4. *.do：扩展名匹配（网址中需要这样“demo.do”）













## HTTP：

![image-20201218191226751](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201218191226751.png)

### 概念

概念：Hyper Text Transfer Protocol 超文本传输协议
* 传输协议：定义了，客户端和服务器端通信时，发送数据的格式
* 特点：
	1. 基于TCP/IP的高级协议
	2. 默认端口号:80
	3. 基于请求/响应模型的:一次请求对应一次响应
	4. 无状态的：每次请求之间相互独立，不能交互数据
* 历史版本：
    * 1.0：每一次请求响应都会建立新的连接
    * 1.1：复用连接





### 请求消息数据格式（ServletRequest）

```
请求行
请求头
请求空行
请求体(正文)
```

请求消息数据格式

1. 请求行
	请求方式    请求url     请求协议/版本
	
```
	GET /login.html	HTTP/1.1
```


​	
​	* 请求方式：
​		* HTTP协议有7中请求方式，常用的有2种
​			* GET：
​				1. 请求参数在请求行中，在url后。
​				2. 请求的url长度有限制的
​				3. 不太安全
​			* POST：
​				1. 请求参数在请求体中
​				2. 请求的url长度没有限制的
​				3. 相对安全

2. 请求头：客户端浏览器告诉服务器一些信息
	
	```
	请求头名称: 请求头值
	```

	
	* 常见的请求头：
		
		1. User-Agent：浏览器告诉服务器，我访问你使用的浏览器版本信息
		
	* 可以在服务器端获取该头的信息，解决浏览器的兼容性问题
			
		2. Referer：http://localhost/login.html
			* 告诉服务器，我(当前请求)从哪里来？
				* 作用：
					1. 防盗链：
					2. 统计工作：
			
			（什么是防盗链：）
	

![image-20201219121912374](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201219121912374.png)





2. 请求空行
    空行，就是用于分割POST请求的请求头，和请求体的。

3. 请求体(正文)：

  * 封装POST请求消息的请求参数的



```java
	* 字符串格式：
		POST /login.html	HTTP/1.1
		Host: localhost
		User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; rv:60.0) Gecko/20100101 Firefox/60.0
		Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
		Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
		Accept-Encoding: gzip, deflate
		Referer: http://localhost/login.html
		Connection: keep-alive
		Upgrade-Insecure-Requests: 1
		
		username=zhangsan	
```


	* 响应消息数据格式







## Request：

### 1.request对象和response对象的原理

request对象和response对象的原理
1. request和response对象是由服务器创建的。我们来使用它们
2. request对象是来获取请求消息，response对象是来设置响应消息



![image-20201219124525022](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201219124525022.png)





### 2.request对象继承体系结构：	

ServletRequest		--	接口
	|	继承
HttpServletRequest	-- 子接口
	|	实现
org.apache.catalina.connector.RequestFacade 类(tomcat)





### 3.request功能：

#### 1.获取请求消息数据

##### (1)获取请求行数据

* GET /day14/demo1?name=zhangsan HTTP/1.1
* 方法：
  1. 获取请求方式 ：GET

    ```
    String getMethod()  
    ```

    <font color = "red"></font>

  2. (*)<font color = "red">获取虚拟目录 </font>：/day14

    ```
    String getContextPath()
    ```

    

  3. 获取Servlet路径: /demo1

    ```
    String getServletPath()
    ```

    

  4. 获取get方式请求参数：name=zhangsan

    ```
    String getQueryString()
    ```

    

  5. (*)<font color = "red">获取请求URI</font>：/day14/demo1
    ```
    String getRequestURI():		/day14/demo1
    
    StringBuffer getRequestURL()  :http://localhost/day14/demo1
    
    URL:统一资源定位符 ： http://localhost/day14/demo1	中华人民共和国
    
    URI：统一资源标识符 : /day14/demo1			共和国
    ```

    

  6. 获取协议及版本：HTTP/1.1

    ```
    String getProtocol()
    ```

    

  7. 获取客户机的IP地址：

    ```
    String getRemoteAddr()
    ```

    

##### (2)获取请求头数据

方法：
```
(*)
String getHeader(String name):通过请求头的名称获取请求头的值

Enumeration<String> getHeaderNames():获取所有的请求头名称
```



例子

```java
protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        String agent = request.getHeader("user-agent");
        if(agent.contains("chrome")) {
            System.out.println("谷歌来啦");
        }else if(agent.contains("Firefox")) {
            System.out.println("火狐来啦");
        }
		String refer = request.getHeader("refer");
        System.out.println(refer);
    }
```





##### (3)获取请求体数据:

* 请求体：只有POST请求方式，才有请求体，在请求体中封装了POST请求的请求参数
* 步骤：
  1. 获取流对象
    ```java
    BufferedReader getReader()：获取字符输入流，只能操作字符数据
    ```

    ```java
    ServletInputStream getInputStream()：获取字节输入流，可以操作所有类型数据
    ```

    

    * 在文件上传知识点后讲解

  2. 再从流对象中拿数据









### 2.其他功能：

#### (1)获取请求参数通用方式

获取请求参数通用方式：不论get还是post请求方式都可以使用下列方法来获取请求参数

1. String getParameter(String name):根据参数名称获取参数值    username=zs&password=123
2. String[] getParameterValues(String name):根据参数名称获取参数值的数组  hobby=xx&hobby=game
3. Enumeration<String> getParameterNames():获取所有请求的参数名称
4. Map<String,String[]> getParameterMap():获取所有参数的map集合
  * 中文乱码问题：
  	* get方式：tomcat 8 已经将get方式乱码问题解决了
  	* post方式：会乱码
        		* 解决：在获取参数前，设置request的编码request.setCharacterEncoding("utf-8");

![image-20201221164847117](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201221164847117.png)

​		

​		

#### (2)请求转发

![image-20201221165257967](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201221165257967.png)



![image-20210125095438642](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210125095438642.png)

请求转发：一种在服务器内部的资源跳转方式

1.步骤：

​	1.通过request对象获取请求转发器对象：

```java
RequestDispatcher getRequestDispatcher(String path)
```

​	2.使用RequestDispatcher对象来进行转发：

```java
forward(ServletRequest request, ServletResponse response
```



一般也可以链式编程

```
request.getRequestDispatcher(path).forward(request, response)
```



2.<font color="red">特点 </font>：

1. 浏览器地址栏路径不发生变化
2. 只能转发到当前服务器内部资源中。
3. 转发是一次请求

​	

### 转发的特点

1. 地址栏不发生变化，显示的是上一个页面的地址
2. 请求次数：只有1次请求
3. 根目录：http://localhost:8080/项目地址/，包含了项目的访问地址
4. 请求域中数据不会丢失

​				



#### (3)共享数据：

![image-20201221170930271](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201221170930271.png)

	* 域对象：一个有作用范围的对象，可以在范围内共享数据
	* request域：代表一次请求的范围，一般用于请求转发的多个资源中共享数据
	
	* 方法：
		1. void setAttribute(String name,Object obj):存储数据
		2. Object getAttitude(String name):通过键获取值
		3. void removeAttribute(String name):通过键移除键值对



#### (4)获取ServletContext：

		* ServletContext getServletContext()

ServletContext官方叫servlet上下文。服务器会为每一个工程创建一个对象，这个对象就是ServletContext对象。这个对象全局唯一，而且工程内部的所有servlet都共享这个对象。所以叫全局应用程序共享对象。

![image-20201225091148738](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201225091148738.png)



## 案例：用户登录

![image-20201221195807443](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201221195807443.png)



	* 用户登录案例需求：
		1.编写login.html登录页面
			username & password 两个输入框
		2.使用Druid数据库连接池技术,操作mysql，day14数据库中user表
		3.使用JdbcTemplate技术封装JDBC
		4.登录成功跳转到SuccessServlet展示：登录成功！用户名,欢迎您
		5.登录失败跳转到FailServlet展示：登录失败，用户名或密码错误


	* 分析
	
	* 开发步骤
		1. 创建项目，导入html页面，配置文件，jar包
		2. 创建数据库环境
			CREATE DATABASE day14;
			USE day14;
			CREATE TABLE USER(
			
				id INT PRIMARY KEY AUTO_INCREMENT,
				username VARCHAR(32) UNIQUE NOT NULL,
				PASSWORD VARCHAR(32) NOT NULL
			);
	
		3. 创建包cn.itcast.domain,创建类User
			package cn.itcast.domain;
			/**
			 * 用户的实体类
			 */
			public class User {
			
			    private int id;
			    private String username;
			    private String password;


​			

			    public int getId() {
			        return id;
			    }
			
			    public void setId(int id) {
			        this.id = id;
			    }
			
			    public String getUsername() {
			        return username;
			    }
			
			    public void setUsername(String username) {
			        this.username = username;
			    }
			
			    public String getPassword() {
			        return password;
			    }
			
			    public void setPassword(String password) {
			        this.password = password;
			    }
			
			    @Override
			    public String toString() {
			        return "User{" +
			                "id=" + id +
			                ", username='" + username + '\'' +
			                ", password='" + password + '\'' +
			                '}';
			    }
			}
		4. 创建包cn.itcast.util,编写工具类JDBCUtils
			package cn.itcast.util;
	
			import com.alibaba.druid.pool.DruidDataSourceFactory;
			
			import javax.sql.DataSource;
			import javax.xml.crypto.Data;
			import java.io.IOException;
			import java.io.InputStream;
			import java.sql.Connection;
			import java.sql.SQLException;
			import java.util.Properties;
			
			/**
			 * JDBC工具类 使用Durid连接池
			 */
			public class JDBCUtils {
			
			    private static DataSource ds ;
			
			    static {
			
			        try {
			            //1.加载配置文件
			            Properties pro = new Properties();
			            //使用ClassLoader加载配置文件，获取字节输入流
			            InputStream is = JDBCUtils.class.getClassLoader().getResourceAsStream("druid.properties");
			            pro.load(is);
			
			            //2.初始化连接池对象
			            ds = DruidDataSourceFactory.createDataSource(pro);
			
			        } catch (IOException e) {
			            e.printStackTrace();
			        } catch (Exception e) {
			            e.printStackTrace();
			        }
			    }
			
			    /**
			     * 获取连接池对象
			     */
			    public static DataSource getDataSource(){
			        return ds;
			    }


​			

			    /**
			     * 获取连接Connection对象
			     */
			    public static Connection getConnection() throws SQLException {
			        return  ds.getConnection();
			    }
			}
		5. 创建包cn.itcast.dao,创建类UserDao,提供login方法
			
			package cn.itcast.dao;
	
			import cn.itcast.domain.User;
			import cn.itcast.util.JDBCUtils;
			import org.springframework.dao.DataAccessException;
			import org.springframework.jdbc.core.BeanPropertyRowMapper;
			import org.springframework.jdbc.core.JdbcTemplate;
			
			/**
			 * 操作数据库中User表的类
			 */
			public class UserDao {
			
			    //声明JDBCTemplate对象共用
			    private JdbcTemplate template = new JdbcTemplate(JDBCUtils.getDataSource());
			
			    /**
			     * 登录方法
			     * @param loginUser 只有用户名和密码
			     * @return user包含用户全部数据,没有查询到，返回null
			     */
			    public User login(User loginUser){
			        try {
			            //1.编写sql
			            String sql = "select * from user where username = ? and password = ?";
			            //2.调用query方法
			            User user = template.queryForObject(sql,
			                    new BeanPropertyRowMapper<User>(User.class),
			                    loginUser.getUsername(), loginUser.getPassword());


​			

			            return user;
			        } catch (DataAccessException e) {
			            e.printStackTrace();//记录日志
			            return null;
			        }
			    }
			}
		
		6. 编写cn.itcast.web.servlet.LoginServlet类
			package cn.itcast.web.servlet;
	
			import cn.itcast.dao.UserDao;
			import cn.itcast.domain.User;
			
			import javax.servlet.ServletException;
			import javax.servlet.annotation.WebServlet;
			import javax.servlet.http.HttpServlet;
			import javax.servlet.http.HttpServletRequest;
			import javax.servlet.http.HttpServletResponse;
			import java.io.IOException;


​			

			@WebServlet("/loginServlet")
			public class LoginServlet extends HttpServlet {


​			

			    @Override
			    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
			        //1.设置编码
			        req.setCharacterEncoding("utf-8");
			        //2.获取请求参数
			        String username = req.getParameter("username");
			        String password = req.getParameter("password");
			        //3.封装user对象
			        User loginUser = new User();
			        loginUser.setUsername(username);
			        loginUser.setPassword(password);
			
			        //4.调用UserDao的login方法
			        UserDao dao = new UserDao();
			        User user = dao.login(loginUser);
			
			        //5.判断user
			        if(user == null){
			            //登录失败
			            req.getRequestDispatcher("/failServlet").forward(req,resp);
			        }else{
			            //登录成功
			            //存储数据
			            req.setAttribute("user",user);
			            //转发
			            req.getRequestDispatcher("/successServlet").forward(req,resp);
			        }
			
			    }
			
			    @Override
			    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
			        this.doGet(req,resp);
			    }
			}
	
		7. 编写FailServlet和SuccessServlet类
			@WebServlet("/successServlet")
			public class SuccessServlet extends HttpServlet {
			    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
			        //获取request域中共享的user对象
			        User user = (User) request.getAttribute("user");
			
			        if(user != null){
			            //给页面写一句话
			
			            //设置编码
			            response.setContentType("text/html;charset=utf-8");
			            //输出
			            response.getWriter().write("登录成功！"+user.getUsername()+",欢迎您");
			        }


​			

			    }		


			@WebServlet("/failServlet")
			public class FailServlet extends HttpServlet {
			    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
			        //给页面写一句话
			
			        //设置编码
			        response.setContentType("text/html;charset=utf-8");
			        //输出
			        response.getWriter().write("登录失败，用户名或密码错误");
			
			    }
			
			    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
			        this.doPost(request,response);
			    }
			}



8. login.html中form表单的action路径的写法
	* 虚拟目录+Servlet的资源路径



## BeanUtils

9. BeanUtils工具类，简化数据封装
  * 用于封装JavaBean的
  1. JavaBean：标准的Java类
  	1. 要求：
        		1. 类必须被public修饰
               
                 		2. 必须提供空参的构造器
        		3. 成员变量必须使用private修饰
       
                   		4. 提供公共setter和getter方法
  	2. 功能：封装数据
  
  2. 概念：
     			成员变量：
          			属性：setter和getter方法截取后的产物
          				例如：getUsername() --> Username--> username

     setProperty操作

     ![image-20201222170657554](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201222170657554.png)

  3. 方法：
        			1. setProperty()
                			2. getProperty()
                			3. populate(Object obj , Map map):将map集合的键值对信息，封装到对应的JavaBean对象中











# 扩展知识TCP/IP

### TCP 协议简述

TCP 提供面向有连接的通信传输，面向有连接是指在传送数据之前必须先建立连接，数据传送完成后要释放连接。

无论哪一方向另一方发送数据之前，都必须先在双方之间建立一条连接。在TCP/IP协议中，TCP协议提供可靠的连接服务，连接是通过**三次握手**进行初始化的。
同时由于TCP协议是一种面向连接的、可靠的、基于字节流的运输层通信协议，TCP是**全双工模式**，所以需要**四次挥手**关闭连接。

### TCP包首部

网络中传输的数据包由两部分组成：一部分是协议所要用到的首部，另一部分是上一层传过来的数据。首部的结构由协议的具体规范详细定义。在数据包的首部，明确标明了协议应该如何读取数据。反过来说，看到首部，也就能够了解该协议必要的信息以及所要处理的数据。包首部就像协议的脸。

所以我们在学习TCP协议之前，首先要知道TCP在网络传输中处于哪个位置，以及它的协议的规范，下面我们就看看TCP首部的网络传输起到的作用：

![网络数据传输过程](https://cooffeeli-blog.oss-cn-beijing.aliyuncs.com/TCP/msg_tcp.png)

下面的图是TCP头部的规范定义，它定义了TCP协议如何读取和解析数据：
![TCP头部](https://cooffeeli-blog.oss-cn-beijing.aliyuncs.com/TCP/TCPheader.png)

TCP首部承载这TCP协议需要的各项信息，下面我们来分析一下：

- **TCP端口号**
  TCP的连接是需要四个要素确定唯一一个连接：
  **（源IP，源端口号）+ （目地IP，目的端口号）**
  所以TCP首部预留了两个16位作为端口号的存储，而IP地址由上一层IP协议负责传递
  源端口号和目地端口各占16位两个字节，也就是端口的范围是2^16=65535
  另外1024以下是系统保留的，从1024-65535是用户使用的端口范围
- **TCP的序号和确认号**：
  **32位序号 seq**：Sequence number 缩写seq ，TCP通信过程中某一个传输方向上的字节流的每个字节的序号，通过这个来确认发送的数据**有序**，比如现在序列号为1000，发送了1000，下一个序列号就是2000。
  **32位确认号 ack**：Acknowledge number 缩写ack，TCP对上一次seq序号做出的确认号，用来响应TCP报文段，给收到的TCP报文段的序号seq加1。
- **TCP的标志位**
  每个TCP段都有一个目的，这是借助于TCP标志位选项来确定的，允许发送方或接收方指定哪些标志应该被使用，以便段被另一端正确处理。
  用的最广泛的标志是 **SYN**，**ACK** 和 **FIN**，用于建立连接，确认成功的段传输，最后终止连接。
  1. **SYN**：简写为`S`，同步标志位，用于建立会话连接，同步序列号；
  2. **ACK**： 简写为`.`，确认标志位，对已接收的数据包进行确认；
  3. **FIN**： 简写为`F`，完成标志位，表示我已经没有数据要发送了，即将关闭连接；
  4. PSH：简写为`P`，推送标志位，表示该数据包被对方接收后应立即交给上层应用，而不在缓冲区排队；
  5. RST：简写为`R`，重置标志位，用于连接复位、拒绝错误和非法的数据包；
  6. URG：简写为`U`，紧急标志位，表示数据包的紧急指针域有效，用来保证连接不被阻断，并督促中间设备尽快处理；

### TCP 三次握手建立连接

所谓三次握手(Three-way Handshake)，是指建立一个 TCP 连接时，需要客户端和服务器总共发送3个报文。

三次握手的目的是连接服务器指定端口，建立 TCP 连接，并同步连接双方的序列号和确认号，交换 TCP 窗口大小信息。在 socket 编程中，客户端执行 connect() 时。将触发三次握手。

三次握手过程的示意图如下：
![三次握手建立连接](https://cooffeeli-blog.oss-cn-beijing.aliyuncs.com/TCP/established.png)

- **第一次握手**：
  客户端将TCP报文**标志位SYN置为1**，随机产生一个序号值seq=J，保存在TCP首部的序列号(Sequence Number)字段里，指明客户端打算连接的服务器的端口，并将该数据包发送给服务器端，发送完毕后，客户端进入`SYN_SENT`状态，等待服务器端确认。
- **第二次握手**：
  服务器端收到数据包后由标志位SYN=1知道客户端请求建立连接，服务器端将TCP报文**标志位SYN和ACK都置为1**，ack=J+1，随机产生一个序号值seq=K，并将该数据包发送给客户端以确认连接请求，服务器端进入`SYN_RCVD`状态。
- **第三次握手**：
  客户端收到确认后，检查ack是否为J+1，ACK是否为1，如果正确则将标志位ACK置为1，ack=K+1，并将该数据包发送给服务器端，服务器端检查ack是否为K+1，ACK是否为1，如果正确则连接建立成功，客户端和服务器端进入`ESTABLISHED`状态，完成三次握手，随后客户端与服务器端之间可以开始传输数据了。

注意:我们上面写的ack和ACK，不是同一个概念：

- 小写的ack代表的是头部的确认号Acknowledge number， 缩写ack，是对上一个包的序号进行确认的号，ack=seq+1。
- 大写的ACK，则是我们上面说的TCP首部的标志位，用于标志的TCP包是否对上一个包进行了确认操作，如果确认了，则把ACK标志位设置成1。

下面我自己做实验，开一个HTTP服务，监听80端口，然后使用Tcpdump命令抓包，看一下TCP三次握手的过程：

```python
sudo tcpdump -n -t -S -i enp0s3  port 80 

第一次握手，标志位Flags=S
IP 10.0.2.2.51323 > 10.0.2.15.80: Flags [S], seq 84689409, win 65535, options [mss 1460], length 0
第二次握手，标志位Flags=[S.]
IP 10.0.2.15.80 > 10.0.2.2.51323: Flags [S.], seq 1893430205, ack 84689410, win 64240, options [mss 1460], length 0
第三次握手，标志位Flags=[.]
IP 10.0.2.2.51323 > 10.0.2.15.80: Flags [.], ack 1893430206, win 65535, length 0
建立连接后，客户端发送http请求 
IP 10.0.2.2.51321 > 10.0.2.15.80: Flags [P.], seq 1:753, ack 1, win 65535, length 752: HTTP: GET / HTTP/1.1
```

> tcpdump命令解析一下：
> -i : 指定抓包的网卡是enp0s3
> -n: 把域名转成IP显示
> -t: 不显示时间
> -S: 序列号使用绝对数值，不指定-S的话，序列号会使用相对的数值
> port: 指定监听端口是80
> host:指定监听的主机名

我们看下实战中TCP的三次握手过程：

- 第一次握手，客户端51323端口号向服务器端80号端口发起连接，此时标志位flags=S，即SYN=1标志，表示向服务端发起连接的请求，同时生成序列号seq=84689409
- 第二次握手，服务端标志位flags=[S.]，即SYN+ACK标志位设置为1，表示对上一个请求连接的报文进行确认，同时设置ack=seq+1=184689410，生成序列号seq=1893430205
- 第三次握手，客户端对服务端的响应进行确认，所以此时标志位是[.]即ACK=1，同时返回对上一个报文的seq的确认号，ack=1893430206

至此，三次握手完成，一个TCP连接建立完成，接下来就是双端传输数据了

#### 为什么需要三次握手？

我们假设client发出的第一个连接请求报文段并没有丢失，而是在某个网络结点长时间的滞留了，以致延误到连接释放以后的某个时间才到达server。

本来这是一个早已失效的报文段。但server收到此失效的连接请求报文段后，就误认为是client再次发出的一个新的连接请求。于是就向client发出确认报文段，同意建立连接。

假设不采用“三次握手”，那么只要server发出确认，新的连接就建立了。由于现在client并没有发出建立连接的请求，因此不会理睬server的确认，也不会向server发送数据。但server却以为新的运输连接已经建立，并一直等待client发来数据。这样，server的很多资源就白白浪费掉了。

所以，采用“三次握手”的办法可以防止上述现象发生。例如刚才那种情况，client不会向server的确认发出确认。server由于收不到确认，就知道client并没有要求建立连接。

TCP 三次握手跟现实生活中的人与人打电话是很类似的：

> 三次握手：
> “喂，你听得到吗？”
> “我听得到呀，你听得到我吗？”
> “我能听到你，今天 balabala……”

经过三次的互相确认，大家就会认为对方对听的到自己说话，并且愿意下一步沟通，否则，对话就不一定能正常下去了。

### TCP 四次挥手关闭连接

四次挥手即终止TCP连接，就是指断开一个TCP连接时，需要客户端和服务端总共发送4个包以确认连接的断开。在socket编程中，这一过程由客户端或服务端任一方执行close来触发。
由于TCP连接是全双工的，因此，每个方向都必须要单独进行关闭，这一原则是当一方完成数据发送任务后，发送一个FIN来终止这一方向的连接，收到一个FIN只是意味着这一方向上没有数据流动了，即不会再收到数据了，但是在这个TCP连接上仍然能够发送数据，直到这一方向也发送了FIN。首先进行关闭的一方将执行主动关闭，而另一方则执行被动关闭。

四次挥手过程的示意图如下：
![四次挥手关闭连接](https://cooffeeli-blog.oss-cn-beijing.aliyuncs.com/TCP/close.png)

挥手请求可以是Client端，也可以是Server端发起的，我们假设是Client端发起：

- **第一次挥手**： Client端发起挥手请求，向Server端发送标志位是FIN报文段，设置序列号seq，此时，Client端进入`FIN_WAIT_1`状态，这表示Client端没有数据要发送给Server端了。
- **第二次分手**：Server端收到了Client端发送的FIN报文段，向Client端返回一个标志位是ACK的报文段，ack设为seq加1，Client端进入`FIN_WAIT_2`状态，Server端告诉Client端，我确认并同意你的关闭请求。
- **第三次分手**： Server端向Client端发送标志位是FIN的报文段，请求关闭连接，同时Client端进入`LAST_ACK`状态。
- **第四次分手** ： Client端收到Server端发送的FIN报文段，向Server端发送标志位是ACK的报文段，然后Client端进入`TIME_WAIT`状态。Server端收到Client端的ACK报文段以后，就关闭连接。此时，Client端等待**2MSL**的时间后依然没有收到回复，则证明Server端已正常关闭，那好，Client端也可以关闭连接了。

#### 为什么连接的时候是三次握手，关闭的时候却是四次握手？

建立连接时因为当Server端收到Client端的SYN连接请求报文后，可以直接发送**SYN+ACK**报文。其中ACK报文是用来应答的，SYN报文是用来同步的。所以建立连接只需要三次握手。

由于TCP协议是一种面向连接的、可靠的、基于字节流的运输层通信协议，TCP是**全双工模式**。
这就意味着，关闭连接时，当Client端发出FIN报文段时，只是表示Client端告诉Server端数据已经发送完毕了。当Server端收到FIN报文并返回ACK报文段，表示它已经知道Client端没有数据发送了，但是Server端还是可以发送数据到Client端的，所以Server很可能并不会立即关闭SOCKET，直到Server端把数据也发送完毕。
当Server端也发送了FIN报文段时，这个时候就表示Server端也没有数据要发送了，就会告诉Client端，我也没有数据要发送了，之后彼此就会愉快的中断这次TCP连接。

#### 为什么要等待2MSL？

**MSL**：报文段最大生存时间，它是任何报文段被丢弃前在网络内的最长时间。
有以下两个原因：

- **第一点：保证TCP协议的全双工连接能够可靠关闭**：
  由于IP协议的不可靠性或者是其它网络原因，导致了Server端没有收到Client端的ACK报文，那么Server端就会在超时之后重新发送FIN，如果此时Client端的连接已经关闭处于`CLOESD`状态，那么重发的FIN就找不到对应的连接了，从而导致连接错乱，所以，Client端发送完最后的ACK不能直接进入`CLOSED`状态，而要保持`TIME_WAIT`，当再次收到FIN的收，能够保证对方收到ACK，最后正确关闭连接。
- **第二点：保证这次连接的重复数据段从网络中消失**
  如果Client端发送最后的ACK直接进入`CLOSED`状态，然后又再向Server端发起一个新连接，这时不能保证新连接的与刚关闭的连接的端口号是不同的，也就是新连接和老连接的端口号可能一样了，那么就可能出现问题：如果前一次的连接某些数据滞留在网络中，这些延迟数据在建立新连接后到达Client端，由于新老连接的端口号和IP都一样，TCP协议就认为延迟数据是属于新连接的，新连接就会接收到脏数据，这样就会导致数据包混乱。所以TCP连接需要在TIME_WAIT状态等待2倍MSL，才能保证本次连接的所有数据在网络中消失。





# Response

	1. HTTP协议：响应消息
	2. Response对象
	3. ServletContext对象



## HTTP协议：



### (1)请求消息

请求消息：客户端发送给服务器端的数据
* 数据格式：
	1. 请求行
	2. 请求头
	3. 请求空行
	4. 请求体



### (2)响应消息

响应消息：服务器端发送给客户端的数据

数据格式：
#### 响应行

1. 组成：协议/版本 响应状态码 状态码描述
2. 响应状态码：服务器告诉客户端浏览器本次请求和响应的一个状态。
	1. 状态码都是3位数字 
	2. 分类：
		1. 1xx：服务器就收客户端消息，但没有接受完成，等待一段时间后，发送1xx多状态码
		
		2. 2xx：成功。代表：200
		
		3. 3xx：重定向。代表：302(重定向)，304(访问缓存)
		
		   （1）重定向
		
		   ![image-20201222185753281](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201222185753281.png)
		
		   （2）访问缓存
		
		   ![image-20201222185905084](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201222185905084.png)
		
		4. 4xx：<font color ="red">客户端错误</font>。
		
		  * 代表：
		  	* 404（请求路径没有对应的资源） 
		  	* 405：请求方式没有对应的doXxx方法
		
		5. 5xx：<font color = "red">服务器端错误</font>。代表：500(服务器内部出现异常)

#### 响应头

   1. 格式：头名称： 值

   2. 常见的响应头：

        1. Content-Type：服务器告诉客户端本次响应体数据格式以及编码格式

        2. Content-disposition：服务器告诉客户端以什么格式打开响应体数据

            * 值：
                * in-line:默认值,在当前页面内打开
                * attachment;filename=xxx：以附件形式打开响应体。文件下载

           

#### 响应空行

#### 响应体

传输的数据(HTML页面)					




```html
	* 响应字符串格式
		HTTP/1.1 200 OK
		Content-Type: text/html;charset=UTF-8
		Content-Length: 101
		Date: Wed, 06 Jun 2018 07:08:42 GMT

		<html>
		  <head>
		    <title>$Title$</title>
		  </head>
		  <body>
		  hello , response
		  </body>
		</html>
```



## Response对象



### 功能：设置响应消息

1. 设置响应行
	1. 格式：HTTP/1.1 200 ok
	
	2. 设置状态码：
	
	   ```
	   setStatus(int sc) 
	   ```
	
2. 设置响应头：
	
	```
	setHeader(String name, String value) 
	```
	
3. 设置响应体：
	* 使用步骤：
		1. 获取输出流
			* 字符输出流：

			  ```
    PrintWriter getWriter()
			  ```
			
			* 字节输出流：
			
			  ```
			  ServletOutputStream getOutputStream()
			  ```
			
		2. 使用输出流，将数据输出到客户端浏览器









### 案例：

案例一

（1）完成重定向

（2）服务器输出字符数据到浏览器

（3）服务器输出字节数据到浏览器

（4）验证码



1. 完成重定向
	* 重定向：资源跳转的方式
	
	* 代码实现：
   	
     ```java
     //1. 设置状态码为302
     response.setStatus(302);
     //2.设置响应头location
     response.setHeader("location","/day15/responseDemo2");
        		
     //简单的重定向方法	   ！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！     
     response.sendRedirect("/day15/responseDemo2");
     ```

![image-20201222195853210](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201222195853210.png)







### 重定向的特点:redirect

1. 地址栏发生变化
2. 重定向可以访问其他站点(服务器)的资源
3. 重定向是两次请求。不能使用request对象来共享数据



### 转发的特点：forward

​	(1)转发地址栏路径不变

​	(2)转发只能访问当前服务器下的资源

​	(3)转发是一次请求，可以使用request对象来共享数据



### forward 和  redirect 区别(<font color = "red">面试</font>)

（如上）







### 路径写法：

(1)路径分类

1. 相对路径：通过相对路径不可以确定唯一资源
	* 如：./index.html
	* 不以/开头，以.开头路径

	* <font color ="red">规则</font>：找到当前资源和目标资源之间的相对位置关系
		* ./：当前目录
		* ../:后退一级目录
	
	```html
	//找到当前资源和目标资源之间的相对位置关系
	<p> 当前资源：
	    http://localhost/day15/location.html            #在web下
	</p>
	<p> 目标资源：
	    http://localhost/day15/responseDemo2     #在src下
	</p>
	# 相对路径
	<a href="./responseDemo2"> responseDemo2 </a>   #./可以省略
	<a href="responseDemo2"> responseDemo2 </a>   #./可以省略
	#如果在web目录下，新建一个目录则，该目录需要../返回到day15
	```
	
	
	
2. 绝对路径：通过绝对路径可以确定唯一资源
  * 如：http://localhost/day15/responseDemo2		/day15/responseDemo2
  * 以/开头的路径 

  * 规则：判断定义的路径是给谁用的？判断请求将来从哪儿发出
  	* <font color= "red">给客户端浏览器使用</font>：需要加虚拟目录(项目的访问路径)
        		* 建议虚拟目录动态获取：request.getContextPath()
                		* <a> , <form> 重定向...
  	* <font color= "red">给服务器使用</font>：不需要加虚拟目录
        		* 转发路径

  <font color = "red">虚拟目录可以理解为区分一个系统中多个服务器 </font>

  ```java
  //动态获取虚拟目录
  String contextPath = resquest.getContextPath();
  ```

  

### 服务器输出字符数据到浏览器

* 步骤：
   1. 获取字符输出流
   2. 输出数据

   * 注意：
   	* 乱码问题：
   		1. ```java
   		   PrintWriter pw = response.getWriter();//获取的流的默认编码是ISO-8859-1
   		   pw.write("hello")
     	   ```
   	 ```
   		
   		   
   		
   		2. 设置该流的默认编码
   		
   		3. 告诉浏览器响应体使用的编码
   		
   		//简单的形式，设置编码，是在获取流之前设置
   		
   		```java
   		//获取流对象之前，设置流的默认编码 : ISO-8859-1 设置为：GBK
   		response.setCharacterEncoding("utf-8");// 可省略
   		//然后 高速浏览器，服务器发送的消息体数据的编码。建议浏览器使用该编码解码
   		response.setHeader("content-type", "text/html;charset=utf-8")
   		
   		    
   		 //记住！！！ 简化版
   		response.setContentType("text/html;charset=utf-8");
   		
   		
   		// 服务器输出字节数据到浏览器
   		//区别（request）
   		req.setCharacterEncoding("utf-8");
   	 ```
   	
   	​	
### 服务器输出字节数据到浏览器

* 步骤：
	1. 获取字节输出流
	2. 输出数据

```java
response.setContentType("text/html;charset=utf-8");
ServletOutputStream sos = response.getOutputStream();
sos.write("你好".getBytes("utf-8"));
//一般字节输出图片
```







## 验证码

1. 本质：图片
2. 目的：防止恶意表单注册












​						









## ServletContext对象：



### (1)概念：

代表整个web应用，可以和程序的容器(服务器)来通信

### (2)获取：

1. 通过request对象获取
	
	```
	request.getServletContext();
	```
	
	
	
2. 通过HttpServlet获取
	
	```
	this.getServletContext();
	```
	
	

### (3)功能：

#### 1）获取MIME类型：

* MIME类型:在互联网通信过程中定义的一种文件数据类型
	
* 格式： 大类型/小类型   text/html		image/jpeg
	
* 获取：

  ```
  String getMimeType(String file)  
  ```

  

#### 2）域对象：共享数据

1. ```
   setAttribute(String name,Object value)
   ```

   

2. ```
   getAttribute(String name)
   ```

   

3. ```
    removeAttribute(String name)
   ```

   

* ServletContext对象范围：<font color = "red">所有用户所有请求的数据</font>
* request域也有类似的：代表一次请求的范围，一般用于请求转发的多个资源中共享数据。但ServletContext范围是全部用户



#### 3)获取文件的真实(服务器)路径



1. 方法：String getRealPath(String path)  
	
    ```java
String b = context.getRealPath("/b.txt");//web目录下资源访问
    System.out.println(b);
    
    String c = context.getRealPath("/WEB-INF/c.txt");//WEB-INF目录下的资源访问
    System.out.println(c);
           
    
    String a = context.getRealPath("/WEB-INF/classes/a.txt");//src目录下的资源访问
    System.out.println(a);
    
    
        
    ```
    
    一般配置文件放在三个位置（src,  web,  /web/WEB-INF）

   ![image-20201223171101465](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201223171101465.png)


​     
​       







## 案例：

	* 文件下载需求：
		1. 页面显示超链接
		2. 点击超链接后弹出下载提示框
		3. 完成图片文件下载


	* 分析：
		1. 超链接指向的资源如果能够被浏览器解析，则在浏览器中展示，如果不能解析，则弹出下载提示框。不满足需求
		2. 任何资源都必须弹出下载提示框
		3. 使用响应头设置资源的打开方式：
			* content-disposition:attachment;filename=xxx


	* 步骤：
		1. 定义页面，编辑超链接href属性，指向Servlet，传递资源名称filename
		2. 定义Servlet
			1. 获取文件名称
			2. 使用字节输入流加载文件进内存
			3. 指定response的响应头： content-disposition:attachment;filename=xxx
			4. 将数据写出到response输出流


	* 问题：
		* 中文文件问题
			* 解决思路：
				1. 获取客户端使用的浏览器版本信息
				2. 根据不同的版本信息，设置filename的编码方式不同













# 会话技术&JSP入门

	1. 会话技术
		1. Cookie
		2. Session
	2. JSP：入门学习



## 会话技术

1. 会话：**一次会话**中包含**多次请求和响应**。
	* 一次会话：浏览器第一次给服务器资源发送请求，会话建立，直到有一方断开为止
2. 功能：在一次会话的范围内的多次请求间，共享数据
3. 方式：
	1. 客户端会话技术：Cookie
	2. 服务器端会话技术：Session

![image-20201224093000673](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201224093000673.png)

数据存到客户端：Cookie，存到服务端：Session







## Cookie：小饼干

### (1)概念：

客户端会话技术，将数据保存到客户端。每次响应发过去，实现共享。

![image-20201224093508665](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201224093508665.png)

### (2)快速入门：

* 使用步骤：
  1. 创建Cookie对象，绑定数据

    ```
    new Cookie(String name, String value) 
    ```

    

  2. 发送Cookie对象

    ```
    response.addCookie(Cookie cookie) 
    ```

    

  3. 获取Cookie，拿到数据

    ```
    Cookie[]  request.getCookies()  
    ```

    



### (3)实现原理

* 基于响应头set-cookie和请求头cookie实现

![image-20201224105448730](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201224105448730.png)







### (4)cookie的细节

1. 一次可不可以发送多个cookie?
	* 可以
	* 可以创建多个Cookie对象，使用response调用多次addCookie方法发送cookie即可。
2. cookie在浏览器中保存多长时间？
  1. 默认情况下，当浏览器关闭后，Cookie数据被销毁

  2. <font color="red">持久化存储</font>：

    ```
    setMaxAge(int seconds)
    ```


​    
​    1. 正数：将Cookie数据写到硬盘的文件中。持久化存储。并指定cookie存活时间，时间到后，cookie文件自动失效
​    2. 负数：默认值
​    3. 零：删除cookie信息
3. cookie能不能存中文？
	* 在tomcat 8 之前 cookie中不能直接存储中文数据。
		* 需要将中文数据转码---一般采用URL编码(%E3)
	* 在tomcat 8 之后，cookie支持中文数据。特殊字符还是不支持，建议使用URL编码存储，URL解码解析
4. cookie共享问题？
  1. 假设**在一个tomcat服务器**中，部署了**多个web项目**，那么在这些web项目中cookie能不能共享？
   * 默认情况下cookie不能共享

        ```
        setPath(String path)
        ```

        :设置cookie的获取范围。默认情况下，设置当前的虚拟目录

        	* **如果要共享，则可以将path设置为"/"**

        

6.不同的tomcat服务器间cookie共享问题？

```
setDomain(String path)
```

:如果设置<font color = "red">一级域名</font>相同(baidu.com)，那么多个服务器之间cookie可以共享

```
setDomain(".baidu.com")
```

,那么tieba.baidu.com和news.baidu.com中cookie可以共享



### (5)Cookie的特点和作用

1. cookie**存储数据在客户端浏览器**
2. 浏览器对于单个cookie 的**大小有限制(4kb)** 以及 对同一个域名下的总**cookie数量也有限制(20个)**

* 作用：
	1. cookie一般用于存出少量的不太敏感的数据
	2. 在不登录的情况下，完成服务器对客户端的身份识别

​			















### 案例：记住上一次访问时间



![image-20201224144403653](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201224144403653.png)




	6. 案例：记住上一次访问时间
		1. 需求：
			1. 访问一个Servlet，如果是第一次访问，则提示：您好，欢迎您首次访问。
			2. 如果不是第一次访问，则提示：欢迎回来，您上次访问时间为:显示时间字符串
	
		2. 分析：
			1. 可以采用Cookie来完成
			2. 在服务器中的Servlet判断是否有一个名为lastTime的cookie
				1. 有：不是第一次访问
					1. 响应数据：欢迎回来，您上次访问时间为:2018年6月10日11:50:20
					2. 写回Cookie：lastTime=2018年6月10日11:50:01
				2. 没有：是第一次访问
					1. 响应数据：您好，欢迎您首次访问
					2. 写回Cookie：lastTime=2018年6月10日11:50:01
	
		3. 代码实现：




```java
@WebServlet("/CookieTest")
public class CookieTest extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        Cookie[] cookies = request.getCookies();
        response.setContentType("text/html;charset=utf-8");
        boolean flag = false;
        if(cookies != null) {
            for (Cookie cookie : cookies) {
                String lastname = cookie.getName();
                if(lastname.equals("lastname")) {
                    flag = true;
                    String date = cookie.getValue();
                    //解码
                    String decode = URLDecoder.decode(date, StandardCharsets.UTF_8);
                    response.getWriter().write("上次访问的时间为："+decode);
                    //重新设置时间
                    Date date1 = new Date();
                    SimpleDateFormat dateFormat = new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");
                    String format_date = dateFormat.format(date1);
                    //编码
                    String encode = URLEncoder.encode(format_date, StandardCharsets.UTF_8);

                    cookie.setValue(encode);
                    cookie.setMaxAge(60*60*24);
                    response.addCookie(cookie);
                    break;
                }
            }
        }
        if(cookies == null || !flag) {
            Date date_first = new Date();
            SimpleDateFormat dateFormat = new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");
            String first = dateFormat.format(date_first);

            String encode = URLEncoder.encode(first, StandardCharsets.UTF_8);
            response.getWriter().write("首次访问！");
            //绑定cookie
            Cookie lastname = new Cookie("lastname", encode);
            response.addCookie(lastname);
            lastname.setMaxAge(60*60*24);
        }
    }

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        this.doPost(request, response);
    }
}
```




​		




​		









## JSP：入门学习



### (1)概念：

<font color = "red">Java Server Pages</font>： java服务器端页面

* 可以理解为：一个特殊的页面，其中既可以指定定义html标签，又可以定义java代码
* 用于简化书写！！！





### (2)原理

* JSP本质上就是一个Servlet

 ![image-20201224160232113](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201224160232113.png)









### (3)JSP的脚本：JSP定义Java代码的方式

1. <%  代码 %>：定义的java代码，在service方法中。service方法中可以定义什么，该脚本中就可以定义什么。
2. <%! 代码 %>：定义的java代码，在jsp转换后的java类的成员位置。
3. <%= 代码 %>：定义的java代码，会输出到页面上。输出语句中可以定义什么，该脚本中就可以定义什么。







### (4)JSP的内置对象：

* 在jsp页面中不需要获取和创建，可以直接使用的对象
* jsp一共有9个内置对象。
* 今天学习3个：
	* <font color = "red">request</font>
	* <font color = "red">response</font>
	* <font color = "red">out</font>：字符输出流对象。可以将数据输出到页面上。和response.getWriter()类似
		* response.getWriter()和out.write()的区别：
			* 在tomcat服务器真正给客户端做出响应之前，会先找response缓冲区数据，再找out缓冲区数据。
			* response.getWriter()数据输出永远在out.write()之前



![image-20201224170807912](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201224170807912.png)











### (5)案例:改造Cookie案例







## Session：主菜

### (1)概念

服务器端会话技术，在一次会话的多次请求间共享数据，将数据保存在服务器端的对象中。HttpSession



### (2)快速入门：

1. 获取HttpSession对象：
	
	```java
	HttpSession session = request.getSession();
	```
	
	
	
2. 使用HttpSession对象：
	
	```java
	Object getAttribute(String name)  
	void setAttribute(String name, Object value)
	void removeAttribute(String name)  
	
	```
	
	

### (3)原理

* Session的实现是依赖于Cookie的

![image-20201224192754861](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201224192754861.png)

 











### (4)细节：

1. 当客户端关闭后，服务器不关闭，两次获取session是否为同一个？
	* 默认情况下。**不是**。
	
	* 如果需要相同，则可以创建Cookie,键为JSESSIONID，设置最大存活时间，让cookie持久化保存。
   	
      ```java
   Cookie c = new Cookie("JSESSIONID",session.getId());
	   c.setMaxAge(60*60);
	   response.addCookie(c);
	   ```
	   
	   
	
2. 客户端不关闭，服务器关闭后，两次获取的session是同一个吗？
	* 不**是同一个，但是要确保数据不丢失**。tomcat自动完成以下工作**(idea不可以活化)**
		* session的钝化：
			* 在服务器正常关闭之前，将session对象系列化到硬盘上
		* session的活化：
			* 在服务器启动后，将session文件转化为内存中的session对象即可。
	
3. session什么时候被销毁？
	1. 服务器关闭
	
	2. session对象调用（自杀~）
	
	   ```
	   invalidate()
	   ```
	
	    
	
	3. session默认失效时间 **30分钟**
		选择性配置修改	
		<session-config>
	        <session-   timeout>30</session-timeout>
	    </session-config>





### (5)session的特点

1. session用于存储一次会话的多次请求的数据，存在服务器端
 2. session可以存储任意类型，任意大小的数据

* session与Cookie的区别：
	1. session存储数据在服务器端，Cookie在客户端
	2. session没有数据大小限制，Cookie有
	3. session数据安全，Cookie相对于不安全









## 案例：验证码

	1. 案例需求：
		1. 访问带有验证码的登录页面login.jsp
		2. 用户输入用户名，密码以及验证码。
			* 如果用户名和密码输入有误，跳转登录页面，提示:用户名或密码错误
			* 如果验证码输入有误，跳转登录页面，提示：验证码错误
			* 如果全部输入正确，则跳转到主页success.jsp，显示：用户名,欢迎您


	2. 分析：




![image-20201224201139889](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201224201139889.png)





# JSP&&MVC开发模式&&EL表达式&&JSTL标签&&三层架构

	1. JSP:
		1. 指令
		2. 注释
		3. 内置对象
	
	2. MVC开发模式
	3. EL表达式
	4. JSTL标签
	5. 三层架构



## JSP:

### (1)指令

* 作用：用于配置JSP页面，导入资源文件

* 格式：
	
	```JSP
	<%@ 指令名称 属性名1=属性值1 属性名2=属性值2 ... %>
	```
	
	
	
* 分类：
  1. <font color="red">page</font>		： 配置JSP页面的
  	
  	* contentType：等同于response.setContentType()
  		1. 设置响应体的mime类型以及字符集
  		2. 设置当前jsp页面的编码（只能是高级的IDE才能生效，如果使用低级工具，则需要设置pageEncoding属性设置当前页面的字符集）
  	* import：导包
  	* errorPage：当前页面发生异常后，会自动跳转到指定的错误页面
  	* isErrorPage：标识当前也是是否是错误页面。
  		* true：是，可以使用内置对象exception
  		* false：否。默认值。不可以使用内置对象exception
  	
  2. <font color="red">include</font>	： 页面包含的。导入页面的资源文件

     			* <%@include file="top.jsp"%>

  3. <font color="red">taglib</font>	： 导入资源

     ```java
     <%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
     
     prefix：前缀，自定义的
     ```

     

### (2)注释:

1. html注释：
	<!-- -->:只能注释html代码片段
2. jsp注释：推荐使用
	<%-- --%>：可以注释所有



### (3)内置对象<font color = "green">(面试)</font>

* 在jsp页面中不需要创建，直接使用的对象
* 一共有9个：
  


	  变量名			 真实类型			  作用
	* pageContext	PageContext         当前页面共享数据，还可以获取其他八个内置对象
	* request		HttpServletRequest	一次请求访问的多个资源(转发)
	* session		HttpSession			一次会话的多个请求间
	* application	ServletContext		所有用户间共享数据
	* response		HttpServletResponse	响应对象
	* page			Object				当前页面(Servlet)的对象  this
	* out			JspWriter			输出对象，数据输出到页面上
	* config		ServletConfig		Servlet的配置对象
	* exception		Throwable			异常对象

​	







## MVC：开发模式	



### (1)jsp演变历史

1. 早期只有servlet，只能使用response输出标签数据，非常麻烦
2. 后来又jsp，简化了Servlet的开发，如果过度使用jsp，在jsp中即写大量的java代码，有写html表，造成难于维护，难于分工协作
3. 再后来，java的web开发，借鉴mvc开发模式，使得程序的设计更加合理性

### (2)MVC：

1. M：Model，模型。JavaBean
	* 完成具体的业务操作，如：查询数据库，封装对象
2. V：View，视图。JSP
	* 展示数据
3. C：Controller，控制器。Servlet
	* 获取用户的输入
	* 调用模型
	* 将数据交给视图进行展示



![image-20201225094935568](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201225094935568.png)



* 优缺点：

   1.优点：

   1. 耦合性低，方便维护，可以利于分工协作
   2. 重用性高

   2.缺点：

   1. 使得项目架构变得复杂，对开发人员要求高











## EL表达式

1. 概念：Expression Language 表达式语言
2. 作用：<font color = "red">替换和简化jsp页面中java代码的编写</font>
3. 语法：${表达式}
4. 注意：
	* jsp默认支持el表达式的。如果要忽略EL表达式
		1. 设置jsp中page指令中：isELIgnored="true" 忽略当前jsp页面中所有的el表达式
		2.  \ ${表达式}  ：忽略当前这个el表达式



5. 使用：
  1. 运算：
  	* 运算符：
  		1. 算数运算符： + - * /(div) %(mod)
                		2. 比较运算符： > < >= <= == !=
            		3. 逻辑运算符： &&(and) ||(or) !(not)
                      		4. 空运算符： empty
  			* 功能：用于判断字符串、集合、数组对象是否为null或者长度是否为0
                			* ${**empty** list}:判断字符串、集合、数组对象是否为null或者长度为0
            			* ${**not empty** str}:表示判断字符串、集合、数组对象是否不为null 并且 长度>0

  2. 获取值
        1. el表达式只能从域对象(四个域对象)中获取值
          
              2. 语法：
      1. ${域名称.键名}：从指定域中获取指定键的值
      	* 域名称：
      		1. pageScope		--> pageContext
      		2. requestScope 	--> request
      		3. sessionScope 	--> session
      		4. applicationScope --> application（ServletContext）
      	* 举例：在request域中存储了name=张三
	* 获取：${requestScope.name}
      
2. ${键名}：表示依次从最小的域中查找是否有该键对应的值，直到找到为止。
   
3. 获取对象、List集合、Map集合的值
   
         ```
         通过的是对象的属性来获取
         	* setter或getter方法,去掉set或get,在将剩余部分,首字母变为小写。
         	* setName --> Name --> name
   ```
      
   1)**对象**：${域名称.键名.属性名}
      
   * 本质上会去调用对象的getter方法
      
   2)**List集合**：${域名称.键名[索引]}
      
   3)**Map集合**：
      
         * ${域名称.键名.key名称}
   * ${域名称.键名["key名称"]}
   ```
   
  3. 隐式对象：
       * el表达式中有11个隐式对象

       * pageContext：

         * 获取jsp其他八个内置对象

            ```jsp
            ${pageContext.request.contextPath}
            ```

            动态获取虚拟目录




















​				
​		




​	

## JSTL

1. 概念：JavaServer Pages Tag Library  JSP标准标签库
	
* 是由Apache组织提供的开源的免费的jsp标签		<标签>
	
2. 作用：<font color = "red">替换和简化jsp页面中java代码的编写</font>

3. 使用步骤：
	1. 导入jstl相关jar包
	
	2. 引入标签库：taglib指令：

	   ```jsp
	     <%@ taglib %>
	   例如：
	   <%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
	   
	   prefix：前缀，自定义的
	   ```
	
	   
	
	3. 使用标签
	
	
	
4. 常用的JSTL标签
  1. <font color = "red">if</font>:相当于java代码的if语句

    1)属性：
    
    * test 必须属性，接受boolean表达式
        * 如果表达式为true，则显示if标签体内容，如果为false，则不显示标签体内容
        * 一般情况下，test属性值会结合el表达式一起使用
    
    2)注意：
    
     		 * c:if标签没有else情况，想要else情况，则可以在定义一个c:if标签
    
    ```jsp
    <c:if test="false"> <h1>我是真</h1> </c:if>
    
    <c:if test="${not empty list_1}"> 遍历集合 </c:if>
    ```


​    

  2. <font color = "red">choose</font>:相当于java代码的switch语句

        1. 使用choose标签声明         			相当于switch声明
      2. 使用when标签做判断         			相当于case
      3. 使用otherwise标签做其他情况的声明    	相当于default

    ```jsp
    <%-- 
        完成数字编号对应星期几案例
        1,域中存储一数字
        2,使用choose标签取出数字
        3,使用when标签做数字判断相当于switch声明相当于case
        4.otherwise标签做其他情况的声明 相当于default
        --%>
    
    <%
    	request.setAttribute("number",3);
    %>
    
    <c:choose>
        <c:when test="${number == 1}">星期一</c:when>
        <c:when test="${number == 2}">星期二</c:when>
        <c:when test="${number == 3}">星期三</c:when>
        <c:otherwise>数字输入有误</c:otherwise>
    </c:choose>
    ```


​    

  3. <font color = "red">foreach</font>:相当于java代码的for语句

     ```jsp
     <%-- 
     foreach:相当于java代码的for语句
         1·完成重复的操作for(int i = 0; i< 10; i++){
     	}
     	*属性    begin:开始值		
             	end:结束值
                 var:临时变量
                 step:步长
                 varStatus:循环状态对象
                     index:容器中元素的索引,从开始
                     count:循环次数,从1开始
                         
         2·遍历容器List<User> list;for (User user: list){
             
         }
     
       --%>  
     <c:forEach begin="1" end="10" var="i" step="2">
         ${i}
     </c:forEach>
     
     <c:forEach items="${list}" var="str" varStatus="s">
     	${s.index}  ${s.count} ${str}<br>
     </c:forEach>
     ```

     

5. 练习：
	
	* 需求：在request域中有一个存有User对象的List集合。需要使用jstl+el将list集合数据展示到jsp页面的表格table中



























## 三层架构：软件设计架构

	1. 界面层(表示层)：用户看的得界面。用户可以通过界面上的组件和服务器进行交互
	2. 业务逻辑层：处理业务逻辑的。
	3. 数据访问层：操作数据存储文件。



![image-20201225160604164](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201225160604164.png)












## 案例：用户信息列表展示

	1. 需求：用户信息的增删改查操作
	2. 设计：
		1. 技术选型：Servlet+JSP+MySQL+JDBCTempleat+Duird+BeanUtilS+tomcat
		2. 数据库设计：
			create database day17; -- 创建数据库
			use day17; 			   -- 使用数据库
			create table user(   -- 创建表
				id int primary key auto_increment,
				name varchar(20) not null,
				gender varchar(5),
				age int,
				address varchar(32),
				qq	varchar(20),
				email varchar(50)
			);
	
	3. 开发：
		1. 环境搭建
			1. 创建数据库环境
			2. 创建项目，导入需要的jar包
	
		2. 编码


	4. 测试
	5. 部署运维



![image-20201225165432414](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201225165432414.png)





![image-20201228100736120](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201228100736120.png)









![image-20201228111319696](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201228111319696.png)



![image-20201229161156800](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201229161156800.png)



分页

![image-20201229194752421](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201229194752421.png)

![image-20201229195812272](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201229195812272.png)





复杂条件查询

![image-20201230124345104](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201230124345104.png)









# Filter：过滤器&&Listener：监听器







## Filter：过滤器



![image-20210107170630260](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210107170630260.png)

### 1.概念：

* 生活中的过滤器：净水器,空气净化器，土匪、
* web中的过滤器：当访问服务器的资源时，过滤器可以将请求拦截下来，完成一些特殊的功能。
* 过滤器的作用：
	* 一般用于完成通用的操作。如：登录验证、统一编码处理、敏感字符过滤...



### 2.快速入门：

1. 步骤：
	1. 定义一个类，实现接口Filter
	2. 复写方法
	3. 配置拦截路径
		1. web.xml
		2. 注解







```java
2. 代码：
		@WebFilter("/*")//访问所有资源之前，都会执行该过滤器
		public class FilterDemo1 implements Filter {
		    @Override
		    public void init(FilterConfig filterConfig) throws ServletException {
		
		    }
		
		    @Override
		    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
		        System.out.println("filterDemo1被执行了....");
		        //放行
		        filterChain.doFilter(servletRequest,servletResponse);
		
		    }
		
		    @Override
		    public void destroy() {
		
		    }
		}
```

​		



### 3.过滤器细节：

1. web.xml配置	
	
   ```xml
   <filter>
        <filter-name>demo1</filter-name>
        <filter-class>cn.itcast.web.filter.FilterDemo1</filter-class>
    </filter>
	 <filter-mapping>
        <filter-name>demo1</filter-name>
   	<!-- 拦截路径 -->
        <url-pattern>/*</url-pattern>
   </filter-mapping>
   ```
   
   
   
2. 过滤器执行流程
	1. 执行过滤器
	2. 执行放行后的资源
	3. 回来执行过滤器放行代码下边的代码
	
3. 过滤器生命周期方法
	1. init:在服务器启动后，会创建Filter对象，然后调用init方法。只执行一次。用于加载资源
	2. doFilter:每一次请求被拦截资源时，会执行。执行多次
	3. destroy:在服务器关闭后，Filter对象被销毁。如果服务器是正常关闭，则会执行destroy方法。只执行一次。用于释放资源
	
4. <font color = "red">过滤器配置详解</font> 
	
	* 拦截路径配置：
		1. 具体资源路径： /index.jsp   只有访问index.jsp资源时，过滤器才会被执行
		2. 拦截目录： /user/*	访问/user下的所有资源时，过滤器都会被执行
		3. 后缀名拦截： *.jsp		访问所有后缀名为jsp资源时，过滤器都会被执行
		4. 拦截所有资源：/*		访问所有资源时，过滤器都会被执行
	* 拦截方式配置：资源被访问的方式
		* 注解配置：
			* 设置dispatcherTypes属性
				1. REQUEST：默认值。浏览器直接请求资源
				2. FORWARD：转发访问资源
				3. INCLUDE：包含访问资源
				4. ERROR：错误跳转资源
				5. ASYNC：异步访问资源
		* web.xml配置
			* 设置<dispatcher></dispatcher>标签即可
	
5. 过滤器链(配置多个过滤器)
	* 执行顺序：如果有两个过滤器：过滤器1和过滤器2
		1. 过滤器1
		2. 过滤器2
		3. 资源执行
		4. 过滤器2
		5. 过滤器1 

	* 过滤器先后顺序问题：
		1. 注解配置：按照类名的字符串比较规则比较，值小的先执行
			* 如： AFilter 和 BFilter，AFilter就先执行了。
		2. web.xml配置： <filter-mapping>谁定义在上边，谁先执行

![image-20210108201336052](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210108201336052.png)







 

### 4.1案例1_登录验证

* 需求：
	1. 访问day17_case案例的资源。验证其是否登录
	2. 如果登录了，则直接放行。
	3. 如果没有登录，则跳转到登录页面，提示"您尚未登录，请先登录"。



​	![image-20210109100615058](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210109100615058.png)

```java
public void doFilter(ServletRequest req, ServletResponse resp, FilterChain chain) throws ServletException, IOException {
        //0 强制转换
        HttpServletRequest request = (HttpServletRequest) req;
        //1 获取资源请求路径
        String uri = request.getRequestURI();
        if(uri.contains("/login.jsp") || uri.contains("/loginServlet") || uri.contains("/css/") || uri.contains("/js/") || uri.contains("/fonts") || uri.contains("/checkCodeServlet")) {
            chain.doFilter(req,resp);
        }else {
            Object user = request.getSession().getAttribute("user");
            if(user != null) {
                chain.doFilter(req,resp);
            }else {
                request.setAttribute("login_msg","您尚未登录请登录");
                request.getRequestDispatcher("/login.jsp").forward(req,resp);
            }
        }
    }
```







### 4.2案例2_敏感词汇过滤

		2. 案例2_敏感词汇过滤
			* 需求：
				1. 对day17_case案例录入的数据进行敏感词汇过滤
				2. 敏感词汇参考《敏感词汇.txt》
				3. 如果是敏感词汇，替换为 *** 
	
			* 分析：
				1. 对request对象进行增强。增强获取参数相关方法
				2. 放行。传递代理对象

![image-20210111183922355](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210111183922355.png)

<font color = "red">代码(固定)</font>：(在src下的配置文件：”WEB-INF/classes/xxx.xx“)

```java

```











### 增强对象的功能：

```
* 增强对象的功能：

* 设计模式：一些通用的解决固定问题的方式

    1. 装饰模式

    2. 代理模式
          * 概念：
            1. 真实对象：被代理的对象
            2. 代理对象：
            3. 代理模式：代理对象代理真实对象，达到增强真实对象功能的目的

         * 实现方式：

           1. 静态代理：有一个类文件描述代理模式

           2. 动态代理：在内存中形成代理类

                 * 实现步骤：

                   1. 代理对象和真实对象实现相同的接口
                      2. 代理对象 = Proxy.newProxyInstance();
                      3. 使用代理对象调用方法。
                      4. 增强方法

                   * 增强方式：
                     1. 增强参数列表
                     2. 增强返回值类型
                     3. 增强方法体执行逻辑	




```



代理模式：

![image-20210111184400082](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210111184400082.png)

增强的固定格式：

```java

public class ProxyTest {

    public static void main(String[] args) {
        //1.创建真实对象
        Lenovo lenovo = new Lenovo();
        
        //2.动态代理增强lenovo对象
        /*
            三个参数：
                1. 类加载器：真实对象.getClass().getClassLoader()
                2. 接口数组：真实对象.getClass().getInterfaces()
                3. 处理器：new InvocationHandler()
         */
        SaleComputer proxy_lenovo = (SaleComputer) Proxy.newProxyInstance(lenovo.getClass().getClassLoader(), lenovo.getClass().getInterfaces(), new InvocationHandler() {

            /*
                代理逻辑编写的方法：代理对象调用的所有方法都会触发该方法执行
                    参数：
                        1. proxy:代理对象
                        2. method：代理对象调用的方法，被封装为的对象
                        3. args:代理对象调用的方法时，传递的实际参数
             */
            @Override
            public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
                /*System.out.println("该方法执行了....");
                System.out.println(method.getName());
                System.out.println(args[0]);

*/
                //判断是否是sale方法
                if(method.getName().equals("sale")){
                    //1.增强参数
                    double money = (double) args[0];
                    money = money * 0.85;
                    System.out.println("专车接你....");
                    //使用真实对象调用该方法
                    String obj = (String) method.invoke(lenovo, money);
                    System.out.println("免费送货...");
                    //2.增强返回值
                    return obj+"_鼠标垫";
                }else{
                    Object obj = method.invoke(lenovo, args);
                    return obj;
                }
            }
        });

        //3.调用方法

       /* String computer = proxy_lenovo.sale(8000);
        System.out.println(computer);*/

        proxy_lenovo.show();
    }
}

```







## Listener：监听器



### 1.概念：web的三大组件之一。

* 事件监听机制
	* 事件	：一件事情
	* 事件源 ：事件发生的地方
	* 监听器 ：一个对象
	* 注册监听：将事件、事件源、监听器绑定在一起。 当事件源上发生某个事件后，执行监听器代码



###  2.ServletContextListener:

监听ServletContext对象的创建和销毁

* 方法：
	* void contextDestroyed(ServletContextEvent sce) ：ServletContext对象被销毁之前会调用该方法
	* void contextInitialized(ServletContextEvent sce) ：ServletContext对象创建后会调用该方法
* 步骤：
	1. 定义一个类，实现ServletContextListener接口
	2. 复写方法
	3. 配置
		1. web.xml
				
```xml
	<listener>
			<listener-class>cn.itcast.web.listener.ContextLoaderListener</listener-class>
	</listener>

<!-- 指定初始化参数 -->
	<context-param>
        <param-name>contextConfigLocation</param-name>
        <param-value>/WEB-INF/classes/applicationContext.xml</param-value>
	</context-param>


```

​	指定初始化参数<context-param>

​				2. 注解：

​							

```java
@WebListener
```













****









## 今日内容

	1. JQuery 基础：
		1. 概念
		2. 快速入门
		3. JQuery对象和JS对象区别与转换
		4. 选择器
		5. DOM操作
		6. 案例



![image-20210112102921261](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210112102921261.png)

![image-20210112102938105](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210112102938105.png)



# JQuery 基础：



## 1.概念

概念： 一个JavaScript框架。简化JS开发
* jQuery是一个快速、简洁的JavaScript框架，是继Prototype之后又一个优秀的JavaScript代码库（或JavaScript框架）。jQuery设计的宗旨	是“write Less，Do More”，即倡导写更少的代码，做更多的事情。它封装JavaScript常用的功能代码，提供一种简便的JavaScript设计模式，优	化HTML文档操作、事件处理、动画设计和Ajax交互。

* JavaScript框架：本质上就是一些js文件，封装了js的原生代码而已





## 2.快速入门

1. 步骤：
	1. 下载JQuery
		* 目前jQuery有三个大版本：
			1.x：兼容ie678,使用最为广泛的，官方只做BUG维护，
				 功能不再新增。因此一般项目来说，使用1.x版本就可以了，
				 最终版本：1.12.4 (2016年5月20日)
			2.x：不兼容ie678，很少有人使用，官方只做BUG维护，
				 功能不再新增。如果不考虑兼容低版本的浏览器可以使用2.x，
				 最终版本：2.2.4 (2016年5月20日)
			3.x：不兼容ie678，只支持最新的浏览器。除非特殊要求，
				 一般不会使用3.x版本的，很多老的jQuery插件不支持这个版本。
				 目前该版本是官方主要更新维护的版本。最新版本：3.2.1（2017年3月20日）
		* jquery-xxx.js 与 jquery-xxx.min.js区别：
			1. jquery-xxx.js：开发版本。给程序员看的，有良好的缩进和注释。体积大一些
			2. jquery-xxx.min.js：生产版本。程序中使用，没有缩进。体积小一些。程序加载更快

	2. 导入JQuery的js文件：导入min.js文件
	3. 使用

```javascript
    var div1 = $("#div1");
    alert(div1.html());
```





## 3.JQuery对象和JS对象区别与转换

1. JQuery对象在操作时，更加方便。
 2. JQuery对象和js对象方法不通用的.
 3. 两者相互转换
     * jq -- > js : jq对象[索引] 或者 jq对象.get(索引)
     * js -- > jq : $(js对象)



## 4.选择器：筛选具有相似特征的元素(标签)

### 4.1基本操作学习：

1. 事件绑定
	
   ```
   //1.获取b1按钮
      $("#b1").click(function(){
          alert("abc");
      });
   ```
   
   比较JavaScript中的  js对象.onclick = functiona() {}
   
2. 入口函数
	
    ```
	$(function () {
	    
    
    });
    ```
    
     window.onload  和 $(function) 区别
       * window.onload 只能定义一次,如果定义多次，后边的会将前边的覆盖掉
       * (function)可以定义多次的。
    
3. 样式控制：css方法
	
	```javascript
	// $("#div1").css("background-color","red");
		$("#div1").css("backgroundColor","pink");
	```
	
	







### 4.2分类

1. 基本选择器
		1. 标签选择器（元素选择器）
			* 语法： $("html标签名") 获得所有匹配标签名称的元素
		2. id选择器 
			* 语法： $("#id的属性值") 获得与指定id属性值匹配的元素
		3. 类选择器
			* 语法： $(".class的属性值") 获得与指定的class属性值匹配的元素
		4. 并集选择器：
			* 语法： $("选择器1,选择器2....") 获取多个选择器选中的所有元素
	2. 层级选择器
		1. 后代选择器
			* 语法： $("A B ") 选择A元素内部的所有B元素		
		2. 子选择器(孙子辈不变)
			* 语法： $("A > B") 选择A元素内部的所有B子元素（div>span）
	3. 属性选择器
		1. 属性名称选择器 
			* 语法： $("A[属性名]") 包含指定属性的选择器（“div[title]”）
		2. 属性选择器
			* 语法： $("A[属性名='值']") 包含指定属性等于指定值的选择器
		3. 复合属性选择器
			* 语法： $("A[属性名='值'][]...") 包含多个属性条件的选择器
	4. 过滤选择器
		1. 首元素选择器 
			* 语法： :first 获得选择的元素中的第一个元素
		2. 尾元素选择器 
			* 语法： :last 获得选择的元素中的最后一个元素
		3. 非元素选择器
			* 语法： :not(selector) 不包括指定内容的元素
		4. 偶数选择器
			* 语法： :even 偶数，从 0 开始计数
		5. 奇数选择器
			* 语法： :odd 奇数，从 0 开始计数
		6. 等于索引选择器
			* 语法： :eq(index) 指定索引元素
		7. 大于索引选择器 
			* 语法： :gt(index) 大于指定索引元素
		8. 小于索引选择器 
			* 语法： :lt(index) 小于指定索引元素
		9. 标题选择器
			* 语法： :header 获得标题（h1~h6）元素，固定写法
	5. 表单过滤选择器
		1. 可用元素选择器 
			
			* 语法： :enabled 获得可用元素
			
			  ```javascript
			  $("input[type='text']:enabled").val("a") //用value改变表单内可用<input>元素的值
			  ```
			
		2. 不可用元素选择器 
			
			* 语法： :disabled 获得不可用元素
		3. 选中选择器 
			
			* 语法： :checked 获得单选/复选框选中的元素
		4. 选中选择器 
			
			* 语法： :selected 获得下拉框选中的元素







## 5.DOM操作

1. 内容操作
	1. html(): 获取/设置元素的标签体内容   
	
	   ```html
	   <a><font>内容</font></a>  --> <font>内容</font>
	   ```
	
	   
	
	2. text(): 获取/设置元素的标签体纯文本内容  
	
	   ```html
	    <a><font>内容</font></a> --> 内容
	   ```
	
	   
	
	3. val()： 获取/设置元素的value属性值
	
	 ![image-20210112165624266](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210112165624266.png)
	
	
	
2. 属性操作
  1. 通用属性操作
  	1. attr(): 获取/设置元素的属性
  	2. removeAttr():删除属性
  	3. prop():获取/设置元素的属性
  	4. removeProp():删除属性

  	* attr和prop区别？
  		1. 如果操作的是元素的固有属性，则建议使用prop
                		2. 如果操作的是元素自定义的属性，则建议使用attr
  2. 对class属性操作
  	1. addClass():添加class属性值
  	2. removeClass():删除class属性值
  	3. toggleClass():切换class属性
  		* toggleClass("one"): 
        			* 判断如果元素对象上存在class="one"，则将属性值one删除掉。  如果元素对象上不存在class="one"，则添加
  	4. css():

3. CRUD操作:
  1. append():父元素将子元素追加到末尾
  	* 对象1.append(对象2): 将对象2添加到对象1元素内部，并且在末尾
  2. prepend():父元素将子元素追加到开头
  	* 对象1.prepend(对象2):将对象2添加到对象1元素内部，并且在开头
  3. appendTo():
  	* 对象1.appendTo(对象2):将对象1添加到对象2内部，并且在末尾
  4. prependTo()：
  	* 对象1.prependTo(对象2):将对象1添加到对象2内部，并且在开头
  5. after():添加元素到元素后边
     * 对象1.after(对象2)： 将对象2添加到对象1后边。对象1和对象2是兄弟关系

  6. before():添加元素到元素前边
     * 对象1.before(对象2)： 将对象2添加到对象1前边。对象1和对象2是兄弟关系
  7. insertAfter()
     * 对象1.insertAfter(对象2)：将对象2添加到对象1后边。对象1和对象2是兄弟关系
  8. insertBefore()
     * 对象1.insertBefore(对象2)： 将对象2添加到对象1前边。对象1和对象2是兄弟关系

  9. remove():移除元素
     * 对象.remove():将对象删除掉
  10. empty():清空元素的所有后代元素。
      * 对象.empty():将对象的后代元素全部清空，但是保留当前对象以及其属性节点


	6. 案例



​			







## 今日内容：

	1. JQuery 高级
		1. 动画
		2. 遍历
		3. 事件绑定
		4. 案例
		5. 插件



# JQuery 高级



## 1.动画

三种方式显示和隐藏元素
### (1)默认显示和隐藏方式

1. show([speed,[easing],[fn]])
	1. 参数：
		1. speed：动画的速度。三个预定义的值("slow","normal", "fast")或表示动画时长的毫秒数值(如：1000)
		2. easing：用来指定切换效果，默认是"swing"，可用参数"linear"
			* swing：动画执行时效果是 先慢，中间快，最后又慢
			* linear：动画执行时速度是匀速的
		3. fn：在动画完成时执行的函数，每个元素执行一次。

2. hide([speed,[easing],[fn]])
3. toggle([speed],[easing],[fn])

### (2)滑动显示和隐藏方式

1. slideDown([speed],[easing],[fn])
2. slideUp([speed,[easing],[fn]])
3. slideToggle([speed],[easing],[fn])

### (3)淡入淡出显示和隐藏方式

1. fadeIn([speed],[easing],[fn])
2. fadeOut([speed],[easing],[fn])
3. fadeToggle([speed,[easing],[fn]])





## 2.遍历

### (1)js的遍历方式

* for(初始化值;循环结束条件;步长)

```javascript
// js 遍历方式

        $(function () {
            let cities = $("#city li");
            for (let i = 0; i < cities.length; i++) {
                alert(i+":"+cities[i].innerHTML)
            }
        })
```



### (2)jq的遍历方式

#### 1.jq对象.each(callback)

1. 语法：
	jquery对象.each(function(index,element){});
		* index:就是元素在集合中的索引
		* element：就是集合中的每一个元素对象

		* this：集合中的每一个元素对象
2. 回调函数返回值：
	* true:如果当前function返回为false，则结束循环(break)。
	* false:如果当前function返回为true，则结束本次循环，继续下次循环(continue)

```javascript
// js对象.each(callback)
            cities.each(function (index,element) {
                alert(this.innerHTML);
                alert($(this).html);
                alert(index+":"+element.innerHTML);
                alert(index+":"+$(element).html);
                // 由于没有break和continue
                //判断如果是上海，则结束循环
                if("上海"==$(element).html){
                    //如果当前function返回为false，则结束循环(break)
                    //如果返回为true，则结束本次循环，继续下次循环(continue)
                    return false;
                }
            })
```



#### 2.$.each(object, [callback])

```javascript
//$.each(object, [callback])
            $.each(cities,function () {
                alert(this.innerHTML);
                //其他类似js对象.each(callback)
            })
```



#### 3.for(..of...): jquery 3.0 版本之后提供的方式

for(元素对象 of 容器对象)

```javascript
            //for..of: jquery 3.0 版本之后提供的方式
            for(li of cities) {
                alert($(li).html());
            }
```



## 3.事件绑定

### (1)jquery标准的绑定方式

* jq对象.事件方法(回调函数)；
* 注：如果调用事件方法，不传递回调函数，则会触发浏览器默认行为。
	* 表单对象.submit();//让表单提交

### (2)on绑定事件/off解除绑定

* jq对象.on("事件名称",回调函数)
* jq对象.off("事件名称")
	* 如果off方法不传递任何参数，则将组件上的所有事件全部解绑

```javascript
$(function () {
            $("#btn").on("click",function () {
                alert("click...")
            });
            $("#btn2").click(function () {
                $("#btn").off("click");
            });
        });
```



### (3)事件切换：toggle

* jq对象.toggle(fn1,fn2...)
	
	* 当单击jq对象对应的组件后，会执行fn1.第二次点击会执行fn2.....
	
* 注意：1.9版本 .toggle() 方法删除,jQuery Migrate（迁移）插件可以恢复此功能。
	
	 ```javascript
	 <script src="../js/jquery-migrate-1.0.0.js" type="text/javascript" charset="utf-8"></script>
	 
	     <script type="text/javascript">
	         $(function () {
	             $("#btn").toggle(function () {
	                 $("#myDiv").css("backgroundColor","green");
	             }, function () {
	                 $("#myDiv").css("backgroundColor","yellow");
	             })
	         })ll
	     </script>
	 
	 
	```










```javascript
4. 案例
	1. 广告显示和隐藏
		        /*
		            需求：
		                1. 当页面加载完，3秒后。自动显示广告
		                2. 广告显示5秒后，自动消失。
		
		            分析：
		                1. 使用定时器来完成。setTimeout (执行一次定时器)
		                2. 分析发现JQuery的显示和隐藏动画效果其实就是控制display
		                3. 使用  show/hide方法来完成广告的显示
		         */
		
		        //入口函数，在页面加载完成之后，定义定时器，调用这两个方法
		        $(function () {
		           //定义定时器，调用adShow方法 3秒后执行一次
		           setTimeout(adShow,3000);
		           //定义定时器，调用adHide方法，8秒后执行一次
		            setTimeout(adHide,8000);
		        });
		        //显示广告
		        function adShow() {
		            //获取广告div，调用显示方法
		            $("#ad").show("slow");
		        }
		        //隐藏广告
		        function adHide() {
		            //获取广告div，调用隐藏方法
		            $("#ad").hide("slow");
		        }
```


​			




		2. 抽奖
			            分析：
			                1. 给开始按钮绑定单击事件
			                    1.1 定义循环定时器
			                    1.2 切换小相框的src属性
			                        * 定义数组，存放图片资源路径
			                        * 生成随机数。数组索引
			                 2. 给结束按钮绑定单击事件
			                    1.1 停止定时器
			                    1.2 给大相框设置src属性



## 5.插件：增强JQuery的功能

实现方式：
#### (1)$.fn.extend(object) 

* 增强通过Jquery获取的对象的功能  $("#id")      <font color = "red">//想象这是JQ对象的函数的扩展，fn类似function</font>

```javascript
    <script type="text/javascript">
        // $.fn.extend(object) 增强通过Jquery获取的对象的功能  $("#id")
        $.fn.extend({
            check:function () {
                this.prop("checked",true);
            },
            uncheck:function () {
                this.prop("checked",false);
            }
        });

        $(function () {
            $("#btn-check").click(function () {
                $("input[type='checkbox']").check();
            });
            $("#btn-uncheck").click(function () {
               $("input[type='checkbox']").uncheck();
            });
        })
    </script>
```



#### (2)$.extend(object)

* 增强JQeury对象自身的功能  $/jQuery     <font color = "red">//想象这是JQ的扩展函数</font>

```javascript
//对全局方法扩展2个方法，扩展min方法：求2个值的最小值；扩展max方法：求2个值最大值
        $.extend({
            min:function (a,b) {
                return a>=b ? b:a;
            },
            max:function (a,b) {
                return a>b?a:b;
            }
        });
        $(function () {
           alert($.max(1,2));
           alert($.min(1,2));
        })
```







## 今日内容

	1. AJAX：
	2. JSON





# AJAX & JSON

## AJAX: 

### (1)概念： 

​		ASynchronous JavaScript And XML	异步的JavaScript 和 XML

异步和同步：客户端和服务器端相互通信的基础上
* 客户端必须等待服务器端的响应。在等待的期间客户端不能做其他操作。

* 客户端不需要等待服务器端的响应。在服务器处理请求的过程中，客户端可以进行其他的操作。



![image-20210116140252391](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210116140252391.png)







​	<font color="red">	Ajax 是一种在无需重新加载整个网页的情况下，能够更新部分网页的技术。</font> 
通过在后台与服务器进行少量数据交换，Ajax 可以使网页实现异步更新。这意味着可以在不重新加载整个网页的情况下，对网页的某部分进行更新。
​		传统的网页（不使用 Ajax）如果需要更新内容，必须重载整个网页页面。

​		提升用户的体验





### (2) 实现方式：

#### 1. 原生的JS实现方式（了解）

```javascript
	1. 原生的JS实现方式（了解）
				 //1.创建核心对象
	            var xmlhttp;
	            if (window.XMLHttpRequest)
	            {// code for IE7+, Firefox, Chrome, Opera, Safari
	                xmlhttp=new XMLHttpRequest();
	            }
	            else
	            {// code for IE6, IE5
	                xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
	            }
	
	            //2. 建立连接
	            /*
	                参数：
	                    1. 请求方式：GET、POST
	                        * get方式，请求参数在URL后边拼接。send方法为空参
	                        * post方式，请求参数在send方法中定义
	                    2. 请求的URL：
	                    3. 同步或异步请求：true（异步）或 false（同步）
	
	             */
	            xmlhttp.open("GET","ajaxServlet?username=tom",true);
	
	            //3.发送请求
	            xmlhttp.send();
	
	            //4.接受并处理来自服务器的响应结果
	            //获取方式 ：xmlhttp.responseText
	            //什么时候获取？当服务器响应成功后再获取
	
	            //当xmlhttp对象的就绪状态改变时，触发事件onreadystatechange。
	            xmlhttp.onreadystatechange=function()
	            {
	                //判断readyState就绪状态是否为4，判断status响应状态码是否为200
	                if (xmlhttp.readyState==4 && xmlhttp.status==200)
	                {
	                   //获取服务器的响应结果
	                    var responseText = xmlhttp.responseText;
	                    alert(responseText);
	                }
	            }
	            
	            
```



#### 2.JQeury实现方式

##### (1)$.ajax()

语法：$.ajax({键值对});

```javascript
function fun() {
            $.ajax({
                url:"AJAXServlet01",
                async:false,
                type:"POST",
                data:{"username":"jack","age":23},
                success:function () {
                    alert(this.data)
                }
            })
        }
```



##### (2)$.get()：发送get请求

* 语法：$.get(url, [data], [callback], [type])
	* 参数：
		* url：请求路径
		* data：请求参数
		* callback：回调函数
		* type：响应结果的类型

##### (3)$.post()：发送post请求

* 语法：$.post(url, [data], [callback], [type])
	* 参数：
		* url：请求路径
		* data：请求参数
		* callback：回调函数
		* type：响应结果的类型

```javascript
$.get("findServlet", {username:username},function (data) {
                   alert(data);
                   let span = $("#s_username");
                   if(data.username) {
                       // 用户名存在
                       span.css("color","red");
                       span.html(data.msg);
                   } else {
                       // 用户名不存在
                       span.css("color","green");
                       span.html(data.msg);
                   }
               }, "json")
```





## JSON：

### (1)概念： 

​		JavaScript Object Notation		JavaScript对象表示法

```javascript
// java中
Person p = new Person();
p.setName("张三");
p.setAge(23);
p.setGender("男");
// javascript中JSON：
var p = {"name":"张三","age":23,"gender":"男"};
```



* json现在多用于存储和交换文本信息的语法
* 进行数据的传输
* JSON 比 XML 更小、更快，更易解析。





### (2)语法：

1. 基本规则
	* 数据在名称/值对中：json数据是由键值对构成的
		* 键用引号(单双都行)引起来，也可以不使用引号
		* 值得取值类型：（可以嵌套）
			1. 数字（整数或浮点数）
			2. 字符串（在双引号中）
			3. 逻辑值（true 或 false）
			4. 数组（在方括号中）	{"persons":[{},{}]}
			5. 对象（在花括号中） {"address":{"province"："陕西"....}}
			6. null
	* 数据由逗号分隔：多个键值对由逗号分隔
	* 花括号保存对象：使用{}定义json 格式
	* 方括号保存数组：[]
2. 获取数据:
	1. json对象.键名
	2. json对象["键名"]
	3. 数组对象[索引]
	4. 遍历



```javascript

				 //1.定义基本格式
		        var person = {"name": "张三", age: 23, 'gender': true};
		
		        var ps = [{"name": "张三", "age": 23, "gender": true},
		            {"name": "李四", "age": 24, "gender": true},
		            {"name": "王五", "age": 25, "gender": false}];
		        //获取person对象中所有的键和值
		        //for in 循环
		       /* for(var key in person){
		            //这样的方式获取不行。因为相当于  person."name"
		            //alert(key + ":" + person.key);
		            alert(key+":"+person[key]);
		        }*/
		
		       //获取ps中的所有值
		        for (var i = 0; i < ps.length; i++) {
		            var p = ps[i];
		            for(var key in p){
		                alert(key+":"+p[key]);
		            }
		        }		            
```


​			
​			
​			



### (3)JSON数据和Java对象的相互转换

![image-20210116220406024](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210116220406024.png)

* JSON解析器：
	* 常见的解析器：Jsonlib，Gson，fastjson，jackson

1. JSON转为Java对象
	1. 导入jackson的相关jar包
	2. 创建Jackson核心对象 ObjectMapper
	3. 调用ObjectMapper的相关方法进行转换
		1. readValue(json字符串数据,Class)
	
	```java
	ObjectMapper mapper = new ObjectMapper();
	mapper.readValue(json字符串数据,Class);
	mapper.readValue(json字符串数据,Person.class);
	```
	
	
	
2. Java对象转换JSON
	1. 使用步骤：
		1. 导入jackson的相关jar包
		2. 创建Jackson核心对象 ObjectMapper
		3. 调用ObjectMapper的相关方法进行转换
			1. 转换方法：
				* writeValue(参数1，obj):
                    参数1：
                        File：将obj对象转换为JSON字符串，并保存到指定的文件中
                        Writer：将obj对象转换为JSON字符串，并将json数据填充到字符输出流中
                        OutputStream：将obj对象转换为JSON字符串，并将json数据填充到字节输出流中
                * writeValueAsString(obj):将对象转为json字符串

			2. 注解：
				1. @JsonIgnore：排除属性。(在domain中的java对象的成员变量上注解)
				2. @JsonFormat：属性值得格式化
					* @JsonFormat(pattern = "yyyy-MM-dd")

			3. 复杂java对象转换
				1. List：数组
				2. Map：对象格式一致



```java
//java对象装JSON对象
    @Test
    public void test1() throws Exception {
        // 1 创建java对象
        Person p = new Person();
        p.setName("张三");
        p.setAge(18);
        p.setName("男");

        // 2 Jackson的核心对象，ObjectMapper
        ObjectMapper mapper = new ObjectMapper();
        /*
            转换方法：
            1 . writeValue(参数1，obj)
                参数1:
                        File:将obj对象转为JSON对象，并且保存到指定的文件中
                        Write：将obj对象转为JSON对象，并且将JSON数据填充到字符输出流中
                        OutputStream:将obj对象转为JSON对象，并且将JSON数据填充到字节输出流中
            2 . writeValueAsString(obj)   将obj对象转为JSON对象
        */
        String person = mapper.writeValueAsString(p);
        System.out.println(person);
        // 将转换后的JSON对象保存到该文件中
        mapper.writeValue(new File("d://a.txt"),p);
    }
```







## 案例：

```java
* 校验用户名是否存在
	1. 服务器响应的数据，在客户端使用时，要想当做json数据格式使用。有两种解决方案：
		1. $.get(type):将最后一个参数type指定为"json"
		2. 在服务器端设置MIME类型
			response.setContentType("application/json;charset=utf-8");
```







## 今日内容

	1. redis
		1. 概念
		2. 下载安装
		3. 命令操作
			1. 数据结构
		4. 持久化操作
		5. 使用Java客户端操作redis



# Redis



## (1)概念： 

​				redis是一款高性能的NOSQL系列的非关系型数据库

 

![image-20210118101410579](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210118101410579.png)







### 1.什么是NOSQL

​		NoSQL(NoSQL = Not Only SQL)，意即“不仅仅是SQL”，是一项全新的数据库理念，泛指非关系型的数据库。
​		随着互联网web2.0网站的兴起，传统的关系数据库在应付web2.0网站，特别是超大规模和高并发的SNS类型的web2.0纯动态网站已经显得力不从心，暴露了很多难以克服的问题，而非关系型的数据库则由于其本身的特点得到了非常迅速的发展。NoSQL数据库的产生就是为了解决大规模数据集合多重数据种类带来的挑战，尤其是大数据应用难题。



#### 		1.1	NOSQL和关系型数据库比较

​			优点：
​				1）成本：nosql数据库简单易部署，基本都是开源软件，不需要像使用oracle那样花费大量成本购买使用，相比关系型数据库价格便宜。
​				2）查询速度：nosql数据库将数据存储于缓存之中，关系型数据库将数据存储在硬盘中，自然查询速度远不及nosql数据库。
​				3）存储数据的格式：nosql的存储格式是key,value形式、文档形式、图片形式等等，所以可以存储基础类型以及对象或者是集合等各种格式，而数据库则只支持基础类型。
​				4）扩展性：关系型数据库有类似join这样的多表查询机制的限制导致扩展很艰难。

​			缺点：
​				1）维护的工具和资料有限，因为nosql是属于新的技术，不能和关系型数据库10几年的技术同日而语。
​				2）不提供对sql的支持，如果不支持sql这样的工业标准，将产生一定用户的学习和使用成本。
​				3）不提供关系型数据库对事务的处理。

#### 		1.2	非关系型数据库的优势：

​			1）性能NOSQL是基于键值对的，可以想象成表中的主键和值的对应关系，而且不需要经过SQL层的解析，所以性能非常高。
​			2）可扩展性同样也是因为基于键值对，数据之间没有耦合性，所以非常容易水平扩展。

#### 		1.3.	关系型数据库的优势：

​			1）复杂查询可以用SQL语句方便的在一个表以及多个表之间做非常复杂的数据查询。
​			2）事务支持使得对于安全性能很高的数据访问要求得以实现。对于这两类数据库，对方的优势就是自己的弱势，反之亦然。

#### 		1.4.	总结

​			关系型数据库与NoSQL数据库并非对立而是互补的关系，即通常情况下使用关系型数据库，在适合使用NoSQL的时候使用NoSQL数据库，
​			让NoSQL数据库对关系型数据库的不足进行弥补。
​			<font color="red">一般会将数据存储在关系型数据库中，在nosql数据库中备份存储关系型数据库的数据</font>

​	

### 2.主流的NOSQL产品

​		•	键值(Key-Value)存储数据库
​				相关产品： Tokyo Cabinet/Tyrant、Redis、Voldemort、Berkeley DB
​				典型应用： 内容缓存，主要用于处理大量数据的高访问负载。 
​				数据模型： 一系列键值对
​				优势： 快速查询
​				劣势： 存储的数据缺少结构化
​		•	列存储数据库
​				相关产品：Cassandra, HBase, Riak
​				典型应用：分布式的文件系统
​				数据模型：以列簇式存储，将同一列数据存在一起
​				优势：查找速度快，可扩展性强，更容易进行分布式扩展
​				劣势：功能相对局限
​		•	文档型数据库
​				相关产品：CouchDB、MongoDB
​				典型应用：Web应用（与Key-Value类似，Value是结构化的）
​				数据模型： 一系列键值对
​				优势：数据结构要求不严格
​				劣势： 查询性能不高，而且缺乏统一的查询语法
​		•	图形(Graph)数据库
​				相关数据库：Neo4J、InfoGrid、Infinite Graph
​				典型应用：社交网络
​				数据模型：图结构
​				优势：利用图结构相关算法。
​				劣势：需要对整个图做计算才能得出结果，不容易做分布式的集群方案。
​	

### 3.什么是Redis

​		Redis是用C语言开发的一个开源的高性能键值对（key-value）数据库，官方提供测试数据，50个并发执行100000个请求,读的速度是110000次/s,写的速度是81000次/s ，且Redis通过提供多种键值数据类型来适应不同场景下的存储需求，目前为止Redis支持的键值数据类型如下：
​			1) 字符串类型 string
​			2) 哈希类型 hash
​			3) 列表类型 list
​			4) 集合类型 set
​			5) 有序集合类型 sortedset



#### 3.1 redis的应用场景

​			•	缓存（数据查询、短连接、新闻内容、商品内容等等）
​			•	聊天室的在线好友列表
​			•	任务队列。（秒杀、抢购、12306等等）
​			•	应用排行榜
​			•	网站访问统计
​			•	数据过期处理（可以精确到毫秒)
​			•	分布式集群架构中的session分离



## (2)下载安装

1. 官网：https://redis.io
2. 中文网：http://www.redis.net.cn/
3. 解压直接可以使用：
	* redis.windows.conf：配置文件
	* redis-cli.exe：redis的客户端
	* redis-server.exe：redis服务器端





## (3)命令操作(<font color="red" >面试</font>)

#### 1.redis的数据结构：

* redis存储的是：key,value格式的数据，其中key都是字符串，value有5种不同的数据结构
	* value的数据结构：
		1) 字符串类型 string
		2) 哈希类型 hash ： map格式  
		3) 列表类型 list ： linkedlist格式。支持重复元素
		4) 集合类型 set  ： 不允许重复元素
		5) 有序集合类型 sortedset：不允许重复元素，且元素有顺序

![image-20210118104352549](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210118104352549.png)







#### 2.字符串类型 string

1. 存储： set key value
	127.0.0.1:6379> set username zhangsan
	OK
2. 获取： get key
	127.0.0.1:6379> get username
	"zhangsan"
3. 删除： del key
	127.0.0.1:6379> del age
	(integer) 1

#### 3.哈希类型 hash

1. 存储： hset key field value
	127.0.0.1:6379> hset myhash username lisi
	(integer) 1
	127.0.0.1:6379> hset myhash password 123
	(integer) 1
2. 获取： 
	* hget key field: 获取指定的field对应的值
		127.0.0.1:6379> hget myhash username
		"lisi"
	* hgetall key：获取所有的field和value
		127.0.0.1:6379> hgetall myhash
		1) "username"
		2) "lisi"
		3) "password"
		4) "123"
	
3. 删除： hdel key field
	127.0.0.1:6379> hdel myhash username
	(integer) 1

#### 4.列表类型 list:(模拟queue)

![image-20210118105834366](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210118105834366.png)

可以添加一个元素到列表的头部（左边）或者尾部（右边）

1. 添加：
	1. lpush key value: 将元素加入列表左表
		
	2. lpush key value: 将元素加入列表左表
		
		127.0.0.1:6379> lpush myList a
		(integer) 1
		127.0.0.1:6379> lpush myList b
		(integer) 2
		127.0.0.1:6379> rpush myList c
		(integer) 3
2. 获取：
	* lrange key start end ：范围获取
		127.0.0.1:6379> lrange myList 0 -1
		1) "b"
		2) "a"
		3) "c"
3. 删除：
	* lpop key： 删除列表最左边的元素，并将元素返回
	* rpop key： 删除列表最右边的元素，并将元素返回



#### 5.集合类型 set ： 

不允许重复元素

1. 存储：sadd key value
	127.0.0.1:6379> sadd myset a
	(integer) 1
	127.0.0.1:6379> sadd myset a
	(integer) 0
2. 获取：smembers key:获取set集合中所有元素
	127.0.0.1:6379> smembers myset
	1) "a"
3. 删除：srem key value:删除set集合中的某个元素	
	127.0.0.1:6379> srem myset a
	(integer) 1

#### 6.有序集合类型 sortedset：

不允许重复元素，且元素有顺序.每个元素都会关联一个double类型的分数。redis正是通过分数来为集合中的成员进行从小到大的排序。

1. 存储：zadd key score value
	127.0.0.1:6379> zadd mysort 60 zhangsan
	(integer) 1
	127.0.0.1:6379> zadd mysort 50 lisi
	(integer) 1
	127.0.0.1:6379> zadd mysort 80 wangwu
	(integer) 1
2. 获取：zrange key start end [withscores]
	127.0.0.1:6379> zrange mysort 0 -1
	1) "lisi"
	2) "zhangsan"
	3) "wangwu"

	127.0.0.1:6379> zrange mysort 0 -1 withscores
	1) "zhangsan"
	2) "60"
	3) "wangwu"
	4) "80"
	5) "lisi"
	6) "500"
3. 删除：zrem key value
	127.0.0.1:6379> zrem mysort lisi
	(integer) 1



#### 7.通用命令

1. keys * : 查询所有的键
2. type key ： 获取键对应的value的类型
3. del key：删除指定的key value



## (4)持久化

1. redis是一个内存数据库，当redis服务器重启，获取电脑重启，数据会丢失，我们可以将redis内存中的数据持久化保存到硬盘的文件中。
2. redis持久化机制：
	1. RDB：默认方式，不需要进行配置，默认就使用这种机制
		* 在一定的间隔时间中，检测key的变化情况，然后持久化数据
		1. 编辑redis.windwos.conf文件
			```
			#   after 900 sec (15 min) if at least 1 key changed
			save 900 1
			#   after 300 sec (5 min) if at least 10 keys changed
			save 300 10
			#   after 60 sec if at least 10000 keys changed
			save 60 10000
			```
			
			
			
		2. 重新启动redis服务器，并指定配置文件名称(用cmd在文件所在位置打开redis-server.exe)
			D:\JavaWeb2018\day23_redis\资料\redis\windows-64\redis-2.8.9>redis-server.exe redis.windows.conf	
		
	2. AOF：日志记录的方式，可以记录每一条命令的操作。可以每一次命令操作后，持久化数据
		1. 编辑redis.windwos.conf文件
			
			```
			appendonly no（关闭aof） --> appendonly yes （开启aof）
							
			# appendfsync always ： 每一次操作都进行持久化
			appendfsync everysec ： 每隔一秒进行一次持久化
			# appendfsync no	 ： 不进行持久化
			```
			
			
			

## (5)Java客户 端 Jedis

* Jedis: 一款java操作redis数据库的工具.（类似JDBC链接池）
* 使用步骤：
	1. 下载jedis的jar包
	
	2. 使用
	
	```
		//1. 获取连接
	Jedis jedis = new Jedis("localhost",6379);
//2. 操作
	jedis.set("username","zhangsan");
		//3. 关闭连接
		jedis.close();
	```
	
	​	





## (6)Jedis操作各种redis中的数据结构

### 1)字符串类型 string

jedis.setex:hehe键值对存入redis，并且20秒后自动删除该键值对
			

```java
		 //1. 获取连接
        Jedis jedis = new Jedis();//如果使用空参构造，默认值 "localhost",6379端口
        //2. 操作
        //存储
        jedis.set("username","zhangsan");
        //获取
        String username = jedis.get("username");
        System.out.println(username);

        //可以使用setex()方法存储可以指定过期时间的 key value
        jedis.setex("activecode",20,"hehe");//将activecode：hehe键值对存入redis，并且20秒后自动删除该键值对

        //3. 关闭连接
        jedis.close();
```




### 2) 哈希类型 hash ： map格式  





```java

		
		2) 哈希类型 hash ： map格式  
			hset
			hget
			hgetAll
			//1. 获取连接
	        Jedis jedis = new Jedis();//如果使用空参构造，默认值 "localhost",6379端口
	        //2. 操作
	        // 存储hash
	        jedis.hset("user","name","lisi");
	        jedis.hset("user","age","23");
	        jedis.hset("user","gender","female");
	
	        // 获取hash
	        String name = jedis.hget("user", "name");
	        System.out.println(name);
	        // 获取hash的所有map中的数据
	        Map<String, String> user = jedis.hgetAll("user");
	
	        // keyset
	        Set<String> keySet = user.keySet();
	        for (String key : keySet) {
	            //获取value
	            String value = user.get(key);
	            System.out.println(key + ":" + value);
	        }
	
	        //3. 关闭连接
	        jedis.close();
```


​		





### 3) 列表类型 list ： linkedlist格式。支持重复元素


```java

			lpush / rpush
			lpop / rpop
			lrange start end : 范围获取
			
			 //1. 获取连接
	        Jedis jedis = new Jedis();//如果使用空参构造，默认值 "localhost",6379端口
	        //2. 操作
	        // list 存储
	        jedis.lpush("mylist","a","b","c");//从左边存
	        jedis.rpush("mylist","a","b","c");//从右边存
	
	        // list 范围获取
	        List<String> mylist = jedis.lrange("mylist", 0, -1);
	        System.out.println(mylist);
	        
	        // list 弹出
	        String element1 = jedis.lpop("mylist");//c
	        System.out.println(element1);
	
	        String element2 = jedis.rpop("mylist");//c
	        System.out.println(element2);
	
	        // list 范围获取
	        List<String> mylist2 = jedis.lrange("mylist", 0, -1);
	        System.out.println(mylist2);
	
	        //3. 关闭连接
	        jedis.close();
```





### 4) 集合类型 set  ： 不允许重复元素


```java
		4) 集合类型 set  ： 不允许重复元素
			sadd
			smembers:获取所有元素

			//1. 获取连接
	        Jedis jedis = new Jedis();//如果使用空参构造，默认值 "localhost",6379端口
	        //2. 操作
	         // set 存储
	        jedis.sadd("myset","java","php","c++");
	
	        // set 获取
	        Set<String> myset = jedis.smembers("myset");
	        System.out.println(myset);
	
	        //3. 关闭连接
	        jedis.close();
```

​		

### 5) 有序集合类型 sortedset：不允许重复元素，且元素有顺序

```java
5) 有序集合类型 sortedset：不允许重复元素，且元素有顺序
			zadd
			zrange

			//1. 获取连接
	        Jedis jedis = new Jedis();//如果使用空参构造，默认值 "localhost",6379端口
	        //2. 操作
	        // sortedset 存储
	        jedis.zadd("mysortedset",3,"亚瑟");
	        jedis.zadd("mysortedset",30,"后裔");
	        jedis.zadd("mysortedset",55,"孙悟空");
	
	        // sortedset 获取
	        Set<String> mysortedset = jedis.zrange("mysortedset", 0, -1);
	
	        System.out.println(mysortedset);
	        //3. 关闭连接
	        jedis.close();
```


​		



## (7)jedis连接池： JedisPool

* 使用：
	1. 创建JedisPool连接池对象
	2. 调用方法 getResource()方法获取Jedis连接


```java
			//0.创建一个配置对象
	        JedisPoolConfig config = new JedisPoolConfig();
	        config.setMaxTotal(50);
	        config.setMaxIdle(10);
	
	        //1.创建Jedis连接池对象(可以空参默认使用)
	        JedisPool jedisPool = new JedisPool(config,"localhost",6379);
	
	        //2.获取连接
	        Jedis jedis = jedisPool.getResource();
	        //3. 使用
	        jedis.set("hehe","heihei");
	        //4. 关闭 归还到连接池中
	        jedis.close();
```


## (8)连接池工具类

```java
* 连接池工具类
	/**
		JedisPool工具类
			加载配置文件，配置连接池的参数
			提供获取链接的方法
	*/
    public class JedisPoolUtils {
        private static JedisPool jedisPool;

        static{
            //读取配置文件
            InputStream is = JedisPoolUtils.class.getClassLoader().getResourceAsStream("jedis.properties");
            //创建Properties对象
            Properties pro = new Properties();
            //关联文件
            try {
                pro.load(is);
            } catch (IOException e) {
                e.printStackTrace();
            }
            //获取数据，设置到JedisPoolConfig中
            JedisPoolConfig config = new JedisPoolConfig();
            config.setMaxTotal(Integer.parseInt(pro.getProperty("maxTotal")));
            config.setMaxIdle(Integer.parseInt(pro.getProperty("maxIdle")));

            //初始化JedisPool
            jedisPool = new JedisPool(config,pro.getProperty("host"),Integer.parseInt(pro.getProperty("port")));
        }
        /**
		* 获取连接方法
		*/
        public static Jedis getJedis(){
            return jedisPool.getResource();
        }
    }
```

通过链接池工具类获取

```java
public void test(){
    // 通过链接池工具类获取
    Jedis jedis = JedisPoolUtils.getJedis();
    // 使用
    jedis.set("hehe","heihei");
    // 关闭，归还给链接池
    jedis.close();
}

```

​				



## 案例：

```tex
案例需求：
	1. 提供index.html页面，页面中有一个省份 下拉列表
	2. 当 页面加载完成后 发送ajax请求，加载所有省份
```

![image-20210118172928038](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210118172928038.png)



```
注意：使用redis缓存一些不经常发生变化的数据。

* 数据库的数据一旦发生改变，则需要更新缓存。
  * 数据库的表执行 增删改的相关操作，需要将redis缓存数据情况，再次存入
  * 在service对应的增删改方法中，将redis数据删除。
```

![image-20210118201659795](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210118201659795.png)











# Maven 基础

## 1.什么是 Maven

Maven 的正确发音是[ˈmevən]，而不是“马瘟”以及其他什么瘟。Maven 在美国是一个口语化的词 语，代表专家、内行的意思。 

一个对 Maven 比较正式的定义是这么说的：Maven 是一个项目管理工具，它包含了一个项目对象模 型 (POM：Project Object Model)，一组标准集合，一个项目生命周期(Project Lifecycle)，一个依赖管 理系统(Dependency Management System)，和用来运行定义在生命周期阶段(phase)中插件(plugin)目标 (goal)的逻辑。



### 1.2 Maven 能解决什么问题

​	可以用更通俗的方式来说明。我们知道，项目开发不仅仅是写写代码而已，期间会伴随着各种 必不可少的事情要做，下面列举几个感受一下：

1、我们需要引用各种 jar 包，尤其是比较大的工程，引用的 jar 包往往有几十个乃至上百个， 每用 到一种 jar 包，都需要手动引入工程目录，而且经常遇到各种让人抓狂的 jar 包冲突，版本冲突。 

2、我们辛辛苦苦写好了 Java 文件，可是只懂 0 和 1 的白痴电脑却完全读不懂，需要将它编译成二 进制字节码。好歹现在这项工作可以由各种集成开发工具帮我们完成，Eclipse、IDEA 等都可以将代 码即时编译。当然，如果你嫌生命漫长，何不铺张，也可以用记事本来敲代码，然后用 javac 命令一 个个地去编译，逗电脑玩。

3、世界上没有不存在 bug 的代码，计算机喜欢 bug 就和人们总是喜欢美女帅哥一样。为了追求美为 了减少 bug，因此写完了代码，我们还要写一些单元测试，然后一个个的运行来检验代码质量。 

4、再优雅的代码也是要出来卖的。我们后面还需要把代码与各种配置文件、资源整合到一起，定型 打包，如果是 web 项目，还需要将之发布到服务器，供人蹂躏。 

试想，如果现在有一种工具，可以把你从上面的繁琐工作中解放出来，能帮你构建工程，管理 jar 包，编译代码，还能帮你自动运行单元测试，打包，生成报表，甚至能帮你部署项目，生成 Web 站 点，你会心动吗？Maven 就可以解决上面所提到的这些问题。



### 1.3 Maven 的优势举例

前面我们通过 Web 阶段项目，要能够将项目运行起来，就必须将该项目所依赖的一些 jar 包添加到 工程中，否则项目就不能运行。试想如果具有相同架构的项目有十个，那么我们就需要将这一份 jar 包复制到十个不同的工程中。我们一起来看一个 CRM项目的工程大小。 使用传统 Web 项目构建的 CRM 项目如下：

![image-20210119101044247](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119101044247.png)

原因主要是因为上面的 WEB 程序要运行，我们必须将项目运行所需的 Jar 包复制到工程目录中，从 而导致了工程很大。 同样的项目，如果我们使用 Maven 工程来构建，会发现总体上工程的大小会少很多。如下图:

![image-20210119101058989](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119101058989.png)



## 2.Maven 的两个精典作用

### (1)Maven 的依赖管理(对jar包的管理)

Maven 的一个核心特性就是依赖管理。当我们涉及到多模块的项目（包含成百个模块或者子项目），管理依赖就变成 一项困难的任务。Maven 展示出了它对处理这种情形的高度控制。

![image-20210119101230744](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119101230744.png)

通过分析发现：maven 工程中不直接将 jar 包导入到工程中，而是通过在 pom.xml 文件中添加所需 jar 包的坐标，这样就很好的避免了 jar 直接引入进来，在需要用到 jar 包的时候，只要查找 pom.xml 文 件，再通过 pom.xml 文件中的坐标，到一个专门用于”存放 jar 包的仓库”(maven 仓库)中根据坐标从 而找到这些 jar 包，再把这些 jar 包拿去运行。 那么问题来了 

第一：”存放 jar 包的仓库”长什么样？ 

第二：通过读取 pom.xml 文件中的坐标，再到仓库中找到 jar 包，会不会很慢？从而导致这种方式 不可行！



第一个问题：存放 jar 包的仓库长什么样，这一点我们后期会分析仓库的分类，也会带大家去看我们 的本地的仓库长什么样。 

第二个问题：通过 pom.xml 文件配置要引入的 jar 包的坐标，再读取坐标并到仓库中加载 jar 包，这 样我们就可以直接使用 jar 包了，为了解决这个过程中速度慢的问题，maven 中也有索引的概念，通 过建立索引，可以大大提高加载 jar 包的速度，使得我们认为 jar 包基本跟放在本地的工程文件中再 读取出来的速度是一样的。这个过程就好比我们查阅字典时，为了能够加快查找到内容，书前面的 目录就好比是索引，有了这个目录我们就可以方便找到内容了，一样的在 maven 仓库中有了索引我 们就可以认为可以快速找到 jar 包。



### (2)项目的一键构建

我们的项目，往往都要经历编译、测试、运行、打包、安装 ，部署等一系列过程。 什么是构建？ 

指的是项目从编译、测试、运行、打包、安装 ，部署整个过程都交给 maven 进行管理，这个过程称为构建。 

一键构建 指的是整个构建过程，使用 maven 一个命令可以轻松完成整个工作。

![image-20210119101416933](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119101416933.png)





## 3.Maven 仓库

### (1)Maven 仓库的分类

​	maven 的工作需要从仓库下载一些 jar 包，如下图所示，本地的项目 A、项目 B 等都会通过 maven 软件从远程仓库（可以理解为互联网上的仓库）下载 jar 包并存在本地仓库，本地仓库 就是本地文 件夹，当第二次需要此 jar 包时则不再从远程仓库下载，因为本地仓库已经存在了，可以将本地仓库 理解为缓存，有了本地仓库就不用每次从远程仓库下载了。



* 本地仓库 ：用来存储从远程仓库或中央仓库下载的插件和 jar 包，项目使用一些插件或 jar 包， 优先从本地仓库查找 默认本地仓库位置在 ${user.dir}/.m2/repository，${user.dir}表示 windows 用户目录。( MAVE_HOME/conf/settings.xml)

* 远程仓库：如果本地需要插件或者 jar 包，本地仓库没有，默认去远程仓库下载。 远程仓库可以在互联网内也可以在局域网内。

* 中央仓库 ：在 maven 软件中内置一个远程仓库地址 http://repo1.maven.org/maven2 ，它是中 央仓库，服务于整个互联网，它是由 Maven 团队自己维护，里面存储了非常全的 jar 包，它包 含了世界上大部分流行的开源项目构件。



![image-20210119101742929](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119101742929.png)





在 MAVE_HOME/conf/settings.xml 文件中配置本地仓库位置（maven 的安装目录下）：

![image-20210119101818155](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119101818155.png)

打开 settings.xml文件，配置如下：

![image-20210119101832195](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119101832195.png)

<font color="red">本电脑的本地仓库放在D:\my_maven\maven_repository</font>



(2)全局 setting 与用户 setting

maven 仓库地址、私服等配置信息需要在 setting.xml 文件中配置，分为全局配置和用户配置。 

在 maven 安装目录下的有 conf/setting.xml 文件，此 setting.xml 文件用于 maven 的所有 project 项目，它作为 maven 的全局配置。 

如需要个性配置则需要在用户配置中设置，用户配置的 setting.xml 文件默认的位置在：${user.dir} /.m2/settings.xml 目录中,${user.dir} 指 windows 中的用户目录。 

maven 会先找用户配置，如果找到则以用户配置文件为准，否则使用全局配置文件。

![image-20210119103117635](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119103117635.png)





## 4.Maven 工程的认识

![image-20210119104042052](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119104042052.png)

### (1) Maven 工程的目录结构

![image-20210119104048284](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119104048284.png)



作为一个 maven 工程，它的 src 目录和 pom.xml 是必备的。 进入 src 目录后，我们发现它里面的目录结构如下：

![image-20210119104112858](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119104112858.png)

src/main/java —— 存放项目的.java 文件 

src/main/resources —— 存放项目资源文件，如 spring, hibernate 配置文件

src/test/java —— 存放所有单元测试.java 文件，如 JUnit 测试类 src/test/resources —— 测试资源文件 target —— 项目输出位置，编译后的 class 文件会输出到此目录 

pom.xml——maven 项目核心配置文件 

注意：如果是普通的 java 项目，那么就没有 webapp 目录。





### (2)Maven 工程的运行

进入 maven 工程目录（当前目录有 pom.xml 文件），运行 tomcat:run 命令。









## 5.Maven 常用命令 

我们可以在 cmd 中通过一系列的 maven 命令来对我们的 maven-helloworld 工程进行编译、测试、运 行、打包、安装、部署。

我们在用maven构建java项目时，最常用的打包命令有**mvn package、mvn install、mvn deploy**，这三个命令都可完成打jar包或war（当然也可以是其它形式的包）的功能。

但这三个命令还是有区别的，可以从执行这三个命令的输出结果来分析看，各自所执行的maven的生命周期不同。

通过执行这三个命令的输出结果我们可以看出三者的区别在于包函的maven生命的阶段和执行目标(goal)不同。

maven生命周期（Lifecycle）由各个阶段组成，每个阶段由maven的插件plugin来执行完成。

生命周期（Lifecycle）主要包括clean、resources、complie、install、pacakge、testResources、testCompile、deploy等，其中带test开头的都是用业编译测试代码或运行单元测试用例的。

仔细查看三个命令执行输出的结果，可以发现，

- **mvn clean package** 依次执行了clean、resources、compile、testResources、testCompile、test、jar(打包)等７个阶段。
- **mvn clean install** 依次执行了clean、resources、compile、testResources、testCompile、test、jar(打包)、install等 8个阶段。
- **mvn clean deploy** 依次执行了clean、resources、compile、testResources、testCompile、test、jar(打包)、install、deploy等９个阶段。

由上面的分析可知主要区别如下，

- **package** 命令完成了项目编译、单元测试、打包功能，但没有把打好的可执行jar包（war包或其它形式的包）布署到本地maven仓库和远程maven私服仓库
- **install** 命令完成了项目编译、单元测试、打包功能，同时把打好的可执行jar包（war包或其它形式的包）布署到本地maven仓库，但没有布署到远程maven私服仓库
- **deploy** 命令完成了项目编译、单元测试、打包功能，同时把打好的可执行jar包（war包或其它形式的包）布署到本地maven仓库和远程maven私服仓库

### 1)compile

compile 是 maven 工程的编译命令，作用是将 src/main/java 下的文件编译为 class 文件输出到 target 目录下。 

cmd 进入命令状态，执行

```
 mvn compile
```

如下图提示成功：

![image-20210119104701287](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119104701287.png)

查看 target 目录，class 文件已生成，编译完成。

![image-20210119105401953](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119105401953.png)





### 2)clean 

clean是 maven 工程的清理命令，执行 clean 会删除 target 目录及内容。

```
mvn clean
```



### 3)test

test 是 maven 工程的测试命令 mvn test，会执行 src/test/java 下的单元测试类。 

cmd 执行 

```
mvn test
```

 执行 src/test/java 下单元测试类，下图为测试结果，运行 1 个测试用例，全部成功。

![image-20210119105323677](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119105323677.png)



### 4)package 

package 是 maven 工程的打包命令，对于 java 工程执行 package 打成 jar 包，对于 web 工程打成 war 包。

![image-20210119105258374](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119105258374.png)





### 5)install 

install 是 maven 工程的安装命令，<font color="red">执行 install 将 maven 打成 jar 包或 war 包发布到本地仓库。 </font>(区别)

从运行结果中，可以看出： 当后面的命令执行时，前面的操作过程也都会自动执行

![image-20210119105611636](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119105611636.png)











## 6.Maven 指令的生命周期

maven 对项目构建过程分为三套相互独立的生命周期，请注意这里说的是“三套”，而且“相互独立”， 这三套生命周期分别是： 

* Clean Lifecycle 在进行真正的构建之前进行一些清理工作。 

* Default Lifecycle 构建的核心部分，编译，测试，打包，部署等等。 

* Site Lifecycle 生成项目报告，站点，发布站点。



![image-20210119112730013](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119112730013.png)





## 7.maven 的概念模型

Maven 包含了一个项目对象模型 (Project Object Model)，一组标准集合，一个项目生命周期(Project Lifecycle)，一个依赖管理系统(Dependency Management System)，和用来运行定义在生命周期阶段 (phase)中插件(plugin)目标(goal)的逻辑。

![image-20210119112856824](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119112856824.png)

详细一点（依赖管理+一键构建）：

![image-20210119113437162](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20210119113437162.png)



* 项目对象模型 (Project Object Model) 

一个 maven 工程都有一个 pom.xml 文件，通过 pom.xml 文件定义项目的坐标、项目依赖、项目信息、 插件目标等。



* 依赖管理系统(Dependency Management System) 

通过 maven 的依赖管理对项目所依赖的 jar 包进行统一管理。 比如：项目依赖 junit4.9，通过在 pom.xml 中定义 junit4.9 的依赖即使用 junit4.9，如下所示是 junit4.9 的依赖定义：

```xml
<!-- 依赖关系 -->
	<dependencies>
		<!-- 此项目运行使用 junit，所以此项目依赖 junit -->
		<dependency>
            <!-- junit 的项目名称 -->
            <groupId>junit</groupId>
            <!-- junit 的模块名称 -->
            <artifactId>junit</artifactId>
            <!-- junit 版本 -->
            <version>4.9</version>
            <!-- 依赖范围：单元测试时使用 junit -->
            <scope>test</scope>
	</dependency>
```



* 一个项目生命周期(Project Lifecycle) 

使用 maven 完成项目的构建，项目构建包括：清理、编译、测试、部署等过程，maven 将这些 过程规范为一个生命周期，如下所示是生命周期的各各阶段：



* 一组标准集合 

maven 将整个项目管理过程定义一组标准，比如：通过 maven 构建工程有标准的目录结构，有 标准的生命周期阶段、依赖管理有标准的坐标定义等。



* 插件(plugin)目标(goal)  

maven 管理项目生命周期过程都是基于插件完成的。



































