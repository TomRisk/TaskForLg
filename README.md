1、下面关于虚拟 DOM 的说法正确的是：
A. 使用虚拟 DOM 不需要手动操作 DOM，可以极大的提高程序的性能。

B. 使用虚拟 DOM 不需要手动操作 DOM，可以极大的提高开发效率。

C. 虚拟 DOM 可以维护程序的状态，通过对比两次状态的差异更新真实 DOM。

D. 虚拟 DOM 本质上是 JavaScript 对象，可以跨平台，例如服务器渲染、Weex 开发等。

2、下面关于 Snabbdom 库的描述错误的是：
A. Snabbdom 库是一个高效的虚拟 DOM 库，Vue.js 的虚拟 DOM 借鉴了 Snabbdom 库。

B. 使用 h() 函数创建 VNode 对象，描述真实 DOM 结构。

C. Snabbdom 库本身可以处理 DOM 的属性、事件、样式等操作。

D. 使用 patch(oldVnode, null) 可以清空页面元素

简答题
1、请简述 patchVnode 函数的执行过程。


答案
1.D
2.D
3. 
  01.调用prepatch钩子函数、update钩子函数（对比之前）
  02.postpatch钩子函数（节点触发之后）
  03.判断节点中是否有text属性，且不等于旧节点的text属性。则更新dom元素的文本内容。如果老节点有children，则移除老节点children对应的dom元素。设置新节点对应dom元素的textContent
  04.新老节点都有children，且不相等，则对比两个节点的所有子节点(调用updatechildren，更新差异)。
  05.只有新节点有children属性(老节点没有时)，如果老节点有text属性，则清空对应老节点的textcontent，再调用addvnodes添加所有的子节点。
  06.若老节点有children属性，新节点没有children属性，则移除所有的老节点
  07.只有老节点有text属性，新节点没有text属性，清空对应元素的textcontent
