# API
初始化dva项目
```jsx
    import dva from 'dva';
    import createHistory from 'history/createBrowserHistory';
    const app = dva({
        // history：指定给路由用的 history，默认是 hashHistory
        history: createHistory(),
        // 指定初始数据，优先级高于 model 中的 state，默认是 {}
        initialState:{},
        onError,
        onAction,
        onStateChange,
        onReducer,
        onEffect,
        onHmr,
        extraReducers,
        extraEnhancers,
    })
    //配置hooks或者配置插件
    app.use()
    //挂载状态管理的model
    app.model()
    //取消 model 注册，清理 reducers, effects 和 subscriptions。subscription 如果没有返回 unlisten 函数，使用 app.unmodel 会给予警告
    app.unmodel()
    app.start('#root')
```

# dva-router
定义路由
```jsx
    import { Router, Route, routerRedux } from 'dva/router';
    app.router(({ history }) => {
    return  <Router history={history}>
            <Route path="/" component={App} />
        </Router>
    });
```

# dva-fetch
请求数据
```jsx
    import {fetch} from 'dva';
```

# dva-dynami
动态加载组件
```jsx
    import {dynamic} from 'dva';

    const UserPageComponent = dynamic({
        //dva实例，加载model需要用到
        app,
        //绑定的model
        models: () => [
            import('./models/login'),
        ],
        component: () => import('./containers/login'),
    });
```