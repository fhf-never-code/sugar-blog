# 如何正确判断 this？箭头函数的 this 是什么？
```js
function foo() {
  console.log(this.a)
}
var a = 1
foo() // 1

const obj = {
  a: 2,
  foo: foo
}
obj.foo() // 2

const c = new foo() // undefined
c()
```
1. 对于普通函数来说,this->window
2. 全局作用域下,this -> window
3. 对于对象来说,谁调用函数谁就是this
4. new 的方式,this永远被绑定在实例上
5. 箭头函数本身是没有this,继承外层上下文绑定的this(包裹箭头函数的第一个普通函数的this)
6. 箭头函数使用bind,call,this无效
7. bind/call/apply 这些改变上下文的 API 了，对于这些函数来说，this 取决于第一个参数，如果第一个参数为空，那么就是 window
8. 不管我们给函数 bind 几次，fn 中的 this 永远由第一次 bind 决定

**示例**
```js
var p1 = 1
function fn1(){
    console.log(this.p1)
}
fn1() // 1

let obj2 = {
    p2:2,
    fn2(){
        console.log(this.p2)
    }
}
obj2.fn2() // 2

var p3 = 1
function fn3() {
    this.p3 = 3
    console.log(this.p3)
}
let fn31 = new fn3() // 3

var p4 = 4
const fn4 = ()=>{
    console.log(this.p4)
}
fn4() // 4

function fn5() {
    this.p5 = 5
    return function () {
        this.p5 = 55
        return function () {
            this.p5 = 555
            return () => {
                console.log(this.p5)
            }
        }
    }
}

fn5()()()() // 555

const fn6 = ()=>{
    console.log(this.p6)
}
fn6.bind({p6:6})() // undefined
fn6.call({p6:6}) // undefined

var p7 = 7
function fn7(){
    console.log(this.p7)
}
fn7.bind({p7:77})() // 77
fn7.bind()() // 7

function fn8(){
    console.log(this.p8)
}
fn8 = fn8.bind({p8:8}).bind({p8:88}).bind({p8:888})
fn8() // 8
```

![图片](http://img.cdn.sugarat.top/mdImg/MTU4MzgyNjg3NzI4Mw==583826877283)



**一个笔试题**
```js
let obj2 = {
    name: 'obj2'
}

const obj = {
    name: 'obj',
    say1() {
        console.log(this.name)
    },
    obj1: {
        name: 'obj1',
        say2() {
            console.log(this.name);
        }
    },
    say3() {
        const fn = () => {
            console.log(this.name);
        }
        fn()
    },
    say4() {
        const fn = function () {
            console.log(this.name);
        }
        fn()
    },
    say5() {
        const fn = () => {
            console.log(this.name);
        }
        fn.call(obj2)
    },
    say6() {
        const fn = function () {
            console.log(this.name);
        }
        fn.call(obj2)
    }
}

let a = obj.say1
let b = obj.obj1.say2
a() 
b()
obj.say1()
obj.obj1.say2()
obj.say3()
obj.say4()
obj.say5()
obj.say6()
```

<my-details>

```js
undefined
undefined
obj
obj1
obj
undefined
obj
obj2
```
</my-details>

<tongji/>