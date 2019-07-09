# 在未知父级高度的情况想让子级左右垂直居中(子级一个)

### 1，使用transform来定位

```html

<!-- html -->
<body>
    <div class="fdiv">
        <dir class="cdiv"></dir>
    </div>
</body>

<!-- css -->
<style>
* {
    padding: 0;
    margin: 0;
}
.fdiv {
    width: 100vw;
    height: 100vh;
    position: relative;
}
.cdiv {
    width: 100px;
    height: 100px;
    background: #ccc;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
}
</style>
```

### 2，使用flex布局，相对简单点

```html

<!-- html -->
<body>
    <div class="fdiv">
        <dir class="cdiv"></dir>
    </div>
</body>

<!-- css -->
<style>
* {
    padding: 0;
    margin: 0;
}
.fdiv {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
.cdiv {
    width: 100px;
    height: 100px;
    background: #ccc;
}
</style>
```

# 在未知父级高度的情况想让子级左右垂直居中(子级一个)

### 1，使用transform来定位

```html

<!-- html -->
<body>
    <div class="fdiv">
        <dir class="cdiv"></dir>
    </div>
</body>

<!-- css -->
<style>
* {
    padding: 0;
    margin: 0;
}
.fdiv {
    width: 100vw;
    height: 100vh;
    position: relative;
}
.cdiv {
    width: 100px;
    height: 100px;
    background: #ccc;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
}
</style>
```

### 2，使用flex布局，相对简单点

```html

<!-- html -->
<body>
    <div class="fdiv">
        <dir class="cdiv"></dir>
    </div>
</body>

<!-- css -->
<style>
* {
    padding: 0;
    margin: 0;
}
.fdiv {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
.cdiv {
    width: 100px;
    height: 100px;
    background: #ccc;
}
</style>
```