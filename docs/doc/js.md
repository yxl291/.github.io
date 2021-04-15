> #### Promise

Promise是最早由社区提出和实现的一种解决异步编程的方案，比其他传统的解决方案（回调函数和事件）更合理和更强大。
ES6 规定，Promise对象是一个构造函数，用来生成Promise实例。

promise是为解决异步处理回调金字塔问题而产生的

1. Promise对象的状态不受外界影响
   
    Promise 有以上三种状态，只有异步操作的结果可以决定当前是哪一种状态，其他任何操作都无法改变这个状态

    - pending 初始状态
    - fulfilled 成功状态
    - rejected 失败状态
  
2. Promise的状态一旦改变，就不会再变，任何时候都可以得到这个结果，状态不可以逆，只能由 pending变成fulfilled或者由pending变成rejected
