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
