## vue CLI 

[官方文档](https://cli.vuejs.org/zh/) 

### 关于vue cli 的介绍 

CLI是commend line interface 的缩写，即命令界面。Vue CLI是一个基于Vue.js进行快速开发的完整系统。 

CLI (@vue/cli) 是一个全局安装的 npm 包，提供了终端里的 vue 命令。它可以通过 vue create 快速搭建一个新项目，或者直接通过 vue serve 构建新想法的原型。 

### 安装CLI 

1. 安装一个新包，执行以下命令； 

``` 
npm install -g @vue/cli
# OR
yarn global add @vue/cli 
``` 

2. 检查安装版本确认是否安装成功； 

``` 
vue --version 
``` 

3. 如需升级； 

``` 
npm update -g @vue/cli

# 或者
yarn global upgrade --latest @vue/cli
``` 

### 使用CLI创建一个新项目 

1. 创建一个vue项目； 

``` 
vue create hello world 
``` 

[hello world](https://github.com/huich/hello-world) 