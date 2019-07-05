# 判断变量为数组类型

Object对象和他的原型链上都有个toString的方法，第一个返回的是一个函数，第二个返回的是值类型。
Object.prototype.toString.call([])的call将数组的this的上下文转到了Object
```javascript
Object.prototype.toString.call([]) //"[object Array]"
Object.prototype.toString.call(12) //"[object Number]"
Object.prototype.toString.call(true) //"[object Boolean]"
```

# 原生js写一个new方法

```javascript
function Parent() {
    this.name = "Parent"
    this.say = function() {
        console.log(this.name)
    }
}

function newfn(fn) {
    if(typeof fn !== 'function') return 
    let son = {}
    fn.call(son)
    fn.prototype.constructor = fn
    son.__proto__ = fn.prototype
    return son
}

const son1 = newfn(Parent)
son1.say()
```