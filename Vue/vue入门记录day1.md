### *.vue文件内部包含:
- `<template>html<template>`
- `<script>javascript</script>`
- `<style>css</style>`

- - -
### 命令行工具

    # 全局安装 vue-cli
    $ npm install -g vue-cli
    # 创建一个基于 "webpack" 模板的新项目
    $ vue init webpack my-project
    # 安装依赖，走你
    $ cd my-project
    $ npm install
    $ npm run dev
    
- - -
### 从Vue到页面

![从Vue到页面](img/从Vue到页面.png)

- - - 
### Vue组件的重要选项
- data
- methods
- watch

      new Vue({
        data:{
          a:1,
          b:[]
        },
        methods:{
          dosomething:function(){
            console.log(this.a);
          }
        },
        watch:{
          "a":function(val,oldVal){
                console.log(val,oldVal);
              }
        }
      })
      
- - -
### 模板指令：HTML和Vue的粘合剂

#### 数据渲染：
- v-text
- v-html
- {{}}

![数据渲染](img/数据渲染.png)

#### 控制模块显示与隐藏
- v-if:直接不渲染
- v-show：通过css的display:none来隐藏

![控制模块显示与隐藏](img/控制模块显示与隐藏.png)

#### 渲染循环列表
- v-for

![渲染循环列表](img/渲染循环列表.png)

#### 事件绑定
- v-on
- @ 是v-on的简写

![事件绑定](img/事件绑定.png)

#### 属性绑定
- v-bind
- : 是v-bind的简写

![属性绑定](img/属性绑定.png)







