> #### vuex有哪些部分构成
- state
- getters
- mutations
- actions
- moudules
> #### 什么场景下使用vuex
- 共享、方便管理、方便维护、组件传值...
- 项目：购物车管理、订单数据、用户登录信息...
> #### mutations和actions区别
- 本质区别
    - mutations 必须是同步函数
    - actions "可以包含"包含异步函数
- 使用区别
    - mutations可以放入函数，actions也可以放入函数，但是一般我们在 mutations放入函数而actions是提交mutations




...
> ####  vuex个人理解

- 是什么 专门为vue设计的状态管理工具，任何组件都可以操作数据；（mvc的）
- 有哪些属性   
    - state : 类似与data ，存放数据状态
    - getters   类似与computed，根据其他 getter 或 state 计算返回值。
    - nutations 同步的一些操作
    - actions  异步的操作 常用来提交mutations
    - moudules  可以将store拆分开来
- commit和dispatch区别
    - `this.$store.commit('loginStatus', 1);` 
        - 提交到mutations（同步操作）可用于登录成功后读取用户信息写到缓存里
    - `this.$store.dispatch('isLogin', true);`
        - 提交到actions（异步操作）可用于向后台提交数据
