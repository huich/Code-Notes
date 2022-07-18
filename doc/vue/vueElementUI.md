## vue Element UI 

[官方文档](https://element.eleme.cn/#/zh-CN/component/installation) 

### 关于vue Element UI 的介绍 

Element UI是由于饿了么前端团队基于VUE封装的UI组件库，提供了PC端组件，简化了常用组件的封装，降低了开发难度。 

### 安装 

``` 
npm i element-ui -S

 i : 安装指令，全拼：install
-S :生产环境，全拼：--save
-D :开发环境，全拼：--save--dev
-O :可选依赖，全拼：--save--optional
-E :精确安装指定模块版本，全称：--save--exact
-g：全局安装，全拼：--global
``` 

### 引入 

这里接收完成版引入，在main.js中写入一下语句。 

``` 
import ElementUI from 'element-ui'
import 'element-ui/lib/theme-chalk/index.css'
Vue.use(ElementUI)
``` 

你会发现 import 'element-ui/lib/theme-chalk/index.css' 文件你没有，这时候在根目录建立文件夹style，生成index.css,
在一下位置复制出样式内容。

<div align="center">
    <img src="https://github.com/huich/Code-Notes/blob/main/imgs/vueeleUI1.png">
    <img src="https://github.com/huich/Code-Notes/blob/main/imgs/vueeleUI2.png">
    <img src="https://github.com/huich/Code-Notes/blob/main/imgs/vueeleUI3.png">
    <img src="https://github.com/huich/Code-Notes/blob/main/imgs/vueeleUI4.png">
</div> 

然后你会发现报未引入"element-icons.ttf"和"element-icons.woff"错误，同样引入报错的字体文件。 

<div align="center">
   <img src="https://github.com/huich/Code-Notes/blob/main/imgs/vueeleUI6.png">
</div> 

``` 
// 引入element UI
import ElementUI from 'element-ui'
import './style/index.css';
import './style/fonts/element-icons.ttf';
import './style/fonts/element-icons.woff';
Vue.use(ElementUI)
``` 

引入element UI 样式，成功显示。 

<div align="center">
    <img src="https://github.com/huich/Code-Notes/blob/main/imgs/vueeleUI7.png">
</div> 




