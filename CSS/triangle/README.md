# 使用css绘画一个三角形

### 原理分析

绘制三角形使用的是css3中的transparent属性，意思是透明。就像设置一个div背景为黑色background-color: #000，把它更改为透明色可以写为background-color:transparent;。所以绘制一个三角形基本就是将一个矩形的左右两边设置为透明色，只留下bottom设置颜色

### 1，上三角形

```html
<style>
.div1 {
    width: 0;
    height: 0;
    border-left: 50px solid transparent;
    border-right: 50px solid transparent;
    border-bottom: 100px solid #000;
}
</style>

<body>
    <div class="div1"></div>
</body>
```

### 2，下三角形

```html
<style>
.div2 {
    width: 0;
    height: 0;
    border-left: 50px solid transparent;
    border-right: 50px solid transparent;
    border-top: 100px solid #000;
}
</style>

<body>
    <div class="div2"></div>
</body>
```