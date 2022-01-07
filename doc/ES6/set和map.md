### set和map

#### set

#### map 

  * 定义
    
    为了解决JavaScript中对象键值对的键值只能用字符串的问题，ES6提供了Map数据结构。各种类型的值都可以当做键，包括对象 是一种更完善的hash结构实现。
    
  * 属性和操作方法 
  
    1. size属性

       返回Map的成员总数。
       
       ``` 
       const map=new Map();
       map.set("one",1);
       map.set("two",2);
       
       map.size;//2
       ``` 
       
    2. Map.prototype.set(key,value) 
       
       set方法设置键名和键值，然后返回map的整个结构，若已有键名则重新复制。
       
       ``` 
       const map=new Map();
       
       map.set(undefined,"undefined"); //键值是undefined
       map.set(222,"数字");//键值是数字
       map.set("数字",222);//键值是字符串
       ```
       
       set方法返回map对象，因此可以用链式写法。
       
       ``` 
       let map=new Map().set("1",1).set("2",2).set("3",3);
       ```
    
    3. Map.prototype.get(key) 
    
       get方法是读取key值对应的value，没有对应的key返回undefined.
       
       ``` 
       const map=new Map();
       map.set("one",1);
       map.get("one");//1
       ```
       
    4. Map.prototype.has(key)
       
       has发法表示Map中是否有某个键，返回布尔值。
       
       ``` 
       let map=new Map().set("1",1).set("2",2).set("3",3);
       
       map.has("1");//true
       map.has("4");//false
       
       ```
       
    5. Map.prototype.delete(key) 
    
       delete方法用来删除map中的某个键，删除成功返回true，失败返回false。
       
       ``` 
       const map=new Map().set(undefined,"undefined").set(456,"number");
       
       map.delete(undefined);
       map.has(undefined);//false
       ```
       
    6. Map.prototype.clear() 
       
       clear方法用来清除所有值，没有返回值。
       
       ``` 
       const map=new Map().set(undefined,"undefined").set(456,"number");
       
       map.size;//2
       map.clear();
       map.size;//0
       ```
  
    
    
