# 路由

# 引言
现代前端开发中最流行的页面模型，莫过于SPA单页应用架构。单页面应用指的是应用只有一个主页面，通过动态替换DOM内容并同步修改url地址，来模拟多页应用的效果，切换页面的功能直接由前台脚本来完成，而不是由后端渲染完毕后前端只负责显示。前端三驾马车Angular,Vue,React均基于此模型来运行的。SPA能够以模拟多页面应用的效果，归功于其前端路由机制。
# 路由分类
    - 前端路由
        - hash
        - history
    - 后端路由
# 实现原理

- HashChange
HTML页面中通过锚点定位原理可进行无刷新跳转，触发后url地址中会多出# + 'XXX'的部分，同时在全局的window对象上触发hashChange事件，这样在页面锚点哈希改变为某个预设值的时候，通过代码触发对应的页面DOM改变，就可以实现基本的路由了

- HTML5 HistoryAPI
HTML5的History API为浏览器的全局history对象增加的扩展方法。一般用来解决ajax请求无法通过回退按钮回到请求前状态的问题。
    - history.forward(); //在历史记录中前进一步
    - history.back(); //在历史记录中后退一步
    - history.go(n): //在历史记录中跳转n步骤，n=0为刷新本页,n=-1为后退一页。在HTML5中，window.history对象得到了扩展，新增的API包括：
    - history.pushState(data[,title][,url]);//向历史记录中追加一条记录
    - history.replaceState(data[,title][,url]);//替换当前页在历史记录中的信息。
    - history.state;//是一个属性，可以得到当前页的state信息。
    - window.onpopstate;//是一个事件，在点击浏览器后退按钮或js调用forward()、back()、go()时触发。监听函数中可传入一个event对象，event.state即为通过pushState()或replaceState()方法传入的data参数。

# Vue路由

- 下载插件
    ```cmd
        npm install --save vue-router
    ```

```jsx
    import Vue from 'vue'
    import VueRouter from 'vue-router'

    const router = new VueRouter({
        /**
        * RouterName 路由名称 String类型
        * ComponentsName 组件名称 
        */
        path:'<RouterName>',
        component:< ComponentsName>
    })
    /**
    * Vue全局挂载
    * 通过this.$router可以访问全局路由对象
    *通过this.$route 访问当前路由信息对象
    */
    Vue.use(VueRouter)
    new Vue({
        router : router
    })
```