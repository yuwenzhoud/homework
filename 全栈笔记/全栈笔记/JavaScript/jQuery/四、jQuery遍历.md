# 四、jQuery遍历、

  [jQuery 遍历参考手册](https://www.w3school.com.cn/jquery/jquery_ref_traversing.asp)

## 1、jQuery遍历

jQuery 遍历，意为“移动”，用于根据其相对于其他元素的关系来“查找”（或选取）HTML 元素。以某项选择开始，并沿着这个选择移动，直到抵达您期望的元素为止。

下图展示了一个家族树。通过 jQuery 遍历，能够从被选（当前的）元素开始，轻松地在家族树中向上移动（祖先），向下移动（子孙），水平移动（同胞）。**这种移动被称为对 DOM 进行遍历**。

图示解释：

![遍历 DOM 树](https://www.w3school.com.cn/i/dom_tree.gif)

**提示：**祖先是父、祖父、曾祖父等等。后代是子、孙、曾孙等等。同胞拥有相同的父。

## 2、jQuery 祖先

通过 jQuery，您能够向上遍历 DOM 树，以查找元素的祖先。

### ~ parent

parent() 方法返回被选元素的**直接父元素**。

该方法只会向**上一级**对 DOM 树进行遍历。

下面的例子返回每个 <span> 元素的的直接父元素：

实例：

```js
$(document).ready(function(){
  $("span").parent();
});
```



### ~ parents

parents() 方法返回**被选元素的所有祖先元素**，它一路向上直到文档的根元素 (<html>)。

下面的例子返回所有 <span> 元素的所有祖先：

实例：

```js
$(document).ready(function(){
  $("span").parents();
});
```



也可以使用可选参数来过滤对祖先元素的搜索。

实例：返回所有 <span> 元素的所有祖先，并且它是 <ul> 元素：

```js
$(document).ready(function(){
  $("span").parents("ul");
});
```



### ~ parentsUntil

parentsUntil() 方法返回**介于两个给定元素之间的所有祖先元素**。

下面的例子返回介于 <span> 与 <div> 元素之间的所有祖先元素：

实例：

```js
$(document).ready(function(){
  $("span").parentsUntil("div");//从span到div(不算在其中)的所有祖先元素
});
  <div style="width:500px;">div (曾祖父)
    <ul>ul (祖父)  
      <li>li (直接父)
        <span>span</span>
      </li>
    </ul>   
  </div>
```

## 3、jQuery 后代

### ~ children

children() 方法返回**被选元素的所有直接子元素**。

该方法只会向**下一级**对 DOM 树进行遍历。

实例：返回每个 <div> 元素的所有直接子元素：

```js
$(document).ready(function(){
  $("div").children();
});
```



您也可以使用可选参数来过滤对子元素的搜索。

实例：返回类名为 "1" 的所有 <p> 元素，并且它们是 <div> 的直接子元素：



```js
$(document).ready(function(){
  $("div").children("p.1");
});
```



### ~ find

find() 方法返回**被选元素的后代元素，一路向下直到最后一个后代**。

实例1：返回属于 <div> 后代的所有 <span> 元素：

```js
$(document).ready(function(){
  $("div").find("span");//指定后代
});
```

实例2：返回 <div> 的所有后代：

```js
$(document).ready(function(){
  $("div").find("*");//不指定后代
});
```

## 4、jQuery 同胞

### ~ siblings

- siblings() 方法返回被选元素的**所有同胞元素**。

实例：返回 <h2> 的所有同胞元素：

```js
$(document).ready(function(){
  $("h2").siblings();
});
```

- 也可以使用可选参数来过滤对同胞元素的搜索。

实例：返回属于 <h2> 的同胞元素的**所有** <p> 元素：

```js
$(document).ready(function(){
  $("h2").siblings("p");//指定同胞元素
});
```

### ~ next  ~ prev

- next() 方法返回被选元素的下一个同胞元素。该方法**只返回一个**元素。
- prev() 方法返回被选元素的下一个同胞元素。该方法**只返回一个**元素。

实例：返回 <h2> 的下一个同胞元素：

```js
$(document).ready(function(){
  $("h2").next();
});
```



### ~ nextAll  ~ prevAll

- nextAll() 方法返回被选元素的**所有跟随的同胞元素**。
- prevAll() 方法返回被选元素的**所有跟随的同胞元素**。

实例：返回 <h2> 的所有**跟随的同胞元素**：

```js
$(document).ready(function(){
  $("h2").nextAll();
});
```



### ~ nextUntil   ~ prevUntil

- nextUntil() 方法返回介于两个**给定参数之间的所有跟随的同胞元素。**
- prevUntil() 方法返回介于两个**给定参数之间的所有跟随的同胞元素。**

实例：返回介于 <h2> 与 <h6> 元素之间的**所有同胞元素**：

```js
$(document).ready(function(){
  $("h2").nextUntil("h6");//不包含被指定的两个元素
});
```

## 5、jQuery 过滤

### ~ first

first() 方法返回被选元素的**首个元素**。

实例：选取首个 <div> 元素内部的第一个 <p> 元素：

```js
$(document).ready(function(){
  $("div p").first();
});
```



### ~ last

last() 方法返回被选元素的**最后一个**元素。

实例：选择最后一个 <div> 元素中的最后一个 <p> 元素：

```js
$(document).ready(function(){
  $("div p").last();
});
```



## ~ eq

eq() 方法返回被选元素中带有**指定索引号**的元素。索引号从 0 开始，因此首个元素的索引号是 0 而不是 1。

实例：选取第二个 <p> 元素（索引号 1）：

```js
$(document).ready(function(){
  $("p").eq(1);
});
```



## ~ filter

filter() 方法允许规定一个标准。**不匹配这个标准的元素会被从集合中删除，匹配的元素会被返回**。

实例：返回带有类名 "intro" 的所有 <p> 元素：

```js
$(document).ready(function(){
  $("p").filter(".intro");
});
```



## ~ not

not() 方法返回**不匹配标准**的所有元素。**提示：**not() 方法与 filter() 相反。

实例：返回**不带有类名** "intro" 的所有 <p> 元素：

```js
	$(document).ready(function(){
  $("p").not(".intro");
});
```