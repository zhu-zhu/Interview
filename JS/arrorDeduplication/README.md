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