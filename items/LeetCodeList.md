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

    62.不同路径(中等) 
    状态转移方程：f[i][j]=f[i-1][j]+f[i][j-1]; 
    
    ```
    const uniquePaths=(m,n)=>{
        const dp=Array(m).fill().map((item)=>Array(n).fill(0));
        //初始化列
        for(let i=0;i<m;i++){
            dp[i][0]=1;
        }
        //初始化行
        for(let j=0;j<n;j++){
            dp[0][j]=1;
        }
        for(let i=1;i<m;i++){
            for(let j=1;j<n;j++){
                dp[i][j]=dp[i-1][j]+dp[i][j-1];
            }
        }
        return dp[m-1][n-1];
    }
    ``` 

    63.不同路径2(中等) 
    状态转移方程：f[i][j]=f[i-1][j]+f[i][j-1] 

    ``` 
    const uniquePathWithObstacles=(obstacleGrid)=>{
        const m=obstacleGrid.length;
        const n=obstacleGrid[0].length;

    }
    ```









