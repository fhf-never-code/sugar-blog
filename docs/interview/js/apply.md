# apply,call,bind 的异同

## 相同点
1. 更改this指向
:::tip
bind 会返回一个新的函数
:::

```js
let obj = {
    a: 1,
    b: 2,
    test() {
        console.log(this.a + this.b)
    }
}

obj.test()  // 3
obj.test.apply({ a: 2, b: 2 })  // 4
obj.test.call({ a: 3, b: 3 }) // 6
obj.test.bind({ a: 4, b: 4 })() // 8
```
## 不同点
传参方式不一样
* bind(this,...argv)
* call(this,...argv)
* apply(this,[...argv])

```js
function test(a, b) {
    console.log(this, a + b)
}

test.call('call', 1, 2) // [String: 'call'] 3
test.apply('apply', [2, 4]) // [String: 'apply'] 6
test.bind('bind', 3, 6)() // [String: 'bind'] 9
```

## 简单实现
测试用例
```js
function test(a, b) {
    console.log(this, a + b)
}
```
### mycall
```js
Function.prototype.mycall = function (thisArg) {
    if (typeof this !== 'function') {
        throw "error"
    }
    if (!(thisArg instanceof Object)) {
        thisArg = new Object(thisArg)
    }
    thisArg = thisArg || window
    thisArg.fn = this
    let args = [...arguments].slice(1)
    let res = thisArg.fn(...args)
    delete thisArg.fn
    return res
}
test.mycall({ a: 1, b: 2 }, 1, 2) // { a: 1, b: 2, fn: [Function: test] } 3
```
### myapply
```js
Function.prototype.myapply = function (thisArg) {
    if (typeof this !== 'function') {
        throw 'error'
    }
    thisArg = thisArg || window
    if (!(thisArg instanceof Object)) {
        thisArg = new Object(thisArg)
    }
    thisArg.fn = this
    let res = null
    if (arguments[1]) {
        res = thisArg.fn(...arguments[1])
    } else {
        res = thisArg.fn()
    }
    delete thisArg.fn
    return res
}
test.myapply({ a: 2, b: 4 }, [4, 4]) // { a: 2, b: 4, fn: [Function: test] } 8
```
### mybind
```js
Function.prototype.mybind = function (thisArg) {
    if (typeof this !== 'function') {
        throw 'error'
    }
    const that = this
    thisArg = thisArg || window
    if (!(thisArg instanceof Object)) {
        thisArg = new Object(thisArg)
    }
    const argvs = [...arguments].slice(1)
    return function F() {
        if (this instanceof F) {
            return new that(...argvs, ...arguments)
        }
        return that.apply(thisArg, argvs.concat([...arguments]))
    }
}

test.mybind('123', 4, 5)() // [String: '123'] 9
```