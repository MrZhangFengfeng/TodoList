####  npm init

使用这条命令来开启一个新工程。就是产生package.json
这会直接产生一个package.json,不会逐项询问

        npm init -y 
 
强制产生一个package.json

        npm init -f

- - -
#### 在引入的js文件内定义一个

    var a = 1;
    console.log(window.a) //1
  
这会污染环境。应该用let来定义  或者放在局部作用于内。

- - -
#### css中  max-width 和 width

如果是直接width的话  div会固定宽度，不会随浏览器宽度变化而变化。
但是如果给max-width的话会随着浏览器窗口宽度自动进行调整。自适应。

- - -
调用浏览器自带datepicker

    <input type="date">
 
- - -
