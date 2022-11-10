# HTML5

## 1.HTML5概述

是**超文本标记语言**；一系列用来制作现代富web内容的相关技术；**HTML+CSS+JAVAScript**；特点：向下兼容；用户至上；化繁为简；无插件范式；访问通用性；引入语义；引入原生媒体支持；引入可编程内容；

## 2.规范  

**.html结尾**

标签名，类名，标签属性和大部分属性值统一**用小写**

```html
<!DOCTYPE html>   //文档类型声明
<html lang="en">     //文档开始（页面中的最大的标签，根标签）
<head>              //包含文档元数据开始
	<meta charset="UTF-8">     //声明字符编码
	<title>文件命名</title>     //设置网页标题
<body>                         //表示HTML文档内容
<a href="http://www.baidu.com">百度</a>    //一个超链接元素
</body>                          
</head> 
</html>                            //文档结束

```

lang：语言种类；en为英文；zh-cn为中文；写在<html>中;

<mate charset="utf-8">：charset为**字符集**；UTF-8为目前最常用的字符集编码方式；

GB2312为简体中文；BIG5为繁体中文；GBK包含全部中文字符，是GB2312的扩展，加入了对繁体字的支持，兼容GB2312；

## 3.元素

**1.常规元素**（双标签）

```html
<body>（开始标签）
    我是文字
</body>（结束标签，/为关闭符）
```

​	**标签关系：**

​	1.嵌套关系：子标签采取缩进

```html
<head>
    <title> </title>
</head>
```

​	2.并列关系

```HTML
<head></head>
<body></body>
```

**2.空元素**（单标签）

```html
<br>
```

## 4.图像标签

**img**

|  属性  |           说明           |
| :----: | :----------------------: |
|  src   |        图像的路径        |
|  alt   | 图像无法显示时的代替文本 |
| title  |   鼠标悬停时显示的内容   |
| width  |      设置图像的宽度      |
| height |      设置图像的高度      |
| border |    设置图像边框的宽度    |

属性不区分顺序；

## 5.文本标签汇总

***（注释：Ctrl+?）***

### (1).加粗

**b元素**：加粗；  **strong元素**：加粗； 

### (2).换行

**br元素**：强制换行；**wbr元素**：安全换行（用于英文）；

### (3).倾斜

***i元素***：倾斜；***em元素***：倾斜；

### (4).删除线

**s元素**：删除线（不准确删除）；**del元素**：删除线（删除相关文字）；

### (5).下划线

**u元素**：<u>下划线</u>；（不建议使用）

**ins元素**：<u>下划线</u>

### (6).添加文本，小号字体，上下标，双引号

**ins元素**：添加一段文本；

**small元素**：添加小号字体；

**sub元素**：下标；**sup元素**：上标；

**q元素**：加双引号；

### (7).其他

**code元素**：计算机代码片段；**var元素**：编程语言中的变量；**samp元素**：计算机的输出；**kdb**：元素用户的输入；（上述皆为英文范畴，必须写<html lang="en">体现效果！！！

**abbr元素**：缩写；

***dfn元素***：定义术语（***倾斜***）；

**cite元素**：引用标题（**加粗**）；

**mark元素**：标记文字（黄底黑字）；

**time元素**：表示日期和时间；

https://www.bilibili.com/video/BV1Hx411C7dK?p=3

**h1~h6为标题标签**：**加粗**且独占一行；字体大小**依次减小**；

### (8).加拼音

**ruby元素**：rp与/rp中间写括号，rt与/rt中间写拼音，可以实现**在生字正上方加拼音的效果**

```html
ruby元素：这是<ruby>饕(tao)餮(tie)</ruby>
         <ruby>饕<rp>(</rp><rt>tao</rt><rp>)</rp>餮<rp>(</rp><rt>tie</rt><rp>)</rp></ruby>
         <ruby style="font-size:100px ;">可以改变字体大小
```

### (9).文字输出方向

bdo元素：文字输出的方向；

```
<bdo dir="rtl">HTML 5</bdo>表示从右向左输出
<bdo dir="ltr">HTML 5</bdo>表示从左向右输出
```

## 6.超链接与属性

### (1).href是必须属性

外部链接**http://开头**；内部链接；空链接**#**；图像链接；

```html
<h4>外部链接</h4>
	<a href="https://www.baidu.com" target="_blank">百度</a>
	<a href="https://www.baidu.com" target="_parent">百度</a>
	<a href="https://www.baidu.com" target="_top">百度</a>

	<h4>内部链接</h4>
	<a href="demo.html">胡歌</a>

	<h4>空链接</h4>
	<a href="#">霍建华</a>

	<h4>图像链接</h4>
	<a href="http://www.baidu.com"> <img src="timg.jpg"></a>
```

### (2).target属性

告诉浏览器希望将链接的资源显示在哪里（打开方式）。

_blank：在新窗口或者便签页中打开文档；

_parent：在父窗框组（frameset）中打开文档；

_self：在当前窗口打开文档（默认）；

_top：在顶层窗口打开文档；

```html
<a href="https://www.baidu.com" target="_blank">百度</a>
```

### (3).相对和绝对路径

根目录：打开文件夹的第一个目录叫根目录；

#### 绝对路径

以file：///开头，输入文件所在地址；如果将文件更换盘符或者更换电脑，无法再次使用；（不提倡使用）

#### 相对路径

必须在**同一个磁盘或者目录下**；在同一个目录下的直接属性值就是被链接的文件名.后缀名；同一个主目录下的多个子目录，使用目录结构语法；

目录结构语法

| 存储位置     | 引用方法           |
| ------------ | ------------------ |
| 同一个子目录 | 文件名.html        |
| 在子目录     | xxx/文件名.html    |
| 在孙子目录   | xxx/xxx/文件名html |
| 在父目录     | ../文件名.html     |
| 在爷爷目录   | ../../文件名.html  |

## 7.分组标签

### div元素（布局无语意）

一行只能放一个div的内容；

### **span元素**（布局无语意）

一行可以放好多个span；

### (2).段落标签

```html
<p>
    段落文字
</p>
```

### (3).blockquote

引用大**段**他处内容（存在缩进）

```
<blocaquote></blocaquote>
```

### (4).格式化展示

pre：展示格式化内容：（简单的排版）


### (5).添加水平线

hr：添加一条水平线；

## 8.列表标签

### (1).添加无序列表

<ul></ul>:添加无序列表出现黑点,ul内部只能写li
```html
<ul>
	<li>张三</li>              
	<li>李四</li>
	<li>王五</li>
    <li>马六</li>
</ul>
```

### (2).添加有序列表

<ol></ol>：添加有序列表：出现排序;ol内部只能写li
```html
<ol>
		<li>张三</li>
		<li>李四</li>
		<li>王五</li>
		<li>马六</li>
</ol>
```

**ol元素属性：**

| 属性名称 | 说明                                        |
| -------- | ------------------------------------------- |
| start    | 从第几个序列开始统计：<ol  start ="2">      |
| reversed | 是否倒序排列<ol  reversed>                  |
| type     | 表示列表的编号类型，值分别为1、a、A、i、I； |

**li元素属性**：  value   ： 强行设置某个项目的编号；

### (3).生成自定义列表：

dl     dt     dd

```html
	<dl>
		<dt>这是第一份文件</dt>          写标题
		<dd>这是第一份文件的详细内容1</dd>      内容
		<dd>这是第一份文件的详细内容2</dd>
	</dl>

	<dl>
		<dt>这是第二份文件</dt>
		<dd>这是第二份文件的详细内容1</dd>
		<dd>这是第二份文件的详细内容2</dd>
	</dl>
```

### (4).使用插图

 figure  figcaption

```html
<figure>
		<figcaption>这是一张图片</figcaption>
嵌入		<img src="四六级海报.png">
</figure>
```

## 9.表格标签

### (1).table标签

table的属性

​	**border**="1"可以**来输出边框**；

​	**cellspacing**：设置单元格与单元格边框之间的空白间距；（像素值默认为1）

​	**cellpadding**：设置单元格内容与单元格边框之间的空白间距；（像素值默认为2）

​	**align**：设置单元格内容在**网页**中的**对齐**方式：left左对齐；center居中；right右对齐；

​	height：表格的高度；

​	width：表格的宽度；

### (2).行标签

​	<tr>为**同一行**的内容，**每有一个<tr>表示一行**；

### (3).单元格标签

​	<td>为**同一个单元格**的内容；

### (4).标题

<th>（单元格）**添加标题且文字加粗居中**；

### (5).合并单元格

<th>与<td>有**合并**属性：**clospan   rowspan**；

```html
<table border="1" >
		<caption>个人简介</caption>
		<tr>
			<td>刘德华</td>
			<td>男</td>
			<td>18</td>
			<td rowspan="2">照片</td>
		</tr>
		<tr>
			<td>身高180</td>
			<td>汉族</td>
			<td>已婚</td>
			
		</tr>
		<tr>
			<td>个人作品</td>
			<td colspan="3"></td>
		</tr>
		<tr>
			<td>个人简介</td>
			<td colspan="3"></td>
		</tr>
	</table>
```

### (6).控制行颜色

<tr style="background:red;">

```html
<td colspan="3">共计：两人</td>      （横向几个单元格写几）
<th rowspan="4">基本情况</th>       （纵向几个单元格写几） 
```

### (7).添加表头

thead的内部必须要有tr标签；

```html
<thead>
			<tr>
			<th>姓名</th>
			<th>性别</th>
			<th>婚否</th> 
		</tr>
</thead>
```

### (8).添加表脚

```html
<tfoot>
			<th colspan="4">hahaha</th>
</tfoot>
```

### (9).添加**表主体**

### (10).添加**表格标题**（不进入表格）

```
<caption>这是一个表格</caption> 
```

### (8).**设置列**

```html
<colgroup style="background:yellow;" span="1"></colgroup>(设置第一列的颜色);
<colgroup style="background:yellow;" span="1"></colgroup>(设置第二列的颜色)
```

7.更加灵活的设置列：<col>;与<colgroup>一起使用；

## 10.文档标签

1.<header>:存放页面标头——LOGO，标题，导航

2.<footer>:页面尾部：版权声明，友情链接等；

3.<h1~h6>添加标题；1~6表示字体的不同大小；

4.<hgroup>：组合标题；

5.<section>：文档主题部分；

6.<nav>：添加导航；

7.<article>：添加一个独立成篇的文档；

8.<aside>：添加注释栏；

9.<address>：表示文档或artical元素的联系信息；（主流浏览器不支持）

10.<details>：生成详情区域；<summary>：元素在其内部生成说明标签；（主流浏览器不支持）

## 11.嵌入标签

外部内容插入

1.<img>：插入图像；

| 属性名称 | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| src      | 嵌入图像的URL(每一信息资源都有统一的且在网上唯一的[地址](https://baike.baidu.com/item/地址/80420)，该地址就叫URL) |
| alt      | 当图片不加载的时候显示备用内容                               |
| width    | 定义图片的长度（单位为像素）                                 |
| height   | 定义图片的高度（单位为像素）                                 |
| ismap    | 创建服务区端分区响应图                                       |
| usemap   | 关联<map>元素                                                |

2.<iframe>：嵌入另一个文档；

```html
<a href="https://www.baidu.com" target="in">百度</a> 
<a href="http://www.haosou.com" target="in">好搜</a>

	<br>

	<iframe src="http://www.soso.com" width="800" height="600" name="in"></iframe>
```

src属性表示初始化页面时的页面；name表示target的名称；

3.<embed>：嵌入插件内容；

```html
<embed src="写入地址" type="类型" width="800" height="600"></embed>
```

src属性处写插件内容的地址；type为类型；width写宽度；height写高度；

4.<object>，<param>：插入图片，音频，视频等

5.<progress>：进度条；

6.<meter>：样式；low最小值；high最大值；optimum最佳值；

## 12.音频和视频

主流视频容器支持的格式为：.avi；.flv；**.mp4**；.mkv；**.ogg**；**.webm**；

| 容器格式     | 视频编解码 | 音频编解码 | IE9+ | Firefox5 | Chrome13+ |
| ------------ | ---------- | ---------- | ---- | -------- | --------- |
| WebM（免费） | VP8        | Vorbis     | ×    | √        | √         |
| OGG          | Theora     | Vorbis     | ×    | √        | √         |
| MPEG-4       | H.264      | AAC        | √    | ×        | 疑问？    |

**vedio元素：视频元素；**

| 属性名称 | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| src      | 视频资源的URL                                                |
| widht    | 视频宽度                                                     |
| height   | 视频高度                                                     |
| autoplay | 设置后；表示**立即开始播放**视频                             |
| preload  | 设置后，表示**预先载入**视频；metadata：只加载第一帧；auto：尽快下载； |
| controls | 设置后，表示**显示播放插件**                                 |
| loop     | 设置后，表示**反复播放**视频                                 |
| muted    | 设置后，表示视频处于**静音**状态                             |
| poster   | 指定视频数据载入时**显示的**图片                             |

**audio：音频元素**；**.mp3；.m4a；.wav；**

| 属性名称 | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| src      | 视频资源的URL                                                |
| autoplay | 设置后；表示**立即开始播放**视频                             |
| preload  | 设置后，表示**预先载入**视频；metadata：只加载第一帧；auto：尽快下载； |
| controls | 设置后，表示**显示播放插件**                                 |

## 13.表单标签

### 1**.form标签**（定义）

**定义表单；**

| 元素名称            | 说明                                                         |
| ------------------- | ------------------------------------------------------------ |
| action              | 表示表单提交的页面                                           |
| method              | 表示表单的请求方式：有POST和GET两种，默认GET                 |
| enctype             | 表示浏览器对发送给服务器的数据采取的编码格式。有三种：application/x-www-form-urlencode(默认编码，不能将文件上传到服务器)、multipart/form-data(用于上传文件到服务器)、text/plain(未规范的编码，不建议使用，不同浏览器理解不同) |
| name                | 设置表单名称，以便程序调用                                   |
| **target**（见6.2） | 设置提交时候的**目标位置**：（均有下方小横线）blank、parent、self、top、 |
| autocomplete        | 设置浏览器记住用户输入的数据，实现自动完成表单。默认为on自动完成，如果不想自动完成则设置off |
| novalidate          | 设置是否执行客户端数据有效性检查                             |

#### **（1.）input标签**

表示用户输入数据；

| 属性名称     | 说明                                            |
| ------------ | ----------------------------------------------- |
| autofocus    | 让光标聚焦在莫格input元素上，让用户**直接输入** |
| disabled     | 禁用input元素                                   |
| autocomplete | 单独设置input元素的**自动完成功能**             |
| form         | 让表单**以外**的元素和指定的表单**挂钩提交**    |
| type         | input元素的类型                                 |
| name         | 定义input元素的名称，以便接收相应的值           |
| value        | 默认文本值                                      |
| size         | 插件在网页中的显示宽度                          |

**label**1.直接包含input，鼠标点击名称，光标直接定位指定表单，直接输入；2.还可以通过for和id控制

```html
<label for="user">用户名</label>
	<input id="user" name="user" value="bbb">

<label>
		电子邮件<input name="email">
</label>
```

##### **type的属性总汇**

| 属性名称                                          | 说明                                             |
| ------------------------------------------------- | ------------------------------------------------ |
| text                                              | 一个单行文本框                                   |
| password                                          | 隐藏字符的密码框                                 |
| search                                            | 搜索框，在某些浏览器键入内容会出现叉标记取消     |
| submit、reset、button                             | 生成一个提交按钮，重置按钮，普通按钮             |
| number、range                                     | 只能输入数字的框，只能输入在一个数值范围的框     |
| checkbox、radio                                   | 复选框，用户勾选框；单选框，只能在几个中间选一个 |
| image、color                                      | 生成一个图片按钮，颜色代码按钮                   |
| email、tel、url                                   | 生成一个检测电子邮件、号码、网址的文本框         |
| date、mouth、time、week、datetime、datetime-local | 获取时间和日期                                   |
| hidden                                            | 生成一个隐藏控件                                 |
| file                                              | 生成一个上传控件                                 |

###### **当type为text**

| 属性名称    | 说明                                                         |
| ----------- | ------------------------------------------------------------ |
| list        | 指定为文本框提供**建议**的**datalist**元素，其值为datalist元素的id值 |
| maxlength   | 设置文本框的最大字符长度                                     |
| pattern     | 用于输入验证的正则表达式                                     |
| placeholder | 输入字符提示                                                 |
| readonly    | 文本框处于只读状态                                           |
| disabled    | 文本框处于禁用状态                                           |
| size        | 设置文本框的宽度                                             |
| value       | 设置文本框的初始值                                           |
| required    | 表明用户必须输入一个值，否则无法通过输入验证                 |

**list**

```html
<form action="http://www.baidu.com">
		<input type="text" list="abc">
		<button>提交</button>
	</form>

	<datalist id="abc">
		<option value="1">苹果</option>
	</datalist>
```

###### 当text为password

|  属性名称   |           说明           |
| :---------: | :----------------------: |
|  maxlength  | 设置文本框的最大字符长度 |
|   pattern   | 用于输入验证的正则表达式 |
| placeholder |      输入密码的提示      |
|  readyonly  |    密码框处于只读模式    |
|  disabled   |    密码框处于禁用模式    |
|    size     |     设置密码框的宽度     |
|    value    |    设置密码框的初始值    |
|   require   | 表明用户必须输入同一个值 |

###### 当type为number、range

| 属性名称 | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| list     | 指定为文本框提供**建议**的**datalist**元素，其值为datalist元素的id值 |
| min      | 设置可接受的最小值                                           |
| max      | 设置可接受的最大值                                           |
| readonly | 文本框只读                                                   |
| required | 必须输入，否则无法通过验证                                   |
| step     | 指定上下调节值的步长                                         |
| value    | 指定初始值                                                   |



###### **当type为date**

| 属性名称 | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| list     | 指定为文本框提供**建议**的**datalist**元素，其值为datalist元素的id值 |
| min      | 设置可接受的最小值                                           |
| max      | 设置可接受的最大值                                           |
| readonly | 文本框只读                                                   |
| required | 必须输入，否则无法通过验证                                   |
| step     | 指定上下调节值的步长                                         |
| value    | 指定初始值                                                   |

###### **当type为checkbox、radio**

| 属性名称 |                       说明                       |
| :------: | :----------------------------------------------: |
| checked  |         设置单选框和复选框时否为勾选状态         |
| required |            必须勾选，否则无法通过验证            |
|  value   | 设置单选框和复选框勾选状态时提交的数据，默认为on |

###### 当type为submit、reset、button

生成一个按钮：submit为提交；reset为重置；button为普通按钮；

###### 当type为image

| 属性名称     | 说明                                                         |
| ------------ | ------------------------------------------------------------ |
| ssrc         | 指定显示图像的URL                                            |
| alt          | 提供图片的文字说明                                           |
| width        | 图像的长度                                                   |
| height       | 图像的高度                                                   |
| 提交额外属性 | formaction、formenctype、formmethod、formtarget、formnovalidate |

###### 当type为email、tel、url

email为电子邮件格式  tel为电话格式   url为网址格式

###### 当type为file

| 属性名称 | 说明                               |
| -------- | ---------------------------------- |
| accept   | 指定接受的MIME类型                 |
| required | 必须提供一个值，发否则无法通过验证 |

### （2.）其他标签

| 标签名称                 | 说明                 |
| ------------------------ | -------------------- |
| select                   | 生成下拉列表进行选择 |
| optgroup（内处于select） | 对select进行编组     |
| option(内处于select)     | select中的项目       |
| textarea                 | 生成一个多行文本框   |
| output                   | 表示计算结果         |

#### <1.>select（下拉选项）

生成下拉列表进行选择；至少包含一个option子标签，生成有效选择列表

```html
<select name="fruit">
			<option value="1">苹果</option>
			<option value="2">香蕉</option>
			<option value="3">草莓</option>
			<option value="4">葡萄</option>
</select>
```

select的子标签

| 属性名称  | 说明                             |
| --------- | -------------------------------- |
| name      | 提交时设定的名称                 |
| disabled  | 将下拉列表禁用                   |
| form      | 将表单外的下拉列表与某个表单挂钩 |
| size      | 设置下拉列表的高度               |
| multiple  | 设置是否可以多选                 |
| autofocus | 获取焦点                         |
| required  | 选择验证，设置后必须选择才能通过 |

##### optgroup  option

optgroup和option是用来对select分组；**label**进行分组命名；**disabled**对分组禁用

```html
<select name="fruit" size="10" multiple>
			<optgroup label="水果">
				<option value="1">苹果</option>
				<option value="2" selected>香蕉</option>
				<option value="3">草莓</option>
				<option value="4">葡萄</option>
			</optgroup>

			<optgroup label="粗粮">
				<option value="1">小米</option>
				<option value="2">大米</option>
				<option value="3">高粱</option>
			</optgroup>
			
			
		</select>
```

#### <2.>textarea

多行文本框

| 属性名称    | 说明                                 |
| ----------- | ------------------------------------ |
| name        | 设定提交时的名称                     |
| form        | 将表单外的多行文本框与某个表单挂钩   |
| readonly    | 是指多行文本框只读                   |
| disabled    | 将多行文本框禁用                     |
| maxlength   | 设置最大可输入字符长度               |
| autofocus   | 获取焦点                             |
| placeholder | 设置在输入时的提示信息               |
| rows        | 设置行数                             |
| cols        | 设置列数                             |
| wrap        | 设置是否插入换行符，有soft和hard两种 |
| reuqired    | 设置必须输入值，否则无法通过验证     |

#### <3.>计算结果

```html
<form action="http://www.baidu.com" oninput="res.value =num1.valueAsNumber*num2.valueAsNmuber">
		<input type="number" id="num1">*<input type="number" id="num2">=
		<output for="num1 num2" name="res"></output>
		<button>提交</button>
	</form><br>
```

#### <4.>正则表达式验证

```html
<form action="http://www.baidu.com">
		<input type="text" placeholder="区号＋座机" pattern="^[\d]{2,4}\-[\d]{6,8}$">
		<button>提交</button>
	</form><br>
```

<5.>禁止验证

```html
<form   action="http://www.baidu.com" novalidate >
		<input type="text" placeholder="区号＋座机" pattern="^[\d]{2,4}\-[\d]{6,8}$">
		<button>提交</button>
	</form><br>
```

### 3**.label元素**（标签）

给input添加说明标签；**点击标签就可输入；有两种书写：**

```html
<label>
		用户名 <input id="user" name="user" value="bbb">
		<!-- value为默认输入值 -->
		<br>
</label>
```

```html
<label for="user">用户名</label>
		<input id="user" name="user" value="bbb">
		<!-- value为默认输入值 -->
		<br>
```

### 4.**fieldset标签**（分组）

对表单进行分组；

| 属性名称 | 说明                       |
| -------- | -------------------------- |
| name     | 给分组定义一个名称         |
| form     | 让表单以外的分组与表单挂钩 |
| disabled | 禁止分组内的表单           |

### 5**.legend**（分组标签）

分组添加说明标签；(与4连用)

```html
<fieldset >
			<legend>注册表单</legend>
</fieldset>
```

### 6.**botton**（按钮）

添加按钮；

| 属性名称 | 说明                           |
| -------- | ------------------------------ |
| submit   | 提交                           |
| reset    | 重置                           |
| button   | 普通按钮（配合JavaScript触发） |

```html
<button type="submit">提交</button> 
<button type="reset">重置</button>
<button type="button">按钮</button>
```

当button的属性是**type是submit时**，还有额外的属性

| 属性名称       | 说明                             |
| -------------- | -------------------------------- |
| form           | 指定按钮关联的表单               |
| formaction     | **覆盖**form元素的action属性     |
| formentype     | **覆盖**form元素的entype属性     |
| formmethod     | **覆盖**form元素的method属性     |
| formarget      | **覆盖**form元素的arget属性      |
| formnovalidate | **覆盖**form元素的novalidate属性 |



## 14.扩展阅读

### 1.锚点定位

使用相应的id名标注跳转目标的位置（找目标）；

在需要添加链接的位置写链接标签a,href="#id名"；

```html
<a href="#oldman">2.圣诞老人的由来</a><br>


<h3 id="oldman">圣诞老人的由来</h3>

```

### 2.base

base标签设置整体链接的打开状态；

写在head与/head标签之间；

```html
<base target="_blank">
```

### 3.预格式化文本

按照文本输入的格式显示页面；

```
<pre>
	清蒸班主任，
	油炸小助教。
	爆火炒导师，
	班长要红烧。
</pre>
```

### 4.特殊字符

![](C:\Users\1\Desktop\全栈\笔记图片\屏幕截图 2021-11-29 154524.png)