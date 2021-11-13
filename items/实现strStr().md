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

