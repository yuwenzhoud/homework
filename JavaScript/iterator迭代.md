# iterator

```JavaScript
var arr = [3,4,5];
//打印下标
for(var x in arr) {
    console.log(x)
}
//打印具体的值
for(var x of arr) {
    console.log(x)
}
```

遍历Map：

```javascript
var map = new Map(['tom',100],['jack',90],['haha',80]);
for(let x of map) {
    console.log(x);//每一组都输出了；
}
```

遍历Set：

```javascript
var set = new Set([6,7,8]);
for(let x of set) {
    console.log(x);//
}
```

