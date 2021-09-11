# 深拷贝实现的方法

## 首先要明确几个问题 ##

Q1:什么是浅拷贝(shallow copy)和深拷贝(deep copy)?

A1:浅拷贝和深拷贝最根本的区别就是存储区域是否指向同一个地址，当声明一个对象时，计算机会在内存上分配一个地址给它，当你把这个对象付给另外一个变量的时候，这时候就会出现浅拷贝和深拷贝的情况，指向同一内存为浅拷贝，不同内存为深拷贝、

Q2:什么情况下使用浅拷贝或深拷贝？

A2:存在一个对象A，将A赋值给B，修改A的数据会影响到B，当你不想这样的情况发生，这时候你就要使用深拷贝来解决。

### 以下是实现深拷贝的三种方法

方法一 使用递归方式实现深拷贝:

```
 //使用递归的方式实现数组、对象的深拷贝
    function deepClone(obj) {
      //判断obj是数组还是对象.
      var objClone = Array.isArray(obj) ? [] : {};
      //进行深拷贝的不能为空，并且是对象或者是"object"
      if (obj && typeof obj === "object") {
        for (key in obj) {
          if (obj.hasOwnProperty(key)) {
            if (obj[key] && typeof obj[key] === "object") {
              objClone[key] = deepClone(obj[key]);
            } else {
              objClone[key] = obj[key];
            }
          }
        }
      }
      return objClone;
    }
```

方法二 使用JSON对象实现深拷贝

```
/*
使用js内置JSON实现深拷贝
缺陷：无法实现对对象中方法的深拷贝
*/
function deepCloneJson(obj){
    let objJson=JSON.stringify(obj);
    let objClone=JSON.parse(objJson);
    return objClone;
}

```
方法三 通过JQuery中的extend()方法实现数组深拷贝

```
/*
使用JQ中的extend来实现数组深拷贝
*/
function deepCloneExtend(arr){
    let arrClone=[];//es6 
    arrClone=$.extend(true,[],arr);
    return arrClone;
}

```
