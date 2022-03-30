# Vue 实现公共确认框

首先需要明确公共弹框属于子组件； 
其次子组件可以由任意父组件复用；

### 父组件通过props将弹框显示内容contentObj{title、message、cancel、OK、确定回调、取消回调}传给子组件。

父组件:

```
 <commonDialog v-bind:contentObj="{
    title: '温馨提示',
    message: '支付宝到账100万元',
    cancel:'关闭',
    OK:'确定',
    successCallback:(para)=>{
      //某方法
    },
    closeCallBack:(para)=>{
      //某方法
    }
  }"></commonDialog>
```

子组件： 

```
props:{
  content{
    title:'',
    message:'',
    cancel:'',
    OK:''
  }
}

ok:function(){
  if(content.successCallback){
      content.successCallback(para);
  }
}

```

