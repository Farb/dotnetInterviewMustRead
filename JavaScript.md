# JavaScript
## 1. 如何理解闭包？
    
[MDN 闭包解释](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Closures )

个人理解：闭包是有权限访问其他函数作用域内的变量的一个函数。

 由于在JS中，变量的作用域属于函数作用域，在函数执行后作用域就会被清理、内存也随之回收，但是由于闭包是建立在一个函数内部的子函数，由于其可访问上级作用域的原因，即使上级函数执行完，作用域也不会随之销毁，这时的子函数——也就是闭包，便拥有了访问上级作用域中的变量的权限，即使上级函数执行完后作用域内的值也不会被销毁。
    
#### 闭包解决了什么？

由于闭包可以缓存上级作用域，那么就使得函数外部打破了“函数作用域”的束缚，可以访问函数内部的变量。以平时使用的Ajax成功回调为例，这里其实就是个闭包，由于上述的特性，回调就拥有了整个上级作用域的访问和操作能力，提高了极大的便利。开发者不用去写钩子函数来操作上级函数作用域内部的变量了。

#### 闭包有哪些应用场景
闭包随处可见，一个Ajax请求的成功回调，一个事件绑定的回调方法，一个setTimeout的延时回调，或者一个函数内部返回另一个匿名函数，这些都是闭包。简而言之，无论使用何种方式对函数类型的值进行传递，当函数在别处被调用时都有闭包的身影

#### 闭包有哪些不好的地方？
1. 原理比较深奥：要想完全掌握闭包，一定要清楚函数作用域、内存回收机制、作用域继承等，然而闭包是随处可见的，很可能开发者在不经意间就写出了一个闭包，理解不够深入的话很可能造成运行结果与预期不符。
2. 代码难以维护：闭包内部是可以缓存上级作用域，而如果闭包又是异步执行的话，一定要清楚上级作用域都发生了什么，而这样就需要对代码的运行逻辑和JS运行机制相当了解才能弄明白究竟发生了什么。

#### null 和 undefined 的区别？

#### == 和 === 的区别？
