# 内部对象

## 5.1、Date

**基本使用**

```javascript
var now = new Date();
        now.getFullYear();//年
        now.getMonth();//月,国外月份为0-11；
        now.getDate();//日
        now.getDay();//星期几
        now.getHours();//小时
        now.getMinutes();//分
        now.getSeconds();//秒
        now.getTime();//时间戳  全世界统一，1970-1-1 0:00:00 毫秒数
```

**转化**

```javascript
now = new Date(1643939596309)
Date Fri Feb 04 2022 09:53:16 GMT+0800 (中国标准时间)

now.toDateString()//注意调用一个方法不是一个属性；
"Fri Feb 04 2022"
now.toGMTString()
"Fri, 04 Feb 2022 01:53:16 GMT"
```

## 5.2、JSON

JSON：