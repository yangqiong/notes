## HOC 高阶组件
是一个函数，参数是一个组件，返回一个新组件。

### 实战
封装页面做身份鉴权，参考https://hackernoon.com/role-based-authorization-in-react-c70bb7641db4

**提前生成高阶组件，而不是每次重新生成。**不然每次会生成新的节点，而不是复用原来的节点。
参考https://reactjs.org/docs/higher-order-components.html#dont-use-hocs-inside-the-render-method

## 问题
1. `Can't call setState (or forceUpdate) on an unmounted component`

结果：warning 组件卸载后依然setState，可能引起内存泄露

可能的原因：
```
a. 在异步请求的结果里进行setState，但此时组件已卸载。设置一个_isMounted，在异步结果里判断组件是否已经卸载。
b. 在监听事件里进行setState，但此时组件已卸载。 在componentWillUnmount里取消监听。
c. 在setTimeout里进行setState, 但此时组件已卸载。在componentWillUnmount里clearTimeout。
```

