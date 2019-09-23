# 组件通讯

# 组件通讯

 - 父子通讯

    ```vue
        <Children :params="<varible>"></Children>

        // children.vue
        {
            props:['params]
        }
    ```

 - 子父通讯
    -  $emit()
        //chilren.vue
        ```vue
            this.$emit('<EventName>', ...params)
        ```
        //parent.vue

        ```vue
            <Children @EventName="callbackHandler"></Children>

            {
                methods:{
                    callbackHandler(...reset){
                        //通过es6reset获取子组件传递的参数
                        console.log(reset)
                    }
                }
            }
        ```
    -  回调函数

 - 非父子通讯（同级组件，跨级组件）
    Vue.prototype.$Bus = new Vue();
    this.$Bus.$emit('<EventName>',...params);
    this.$Bus.$on('EventName', callback)

 - 状态管理 - Vuex

 -  理解为什么要使用状态管理


 # 生猛上手 Vuex
 