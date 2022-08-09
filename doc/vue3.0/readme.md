# :point_right:  VUE 3.0 + TS

[vite官网](https://cn.vitejs.dev/guide/#scaffolding-your-first-vite-project) 
[node官网](https://nodejs.org/zh-cn/) 

### 生态系统 

* 构建工具 vite 2.x 
* vue版本 vue3.x 
* vue官方路由 vue router 4.x 
* 开发语言 TS 
* 状态管理工具 vuex4.x 
* 请求工具 axios 

### 框架搭建 

* 需要安装node.js 版本要求大于14.18+，16+ 查看版本 
``` 
    node -v 
``` 

* 建议将node升级到稳定版本 
``` 
    nvm node stable 
``` 

### 使用vite初始化项目 

* 获取项目框架 
``` 
    npm init vite 
``` 
* 输入项目名称 默认 vite-project 

* 选择第三方框架 
<div align="center">
    <img src="https://github.com/huich/Code-Notes/blob/main/imgs/vite1.png">
</div> 

* 选择ts 
<div align="center">
    <img src="https://github.com/huich/Code-Notes/blob/main/imgs/vite2.png">
</div> 

* 执行命令，运行框架 
``` 
    cd vite-project 
    npm install 
    npm run dev
``` 

* 效果 
<div align="center">
  <img src="https://github.com/huich/Code-Notes/blob/main/imgs/vite3.png">
</div> 

#### vite+vue3.0+ts的框架已经搭建完成，下面我们来为这个项目集成 Vue Router、Axios、Vuex、Element Plus、Stylus/Sass/Less。 

* 修改vite配置文件 

Vite 配置文件 vite.config.ts 位于根目录下，项目启动时会自动读取。
本项目先做一些简单配置，例如：设置 @ 指向 src 目录、 服务启动端口、打包路径、代理等。
关于 Vite 更多配置项及用法，请查看 Vite [官网](https://cn.vitejs.dev/config/)。 

``` 
    import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'
// 如果编辑器提示 path 模块找不到，则可以安装一下 @types/node -> npm i @types/node -D
import { resolve } from 'path'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [vue()],
  resolve: {
    alias: {
      '@': resolve(__dirname, 'src') // 设置 `@` 指向 `src` 目录
    }
  },
  base: './', // 设置打包路径
  server: {
    port: 4000, // 设置服务启动端口号
    open: true, // 设置服务启动时是否自动打开浏览器
    cors: true // 允许跨域

    // 设置代理，根据我们项目实际情况配置
    // proxy: {
    //   '/api': {
    //     target: 'http://xxx.xxx.xxx.xxx:8000',
    //     changeOrigin: true,
    //     secure: false,
    //     rewrite: (path) => path.replace('/api/', '/')
    //   }
    // }
  }
})
``` 

* 目录配置 
``` 
    ├── publish/
    └── src/
        ├── assets/                    // 静态资源目录
        ├── cache/                     // 本地存储目录
        ├── common/                    // 通用类库目录
        ├── components/                // 公共组件目录
        ├── router/                    // 路由配置目录
        ├── store/                     // 状态管理目录
        ├── style/                     // 通用 CSS 目录
        ├── utils/                     // 工具函数目录
        ├── views/                     // 页面组件目录
        ├── App.vue
        ├── main.ts
        ├── shims-vue.d.ts
    ├── tests/                         // 单元测试目录
    ├── index.html
    ├── tsconfig.json                  // TypeScript 配置文件
    ├── vite.config.ts                 // Vite 配置文件
    └── package.json
``` 

* 集成vue Router 
``` 
    npm i vue-router@4
``` 

* 创建 src/router/index.ts 文件 
``` 
     └── src/
     ├── router/
         ├── index.ts  // 路由配置文件
``` 

``` 
    import {
      createRouter,
      createWebHashHistory,
      RouteRecordRaw
    } from 'vue-router'
    import Home from '@/views/home.vue'
    import Vuex from '@/views/vuex.vue'

    const routes: Array<RouteRecordRaw> = [
      {
        path: '/',
        name: 'Home',
        component: Home
      },
      {
        path: '/vuex',
        name: 'Vuex',
        component: Vuex
      },
      {
        path: '/axios',
        name: 'Axios',
        component: () => import('@/views/axios.vue') // 懒加载组件
      }
    ]

    const router = createRouter({
      history: createWebHashHistory(),
      routes
    })

    export default router
``` 

* 在 main.ts 文件中挂载路由配置 
``` 
    import { createApp } from 'vue'
    import App from './App.vue'

    import router from './router/index'

    createApp(App).use(router).mount('#app')
``` 


