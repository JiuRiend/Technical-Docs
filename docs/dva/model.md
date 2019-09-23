## 状态管理 - model
```jsx
    export default {
        namespace: '<string|modelname>',
        state: {},
        subscriptions: {
            setup({ dispatch, history }) {
                // eslint-disable-line
            },
        },
        effects: {
            *fetch({ payload }, { call, put }) {  
                // eslint-disable-line
                yield call(<function|apiServer>,<Any|params>)
                yield put({ type: 'save' });
            },
        },
        reducers: {
            save(state, action) {
            return { ...state, ...action.payload };
            },
        }
    };

```
## model
dva用来做状态管理的，内置了redux-sage 使用generator的语法，完成异步请求处理
## namespace - 命名空间 
model 的命名空间，同时也是他在全局 state 上的属性，只能用字符串，不支持通过 . 的方式创建多层命名空间。

## state - 状态
state是 一个model的初始值，优先级低于传给 dva() 的 opts.initialState。
```jsx
    const app = dva({
        initialState: { count: 1 },
    });
    app.model({
        namespace: 'count',
        state: 0,
    });
    //app.start() 后 state.count 为 1 
```

## reducers - 纯函数
以 key/value 格式定义 reducer。用于处理同步操作，唯一可以修改 state 的地方。由 action 触发

```jsx
    格式为 *(action, effects) => void 或 [*(action, effects) => void, { type }]。
```

## effects -
以 key/value 格式定义 effect。用于处理异步操作和业务逻辑，不直接修改 state。由 action 触发，可以触发 action，可以和服务器交互，可以获取全局 state 的数据等等

```jsx
    格式为 *(action, effects) => void 或 [*(action, effects) => void, { type }]。
```

type 类型有：
- takeEvery
- takeLatest
- throttle
- watcher