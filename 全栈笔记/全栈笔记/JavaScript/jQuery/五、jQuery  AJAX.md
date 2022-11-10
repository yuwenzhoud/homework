# jQuery - AJAX 

 [jQuery AJAX 参考手册](https://www.w3school.com.cn/jquery/jquery_ref_ajax.asp)

## 1、jQuery - AJAX 简介

 **AJAX 是与服务器交换数据的艺术，它在不重载全部页面的情况下，实现了对部分网页的更新。** 

### 什么是 AJAX？

- AJAX = 异步 JavaScript 和 XML（Asynchronous JavaScript and XML）。
- 简短地说，在不重载整个网页的情况下，AJAX 通过后台加载数据，并在网页上进行显示。
- 使用 AJAX 的应用程序案例：谷歌地图、腾讯微博、优酷视频、人人网等等。

### 关于 jQuery 与 AJAX

jQuery 提供多个与 AJAX 有关的方法。

通过 jQuery AJAX 方法，您能够使用 HTTP Get 和 HTTP Post 从远程服务器上请求文本、HTML、XML 或 JSON - **同时您能够把这些外部数据直接载入网页的被选元素中。**

**提示：**如果没有 jQuery，AJAX 编程还是有些难度的。

编写常规的 AJAX 代码并不容易，因为不同的浏览器对 AJAX 的实现并不相同。这意味着您必须编写额外的代码对浏览器进行测试。不过，jQuery 团队为我们解决了这个难题，我们只需要一行简单的代码，就可以实现 AJAX 功能。

## 2、jQuery - AJAX load() 方法

### ~ jQuery load() 方法

jQuery load() 方法是简单但强大的 AJAX 方法。

load() 方法从服务器加载数据，并把返回的数据放入被选元素中。

语法：

```js
$(selector).load(URL,data,callback);
```

-  请使用 **selector** 来定义要改变的 HTML 元素，使用 url参数来指定数据的 web 地址。 
- **必需的** *URL* 参数规定您希望加载的 URL。
- **可选的** *data* 参数规定与请求一同发送的查询字符串键/值对集合。
- **可选的** *callback* 参数是 load() **方法完成后**所执行的函数名称。

实例：这是示例文件（"demo_test.txt"）的内容：

```js
<h2>jQuery and AJAX is FUN!!!</h2>
<p id="p1">This is some text in a paragraph.</p>
```

实例：会把文件 "demo_test.txt" 的内容加载到指定的 <div> 元素中：

```js
$("#div1").load("demo_test.txt");
```

也可以把 jQuery 选择器添加到 URL 参数。

实例：把 "demo_test.txt" 文件中 id="p1" 的元素的内容，加载到指定的 <div> 元素中：

```js
$("#div1").load("demo_test.txt #p1");
```



**可选的** callback 参数规定当 load() 方法**完成后所要允许的回调函数**。回调函数可以设置不同的参数：

- *responseTxt* - 包含调用成功时的结果内容
- *statusTXT* - 包含调用的状态
- *xhr* - 包含 XMLHttpRequest 对象

下面的例子会在 load() 方法完成后显示一个提示框。如果 load() 方法已成功，则显示“外部内容加载成功！”，而如果失败，则显示错误消息：

实例：

```js
$("button").click(function(){
  $("#div1").load("demo_test.txt",function(responseTxt,statusTxt,xhr){
    if(statusTxt=="success")
      alert("外部内容加载成功！");
    if(statusTxt=="error")
      alert("Error: "+xhr.status+": "+xhr.statusText);
  });
});
```

## 3、get() 和 post() 方法

 **jQuery get() 和 post() 方法用于通过 HTTP GET 或 POST 请求从服务器请求数据。** 

HTTP 请求：GET vs. POST

两种在客户端和服务器端进行请求-响应的常用方法是：GET 和 POST。

- *GET* - 从指定的资源请求数据
- *POST* - 向指定的资源提交要处理的数据

1. GET 基本上用于从服务器获得（取回）数据。注释：GET 方法可能返回缓存数据。
2. POST 也可用于从服务器获取数据。不过，POST 方法不会缓存数据，并且常用于连同请求一起发送数据。

### ~ jQuery $.get

$.get() 方法通过 HTTP GET 请求从服务器上请求数据。

语法：

```js
$.get(URL,callback);
```

- **必需的** *URL* 参数规定您希望请求的 URL。
- **可选的** *callback* 参数是请求成功后所执行的函数名。

实例：使用 $.get() 方法从服务器上的一个文件中取回数据：

```js
$("button").click(function(){
  $.get("demo_test.asp",function(data,status){
    alert("Data: " + data + "\nStatus: " + status);
  });
});
```



$.get() 的第一个参数是我们希望请求的 URL（"demo_test.asp"）。

第二个参数是回调函数。第一个回调参数存有被**请求页面的内容**，第二个回调参数**存有请求的状态**。

**提示：**这个 ASP 文件 ("demo_test.asp") 类似这样：

```js
<script>
$(document).ready(function(){
  $("button").click(function(){
    $.get("/example/jquery/demo_test.asp",function(data,status){
      alert("数据：" + data + "\n状态：" + status);
    });
  });
});
</script>
```

### ~jQuery $.post

$.post() 方法通过 HTTP POST 请求从服务器上请求数据。

语法：

```js
$.post(URL,data,callback);
```

- **必需的** *URL* 参数规定您希望请求的 URL。
- **可选的** *data* 参数规定连同请求发送的数据。
- **可选的** *callback* 参数是请求成功后所执行的函数名。

实例：使用 $.post() 连同请求一起发送数据：

```js
$("button").click(function(){
  $.post("demo_test_post.asp",
  {
    name:"Donald Duck",
    city:"Duckburg"
  },
  function(data,status){
    alert("Data: " + data + "\nStatus: " + status);
  });
});
```

$.post() 的**第一个参数**是我们希望请求的 URL ("demo_test_post.asp")。然后我们连同请求（name 和 city）一起发送数据。

"demo_test_post.asp" 中的 ASP 脚本读取这些参数，对它们进行处理，然后返回结果。

**第三个参数是回调函数**。第一个回调参数存有被**请求页面的内容**，而第二个参数**存有请求的状态**。

**提示：**这个 ASP 文件 ("demo_test_post.asp") 类似这样：

```js
<%
dim fname,city
fname=Request.Form("name")
city=Request.Form("city")
Response.Write("Dear " & fname & ". ")
Response.Write("Hope you live well in " & city & ".")
%>
```

## 4、noConflict() 方法

产生原因：

```js
其他一些 JavaScript 框架包括：MooTools、Backbone、Sammy、Cappuccino、Knockout、JavaScript MVC、Google Web Toolkit、Google Closure、Ember、Batman 以及 Ext JS。

其中某些框架也使用 $ 符号作为简写（就像 jQuery），如果您在用的两种不同的框架正在使用相同的简写符号，有可能导致脚本停止运行。

jQuery 的团队考虑到了这个问题，并实现了 noConflict() 方法。
```

 noConflict() 方法会释放会 $ 标识符的控制，这样其他脚本就可以使用它了。 

1. 可以通过全名替代简写的方式来使用 jQuery

   ```js
   $.noConflict();
   jQuery(document).ready(function(){
     jQuery("button").click(function(){
       jQuery("p").text("jQuery 仍在运行！");
     });
   });
   ```

   

2. 也可以创建自己的简写。noConflict() 可返回对 jQuery 的引用，您可以把它存入变量，以供稍后使用。

```js
var jq = $.noConflict();
jq(document).ready(function(){
  jq("button").click(function(){
    jq("p").text("jQuery 仍在运行！");
  });
});
```

3. 如果你的 jQuery 代码块使用 $ 简写，并且您不愿意改变这个快捷方式，那么您可以把 $ 符号作为变量传递给 ready 方法。这样就可以**在函数内使用 $ 符号了 - 而在函数外，依旧不得不使用 "jQuery"**： 

```js
$.noConflict();
jQuery(document).ready(function($){
  $("button").click(function(){
    $("p").text("jQuery 仍在运行！");
  });
});
```

## 5、Low Level AJAX

*$.ajax(options)* 是低层级 AJAX 函数的语法。

$.ajax 提供了比高层级函数更多的功能，但是同时也更难使用。

*option* 参数设置的是 name|value 对，定义 url 数据、密码、数据类型、过滤器、字符集、超时以及错误函数。

## 6、jQuery AJAX 请求

| 请求                                | 描述                                   |
| ----------------------------------- | -------------------------------------- |
| $(selector).load(url,data,callback) | 把远程数据加载到被选的元素中           |
| $.ajax(options)                     | 把远程数据加载到 XMLHttpRequest 对象中 |
| $.get(url,data,callback,type)       | 使用 HTTP GET 来加载远程数据           |
| $.post(url,data,callback,type)      | 使用 HTTP POST 来加载远程数据          |
| $.getJSON(url,data,callback)        | 使用 HTTP GET 来加载远程 JSON 数据     |
| $.getScript(url,callback)           | 加载并执行远程的 JavaScript 文件       |

- (*url*) 被加载的数据的 URL（地址）
- (*data*) 发送到服务器的数据的键/值对象
- (*callback*) 当数据被加载时，所执行的函数
- (*type*) 被返回的数据的类型 (html,xml,json,jasonp,script,text)
- (*options*) 完整 AJAX 请求的所有键/值对选项

