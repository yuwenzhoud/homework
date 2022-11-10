# 简介

JavaScript框架

简化Dom操作

响应式数据驱动

# 第一个Vue程序

1. 导入开发版本的Vue.js
2. 创建Vue实例对象，设置el属性和data属性
3. 使用简洁的模板语法把数据渲染到页面上

## 1.el挂载点

1. Vue会管理el选项命中的元素以及内部的后代元素；
2. 可以使用其他的选择器，建议使用id选择器；
3. 使用双标签，不要使用body和HTML；

```html
<p id="app" class="app">
        {{message }}

        <span id="app">
            {{message}}
        </span>
    </p>

    
    <script>
        var app = new new Vue({
            // el:"#app",
            // el:".app",
            el:"p",
            data:{
                message:'黑马'
            }
        })
    </script>
```



## 2.data数据对象

1. Vue用到的数据写在data中；
2. data中可以写复杂类型的数据；
3. 选赞复杂类型的数据时 ，遵守js的语法；（对象的点语法，数据的索引语法）；



```html
    <div id="app">
        {{message}}

        <h2>{{school.name}}  {{school.mobile}}</h2>

        <ul>
            <li>
                {{campus[0]}}
            </li>

            <li>
                {{campus[1]}}
            </li>
        </ul>
    </div>

    <script>
        var app = new Vue({
            el:"#app",
            data:{
                message:"hai",
                school:{
                    name:"黑马程序员",
                    mobile:"123456",
                },
                campus:["北京","上海"]

            }
        })
    </script>
```



# 本地应用

## v-text 设置内容

```html
<div id="app">
        <h2 v-text="message+'!'"></h2>
        <h2>深圳{{message+"!"}}</h2>
        <h2>haha{{info+"@"}}</h2>
    </div>

    <script>
        var app = new Vue({
            el:"#app",
            data:{
                message:"黑马程序员",
                info:"前端移动",
            }
        })
    </script>
```

1. 直接v-text 为data里数据的名称；
2. 使用大括号，内部为数据的名称；
3. 利用+进行字符串的拼接；

## v-html 标签的innerHtml



如果只是设置文本效果与v-text一样，**如果设置的内容中时HTML结构就会被解析为标签；**

```html
    <div id="app">
        <p v-html="content"></p>
        <p v-html="contents"></p>
    </div>

    <script>
        var app =new Vue({
            el:"#app",
            data:{
                content:"黑马程序员",
                contents:"<a href='http://www.itheima.com'>黑马程序员</a>"
            }
        })
    </script>
```

## v-on 为元素绑定事件

1. 事件名不需要写on；
2. 指令可以简写为@；
3. 绑定的方法定义在methods属性中；
4. 方法内部通过this关键字访问定义在data中俄数据；

```html
<div id="app">

        <!-- 点击 -->
        <input type="button" value="v-on" v-on:click="doit">
        <!-- 简写 -->
        <input type="button" value="v-on简写" @click="doit">
        <!-- 双击 -->
        <input type="button" value="双击事件" @dblclick="doit">

        <h2 @click="change">{{food}}</h2>
    </div>

    <script>
        var app = new Vue({
            el:"#app",
            methods:{
                doit:function() {
                    alert("做IT");
                },
                change:function() {
                    this.food+="好好吃"
                }
            },
            data:{
                food:"西兰花",
            }
        }) 
    </script>
```



## v-on 自定义参数

1. 传到自定义参数，事件修饰符；
2. 事件绑定的方法写成函数调用的形式，可以传入自定义参数；
3. 定义方法需要定义形参来接收传入的实参；
4. 事件后面（.事件修饰符）可以触发；



```html
    <div id="app">
        <button @click="doit(666,'啦啦啦')">点击</button>

        <input type="text" @keyup.enter="sayhi">
    </div>

    <script>
        var app = new Vue({
            el:"#app",
            data:{
                
            },
            methods:{
                doit:function(p1,p2) {
                    console.log(p1)
                    console.log(p2)
                },
                sayhi:function(){
                    alert("haha")
                }
            }
        })
    </script>
```



## v-show  元素的显示和隐藏

1. 根据表达式的真假，切换元素的显示和隐藏；
2. **修改元素的display实现隐藏**；
3. 数据也可以做切换条件；
4. 写在最后的都会被解析为布尔值；

```html
 
    <div id="app">
        
        <div v-show="age>=18" style="width: 500px; height: 250px; background-color: green;"></div>
        <div>{{age}}</div>
        <input type="button" value="年龄" @click="Addage">
        
        <div v-show="isShow" style="width: 500px; height: 250px; background-color: red;"></div>
        <button value="切换显示状态" @click="change" >切换显示状态</button>
    </div>

    <script>
        var app = new Vue({

        el:"#app",
        data:{
            isShow:false,
            age:17,
        },
        methods: {
            change:function(){
                this.isShow=!this.isShow;//取反，进行显示和隐藏的切换
            },
            Addage:function(){

                this.age++;
                console.log(this.age)
            }
        },
        })
    </script>
```

## v-if  操作dom元素

1. 根据表达式的真假切换元素的显示状态，
2. 本质：**操作dom元素**；
3. true在dom树中添加；false在dom树 中删除；

```html
<div id="app">
        <input type="button" value="切换显示"  @click="TisShow">
        <p v-if="isShow">黑马程序员</p>

        <input type="button" value="切换显示"  @click="TisShow2">
        <p v-show="isShow2">黑马程序员</p>

        <h2 v-if="temperature>=35">热死了</h2>
        <input type="button" value="温度上升" @click="up">
    </div>

    <script>
        var app = new Vue({
            el:"#app",
            data:{
                isShow:false,
                isShow2:false,
                temperature:33
            },
            methods: {
                TisShow:function() {
                    this.isShow=!this.isShow;
                },
                TisShow2:function() {
                    this.isShow2=!this.isShow2;
                },
                up:function() {
                    this.temperature++;
                }
            }
        })
    </script>
```

## v-bind 绑定属性

为元素绑定属性（title，src，class）；

语法：v-bind：属性名=表达式；简写（：属性名）；

```html
     <div id="app">
        <!-- 图片地址 -->
        <img v-bind:src="imgSrc">
        <br>
        <!-- 简写 -->
        <!-- 鼠标悬停 -->
        <img :src="imgSrc"  :title="imgTitle+'!!!'">
        <br>

        <!-- 设置class -->
        <img :src="imgSrc" v-bind:class="{active:imgActive}" @click="Active">
    </div>

<script>
    var app = new Vue({
        el:"#app",
        data:{
            imgSrc:"images/fly.png",
            imgTitle:"云翼",
            imgActive:false
        },
        methods: {
            Active:function() {
                this.imgActive=!this.imgActive;
            }
        }
    })
</script>
```

## v-for 生成列表结构

语法：

```html
v-for="名称 in arr"
```

```html
<div id="app">
        <ul>
            <!-- 根据数组长度创建li,再利用item写入数组的内容,item是名称可以更改-->
            <li v-for="(item,index) in arr">{{index+1}}哈哈{{item}}</li>
        </ul>

        <h2 v-for="it in vegetables" v-bind:title="it.name">{{it.name}}</h2>

        <input type="button"value="添加" @click="add">
        <input type="button"value="移除" @click="remove">
    </div>
    
    <script>
        var app= new Vue({
            el:"#app",
            data:{
                arr:["北京","上海","广州","深圳"],
                vegetables:[
                    {name:"西兰花"},
                    {name:"苦瓜"},
                ],
            },
            methods: {
                add:function() {
                    this.vegetables.push({name:"番茄"});
                },
                remove:function() {
                    this.vegetables.shift();
                },
            }
        })
    </script>
```

## v-model获取和设置表单元素的值

绑定的数据会和表单的值相关联；

绑定的数据与表单元素的值双向绑定；

```html
    <div id="app">
        <input type="button" value="修改message" @click="setm">
        <input type="text" v-model="message" @keyup.enter="getm">
        <!-- 同步更新 -->
        <h2>{{message}}</h2>
    </div>

    <script>
        var app = new Vue({
            el:"#app",
            data:{
                message:"黑马sxdgfv"
            },
            methods: {
                getm:function() {
                    alert(this.message)
                },
                setm:function() {
                    this.message="hahha";
                }
            }
        })
    </script>
```

