# Map

匹配检索

```javascript
var map = new Map(['tom',100],['jack',90],['dom',80]);
var name = map.get('tom');//通过key获得value；
console.log(name);
//set新增或修改;
map.set('admin',123456);
//delete删除某一组数据；
map.delete('tom');
```

# Set

无须不重复的集合

```javascript
var set = new Set([1,1,1,2]);
console.log(set);//输出1，2；
//1.添加
set.add('3')//添加数字；
console.log(set);//输出1，2，3；
//2.删除
set.delete('1')//删除数据；
console.log(set);//输出2，3；
//3.判断是否包含某个元素；
console.log(set.has(3));
//true;
```

