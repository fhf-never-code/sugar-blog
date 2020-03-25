# Q&A

前端面试常见问题及个人的结论整

## js
<solve ok>[原始类型有哪些？](../other/primitive.md#原始值类型)</solve>
<solve ok>[null是对象吗？](../other/primitive.md#null)</solve>
<solve ok>[为什么0.1+0.2!=0.3?](./zero.md)</solve>
<solve ok>[对象类型与原始类型的不同之处?](./objDfValue.md)</solve>
<solve ok>[函数参数是对象会发生什么问题?](./objparam.md)</solve>
<solve ok>[typeof能否正常判断类型?](./typeof.md)</solve>
<solve ok>[instanceof能正确判断类型的原因是什么?](./instanceof.md)</solve>
<solve ok>[原型与原型链?](../js/prototype.md)</solve>
<solve ok>[如何正确判断this?](../other/this.md)</solve>
<solve ok>[箭头函数的this是什么?](../other/this.md)</solve>
<solve ok>[==与===有什么区别?](../other/equal.md)</solve>
<solve ok>[什么是闭包?](../js/closure.md)</solve>
<solve ok>[深拷贝与浅拷贝?](../other/copy.md)</solve>
<solve ok>[为什么使用模块化？实现模块化的几种方式](../other/module.md)</solve>
<solve ok>[Promise的特点/优点/缺点？](../other/promise.md#特点)</solve>
<solve ok>[什么是Promise链？](../other/promise.md#promise链)</solve>
<solve ok>[Promise构造函数执行和then函数执行有什么区别？](../other/promise.md#promise链)</solve>
<solve ok>[async及await的特点/优点/缺点是什么？]((../other/asyncawait.md))</solve>
<solve ok>[await原理是什么？](../other/asyncawait.md)</solve>
<solve ok>[new原理是什么？](../other/new.md)</solve>
<solve ok>[new创建对象与字面量创建对象的区别？](../other/new.md)</solve>
<solve ok>[v8下的垃圾回收机制？](../other/v8garbage.md)</solve>
<solve ok>[事件触发过程是怎么样的？](../other/event.md)</solve>
<solve ok>[什么是事件代理？](../other/event.md)</solve>
<solve ok>[什么是跨域？使用同源策略的原因？](../other/cros.md)</solve>
<solve ok>[解决跨域的方式？](../other/cros.md)</solve>
<solve ok>[什么是预检请求？](../other/cros.md#预检请求)</solve>
<solve ok>[什么是函数柯里化？](../js/currying.md#柯里化)</solve>
<solve ok>[JS的垃圾回收机制？](../js/garbage.md)</solve>
<solve ok>[节流与防抖？](../js/throttling.md#防抖)</solve>
<solve ok>[浏览器与Node中event loop?他们有何不同？](../js/eventloop.md)</solve>
<solve ok>[概述一下js中的词法作用域？](../js/scope.md)</solve>

## css
<solve ok>[什么是回流与重绘？](../css/reflow.md#回流)</solve>
<solve ok>[什么是盒模型？](../css/box.md)</solve>
<solve ok>[CSS的层级关系？](../css/level.md)</solve>
<solve ok>[什么是BFC？](../css/bfc.md)</solve>
<solve>[什么是IFC？](../css/ifc.md)</solve>
<solve ok>[flex弹性布局？](../css/flex.md)</solve>
<solve>grid布局？</solve>
<solve ok>[display属性有哪些?作用分别是什么?](./../css/display.md)</solve>
<solve ok>[position的值有哪些?](./../css/position.md)</solve>

## vue
<solve>[实现数据的响应式的原理？](../vue/bindData.md)</solve>
<solve>路由原理,为什么浏览器不会刷新</solve>

## ES6
<solve ok>[常见es6问题?](../js/es6.md)</solve>
<solve ok>[Symbol的用法?](../js/symbol.md)</solve>
<solve ok>[箭头函数特点?](../js/arrowfun.md#特点)</solve>
<solve ok>[什么是提升/暂时性死区?var/let/const区别](../other/promote.md)</solve>

## 浏览器
<solve ok>[浏览器的缓存机制？](../performance/cache.md)</solve>
<solve ok>[什么是强缓存/协商缓存？](../performance/cache.md#强缓存)</solve>
<solve ok>[协商缓存的作用？如何工作的？](../performance/cache.md#协商缓存)</solve>
<solve ok>[浏览器安全问题？](../internet/safe.md)</solve>


## 编程题
<solve ok>如何实现继承？</solve>
<solve ok>实现new</solve>
<solve ok>节流与防抖实现</solve>
<solve ok>实现call/apply/bind</solve>
<solve ok>实现setTimeout/setInterval</solve>
<solve>并发请求?</solve>
<solve ok>实现一个ajax</solve>
<solve ok>vue原理</solve>
<solve ok>如何实现垂直居中</solve>
<solve>KMP</solve>
<solve ok>quicksort</solve>
<solve ok>实现36进制转换</solve>
<solve>树的遍历方式,前/中/后,层次</solve>
<solve>对称二叉树</solve>
<solve ok>实现36进制转换</solve>

## 网络
<solve ok>[概述一下TCP？](../internet/tcp.md)</solve>
<solve ok>[概述一下UDP？](../internet/udp.md)</solve>
<solve ok>[TCP与UDP区别？](../internet/tcp-udp.md)</solve>
<solve ok>[概述HTTP？](../internet/http.md)</solve>
<solve ok>[HTTP与HTTPS的区别?](../internet/http.md#HTTPS)</solve>
<solve ok>[TLS协议握手过程,如何工作的？](../internet/http.md#TLS)</solve>
<solve ok>[HTTP2的特点?](../internet/http.md#http-2)</solve>
<solve ok>[如何才能使用HTTP2?有什么前提条件?](../internet/http.md#如何使用)</solve>
<solve ok>[HTTP3中使用的QUIC协议基于UDP的原因?](../internet/http.md#QUIC)</solve>
<solve ok>[如果响应头Content-Length=0那么是发出来被截取了还是没发出来?](../internet/clength.md)</solve>

## 操作系统
<solve>线程与进程的概念/区别/如何工作的?</solve>
<solve>进程之间如何进行切换的?</solve>
<solve>[进程和线程怎么通信?](../os/communicate.md)</solve>

## 综合问题
<solve ok>[怎么理解前端工程化？](./engineering.md)</solve>
<solve ok>[浏览器输入url之后到网页显示发生了什么？](./inputurl.md)</solve>

## 非技术问题