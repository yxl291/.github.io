> #### 生命周期

| 生命周期 | 生命周期 |
| -------- | -------- |
| beforeCreate   | 组件实例被创建之初，组件的属性生效之前   |
| created   | 组件实例已经完全创建，属性也绑定，但真实dom还没有生成，$el还不可用   |
| beforeMount   | 在挂载开始之前被调用：相关的 render 函数首次被调用  |
| mounted   | el 被新创建的 vm.$el 替换，并挂载到实例上去之后调用该钩子   |
| beforeUpdate   | 组件数据更新之前调用，发生在虚拟 DOM 打补丁之前   |
| update   | 组件数据更新之后   |
| activited   | keep-alive专属，组件被激活时调用   |
| deadctivated   | keep-alive专属，组件被销毁时调用   |
| beforeDestory   | 组件销毁前调用   |
| destoryed   | 组件销毁后调用   |

- 进去界面或者组件，会执行那些生命周期？
    - beforeCreate
    - created
    - beforeMount
    - mounted

- 那些节点有$el(根节点)，$data(数据)
    - beforeCreate **没有**
    - created   **有data无el**
    - beforeMount **有data无el**
    - mounted **都有**

- 如果加入了keep-alive，第二次或者第N次进入组件会执行那些生命周期？只执行一个生命周期：**activated**

> #### keep-alive的了解

- 是什么
    - vue自带的组件，功能：用来缓存组件
- 使用场景
    -缓存组件，提升项目性能。例如：首页进入详情，用户多次相同操作，没必要请求多次，直接缓存即可。

> #### v-model双向数据绑定原理

vue 双向数据绑定是通过 **数据劫持** 结合 **发布订阅模式** 的方式来实现的，也就是说数据和视图同步，数据发生变化，视图跟着变化，视图变化，数据也随之发生改变； 核心：**Object.defineProperty()** 方法。

v-model本质上是语法糖，v-model在内部为不同的输入元素使用不同的属性并抛出不同的事件

* text 和 textarea 元素使用 value 属性和 input 事件

* checkbox 和 radio 使用 checked 属性和 change 事件

* select 字段将 value 作为 prop 并将 change 作为事件

> #### computed和watch区别

* computed 是计算属性，它会根据你所依赖的数据动态显示新的计算结果 计算属性将被加入到 Vue 实例中。所有 getter 和 setter 的 this 上下文自动地绑定为 Vue 实例,通过计算出来的属性不需要调用直接可以在 DOM 里使用

    - 如果一个数据需要经过复杂计算就用 **computed**

* 一个对象，键是 data 对应的数据，值是对应的回调函数。值也可以是方法名，或者包含选项的对象，当 data 的数据发生变化时，就会发生一个回调，他有两个参数，一个 val （修改后的 data 数据），一个 oldVal（原来的 data 数据）
Vue 实例将会在实例化时调用$watch()，遍历 watch 对象的每一个属性
    
    - 如果一个数据需要被监听并且对数据做一些操作就用 **watch**

> #### 观察者模式(订阅模式)

观察者模式或者说订阅模式，它定义了对象间的一种一对多的关系，让多个观察者对象同时监听某一个主题对象，当一个对象发生改变时，所有依赖于它的对象都将得到通知。


> #### nexttick是什么？

- 获取dom更新后的一些操作