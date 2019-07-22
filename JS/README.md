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

# 数组去重

```javascript
//双循环，兼容性强
const set = (arr) => {
    var newarr = []
    for(var i = 0; i < arr.length; i++) {
        for(var j = 0; j < newarr.length; j++) {
            if(arr[i] === newarr[j]) {
                //如果newarr里的数值有相同的就跳出循环
                break;
            }
        }
        if(j === newarr.length) {
            //如果没有不同的j的值必定等于newarr的长度
            newarr.push(arr[i])
        }
    }
    return newarr
}
set([1, 1, 2, 2, 3, 5, 5])
```

# 封装一个简单的ajax

```javascript
// 接受4个参数 method, url, body, headers

function axios ({ method, url, body, headers }) {
    return new Promise((resolve, reject) => {
        let xhr = new XMLHttpRequest()
        xhr.open(method, url)

        for(let key in headers) {
            let value = headers[key]
            xhr.setRequestHeader(key, value)
        }

        xhr.onreadystatechange = function() {
            if(xhr.readyState == 4) {
                if(xhr.status == 200) {
                    resolve(xhr.responseText)
                }else if(xhr.status >= 400) {
                    reject(xhr)
                }
            }
        }

        xhr.send(body)
    })
}

const init = async () => {
    try {
        let data = await axios({
            method: 'get/post',
            url: 'url',
            headers: {
                "content-type": 'application/x-www-form-urlencoded'
            }
        })

        console.log(JSON.parse(data))
    }catch(err) {
        console.error(err)
    }
}
```