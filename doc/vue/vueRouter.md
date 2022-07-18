## 二、vue Router 

[官方文档](https://router.vuejs.org/zh/) 

### 关于vue Router 的介绍 

Vue Router 是 Vue.js 的官方路由。 

### 安装 

``` 
npm install vue-router@3.1.3

or

yarn add vue-router@3.1.3
``` 
安装成功之后可看package.json、package-lock.json查看相关版本信息; 


### 定义router.js 

router.js 

``` 

import Vue from "vue"
import VueRouter from "vue-router"
Vue.use(VueRouter)

const routes=[
    {  
        path: '/', // 每次进入默认进入该路由
        component:()=>import('../components/HelloWorld.vue')
    },
    {  
        path: '/demo', // 每次进入默认进入该路由
        component: ()=>import('../pages/demo/index.vue')
    }
];

const router = new VueRouter({
    mode: 'history',
    history: process.env.BASE_URL,
    routes // 可直接简写成routes:routes
})

export default router
``` 

### 引入 

main.js 

``` 
import Vue from 'vue'
import App from './App.vue'
// 引入路由
import router from './tools/route.js'
// 引入element UI
import ElementUI from 'element-ui'
import './style/index.css';
import './style/fonts/element-icons.ttf';
import './style/fonts/element-icons.woff';
Vue.use(ElementUI)


Vue.config.productionTip = false

new Vue({
  router,
  render: h => h(App),
}).$mount('#app')
``` 

### 展示路由 router-view 

app.vue 

``` 
<template>
  <div id="app">
      <header-bar/>
          <router-view></router-view>
      <footer-bar/>
  </div>
</template>

<script>
import footerBar from '@/components/footer.vue'
import headerBar from '@/components/header.vue'
export default {
  name: 'App',
  components: {
    footerBar,
    headerBar
  },
  created(){
    console.log("router",this.$route)
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body{
  margin:0;
}

</style>
``` 




