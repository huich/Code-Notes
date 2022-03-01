## 目录 
<div align="center">
    <img src="https://github.com/huich/Code-Notes/blob/main/imgs/sftree.png">
</div>

## :pencil2: 算法
 
****** 

1. 动态规划 

    509.斐波那契数(简单) 
    状态转移方程：dp(n)=dp(n-1)+dp(n-2)

    ``` 
    const  fib=(n)=>{
        if(n<=1) return n;
        let arr=[0,1]
        for(let i=2;i<n;++i){
            arr[i]=arr[i-1]+arr[i-2];//状态转移方程
        }
        return arr[n]
    }
    ```






