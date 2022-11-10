# 二、jQuery效果

## 1、隐藏和显示

 **隐藏、显示、切换，滑动，淡入淡出，以及动画，哇哦！** 

**语法**

```js
$(selector).hide(speed,callback);

$(selector).show(speed,callback);

$(selector).toggle(speed,callback);
```

- **可选的** speed 参数规定隐藏/显示的速度，可以取以下值："slow"、"fast" 或毫秒。
- **可选的** callback 参数是隐藏或显示完成后所执行的函数名称。

### ~ hide

```js
$("#hide").click(function(){
  $("p").hide();
});
```

### ~ show

```js
$("#show").click(function(){
  $("p").show();
});
```

**实例**

```js
$("button").click(function(){
  $("p").hide(1000);//一秒完成隐藏函数
});
```

### ~ toggle(转化)

使用 toggle() 方法来切换 hide() 和 show() 方法。

显示被隐藏的元素，并隐藏已显示的元素：

**实例**

```js
$("button").click(function(){
  $("p").toggle();//隐藏状态下显示，显示状态下隐藏
});
```



## 2、淡入淡出

语法：

```js
$(selector).fadeIn(speed,callback);

$(selector).fadeOut(speed,callback);

$(selector).fadeToggle(speed,callback);
```

### ~ fadeIn

实例：

```js
$("button").click(function(){
  $("#div1").fadeIn();//直接淡入
  $("#div2").fadeIn("slow");//缓慢淡入
  $("#div3").fadeIn(3000);//三秒淡入
});
```



### ~ fadeOut

实例：

```js
$("button").click(function(){
  $("#div1").fadeOut();//直接淡出
  $("#div2").fadeOut("slow");//缓慢淡出
  $("#div3").fadeOut(3000);//三秒淡出
});
```



### ~ fadeToggle(转化)

淡入与淡出之间切换；淡入后淡出，淡出后淡入；

实例：

```js
$("button").click(function(){
  $("#div1").fadeToggle();
  $("#div2").fadeToggle("slow");
  $("#div3").fadeToggle(3000);
});
```



### ~ fadeTo(透明度)

 jQuery fadeTo() 方法允许渐变为给定的不透明度（值介于 0 与 1 之间）。 

语法：

```js
$(selector).fadeTo(speed,opacity,callback);
```

- **必需的** speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。
- **必需的** opacity 参数将淡入淡出效果设置为给定的不透明度（值介于 0 与 1 之间）。
- **可选的** callback 参数是该函数完成后所执行的函数名称。

实例：

```js
$("button").click(function(){
  $("#div1").fadeTo("slow",0.15);
  $("#div2").fadeTo("slow",0.4);
  $("#div3").fadeTo("slow",0.7);
});
```



## 3、滑动

语法：

```js
$(selector).slideDown(speed,callback);

$(selector).slideUp(speed,callback);

$(selector).slideToggle(speed,callback);
```

- **可选的** speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。
- **可选的** callback 参数是滑动完成后所执行的函数名称。

### ~ slideDown(向下)

**实例：**

```js
$("#flip").click(function(){
  $("#panel").slideDown();
});
```

### ~ slideUp(向上)

**实例**

```js
$("#flip").click(function(){
  $("#panel").slideUp();
});
```

### ~ slideToggle(转化)

**实例**

```js
$("#flip").click(function(){
  $("#panel").slideToggle();
});
```



## 4、动画

### ~ animate

方法允许您创建自定义的动画。

语法：

```js
$(selector).animate({params},speed,callback);
```

- **必需的** params 参数定义形成动画的 CSS 属性。
- **可选的** speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。
- **可选的** callback 参数是动画完成后所执行的函数名称。

下面的例子演示 animate() 方法的简单应用；它把 <div> 元素移动到左边，直到 left 属性等于 250 像素为止：

**实例**

```js
$("button").click(function(){
  $("div").animate({left:'250px'});
}); 
```

 注意：默认情况下，所有 HTML 元素的位置都是静态的，并且无法移动。如需对位置进行操作，记得首先把元素的 CSS **position 属性设置为 relative、fixed 或 absolute。** 

### ~ 操作多个属性

请注意，生成动画的过程中可同时使用多个属性：

**实例**

```js
$("button").click(function(){
  $("div").animate({
    left:'250px',
    opacity:'0.5',
    height:'150px',
    width:'150px'
  });
}); 
```

- 可以用 animate() 方法来操作所有 CSS 属性
- 当使用 animate() 时，必须使用 Camel 标记法书写所有的属性名（驼峰）
- 同时，色彩动画并不包含在核心 jQuery 库中。如果需要生成颜色动画，需要从 jQuery.com 下载 Color Animations 插件。

### ~ 使用相对值

相对值： 该值相对于元素的当前值 ；

 实例：

```js
$("button").click(function(){
  $("div").animate({
    left:'250px',
    height:'+=150px',
    width:'+=150px'
  });
});
```

### ~ 使用预定义的值

 您甚至可以把属性的动画值设置为 "show"、"hide" 或 "toggle"： 

```js
$("button").click(function(){
  $("div").animate({
    height:'toggle'
  });
});
```

### ~ 使用队列功能

 默认地，jQuery 提供针对动画的队列功能。 在彼此之后执行不同的动画，那么我们要利用队列功能：

```js
//实例：1
$("button").click(function(){
  var div=$("div");
    //按顺序执行
  div.animate({height:'300px',opacity:'0.4'},"slow");
  div.animate({width:'300px',opacity:'0.8'},"slow");
  div.animate({height:'100px',opacity:'0.4'},"slow");
  div.animate({width:'100px',opacity:'0.8'},"slow");
});


//实例：2
$("button").click(function(){
  var div=$("div");
  div.animate({left:'100px'},"slow");
  div.animate({fontSize:'3em'},"slow");
});
```



## 5、 停止动画 

~ stop() 方法用于在**动画或效果完成前**对它们进行停止。  

stop() 方法**适用于所有** jQuery 效果函数，包括滑动、淡入淡出和自定义动画。 

### ~ stop

**语法**

```
$(selector).stop(stopAll,goToEnd);
```

**可选的** stopAll 参数规定是否应该清除动画队列。默认是 false，即仅停止活动的动画，**允许任何排入队列的动画向后执行**。

**可选的** goToEnd 参数规定是否立即完成当前动画。默认是 false。

因此，默认地，stop() 会清除在被选元素上指定的当前动画。

实例：

```js
<script> 
$(document).ready(function(){
  $("#flip").click(function(){
    $("#panel").slideDown(5000);
  });
  $("#stop").click(function(){
    $("#panel").stop();
  });
});
</script>
```



## 6、Callback 函数

 **Callback 函数在当前动画 100% 完成之后执行。** 

1. 许多 jQuery 函数涉及动画。这些函数也许会将 *speed* 或 *duration* 作为可选参数。
2. 例子：***$("p").hide("slow")***
3. *speed* 或 *duration* 参数可以设置许多不同的值，比如 "slow", "fast", "normal" 或毫秒。
4. 由于 JavaScript 语句（指令）是逐一执行的 - 按照次序，动画之后的语句可能会产生错误或页面冲突，因为动画还没有完成。
5. 为了避免这个情况，您可以以参数的形式添加 Callback 函数

**典型的语法：**

```js
$(selector).hide(speed,callback)
//callback 参数是一个在 hide 操作完成后被执行的函数。
```



**错误（没有 callback）**

```js
$("p").hide(1000);
alert("The paragraph is now hidden");
//先出现弹窗，后执行动画；
```

**正确（有 callback）**

```js
$("p").hide(1000,function(){
alert("The paragraph is now hidden");
});
//先执行动画，后出现弹窗;
```

 **结论：**如果您希望在一个涉及动画的函数之后来执行语句，请使用 callback 函数。 



## 7、Chaining(链接)

 **Chaining 允许我们在一条语句中允许多个 jQuery 方法（在相同的元素上）。** 

实例：

```js
//方法一:
$("#p1").css("color","red").slideUp(2000).slideDown(2000);

//方法二:
$("#p1").css("color","red")
    .slideUp(2000)
    .slideDown(2000);
```

