* 来源：LeetCode 28题  
* 难度：简单  
* 题目：  

``` 
      实现 strStr() 函数。给你两个字符串 haystack 和 needle ，请你在 haystack 字符串中找出 needle 字符串出现的第一个位置（下标从 0 开始）。如果不存在，则返回  -1 。  
```
* 示例一：  

``` 
      输入：haystack = "hello", needle = "ll"
      输出：2
```
      
* 示例二：  

``` 
      输入：haystack = "", needle = ""
      输出：0
``` 
      
* 示例三：  

``` 
      输入：haystack = "hello", needle = "ll"
      输出：-1
```
      
* 题解一：  

``` 
      /**
      @param{string}heystack
      @param{string}needle
      @return{number}
      */
      var strStr=function(heystack,needle){
          return heystack.indexOf(needle);
      }
```

* 题解二：  

``` 
      /**
      @param{string}heystack
      @param{string}needle
      @return{number}
      */
     var strStr = function(haystack, needle) {
        //return haystack.indexOf(needle);
        //暴力求解
        let n=haystack.length;
        let m=needle.length;
        for(let i=0;i+m<=n;i++){
            let flag=true;
            for(let j=0;j<m;j++){
                if(haystack[i+j]!=needle[j]){
                    flag=false;
                    break;
                }
            } 
            if(flag){
                return i;
            }
        }
        return -1;
};

``` 

* 拓展一：若needle重复出现返回所有位置  

``` 
      /**
      @param{string}heystack
      @param{string}needle
      @return{number}
      */
     var strStr = function(haystack, needle) {
        //return haystack.indexOf(needle);
        //暴力求解
        let n=haystack.length;
        let m=needle.length;
        let arr=[];
        for(let i=0;i+m<=n;i++){
            let flag=true;
            for(let j=0;j<m;j++){
                if(haystack[i+j]!=needle[j]){
                    flag=false;
                    break;
                }
            } 
            if(flag){
                arr.push(i);
            }
        }
        if(arr.length>0){
            return arr.join(",");  
        }
        return -1;
        
};

```


