### vuex （程序中所有组件的集中存储，确保状态以可预测的方式变更）

​	

**state** 初始状态

**mutations** 状态突变，commit来触发状态更改

+ 不同模块的mutations通过commit触发
+ 同名会依次触发不会报错

**getters** 相当于store的计算属性，它的结果基于依赖进行缓存，当依赖改版时重新计算，

+ 第一个参数是state（当前模块内的state）
+ 第二个参数是getters（其他模块的getter）
+ 第三个参数是rootState（全局的state）
+ 通过给返回的函数实现将参数传给getter
+ 通过方法访问的getter，结果不会被缓存，每次被调用时都会运行
+ 同名的getters会报错

**actions** **（接收一个上下文对象 context）** 可以通过解构赋值简化代码

+ 通过context.commit('fn') 提交突变
+ 通过context.state访问状态
+ 通过context.getters访问getter
+ store.dispatch(‘fn’) 触发以上操作
+ 同名的action，通过store.dispatch('fn')会依次触发

*** 在vuex中，访问的时候，state是唯一会通锅模块的别名来添加层级，其他getters，mutations，actions，都是直接合并在store下**

*** 将store 中的satate绑定到vue的computed计算属性要，要更改state的值，要通过mutations或者action来更新，在组件中直接赋值是不会生效的**

































