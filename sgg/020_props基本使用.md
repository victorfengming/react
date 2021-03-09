# 0020_props基本使用


## 案例

```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>06_组件实例三大属性1_state.html.html.html</title>
    <!--引入 react 核心库-->

    <script type="text/javascript" src="../js/react.development.js"></script>
    <!--引入 react-dom ,用于支持react 操作Dom-->
    <script type="text/javascript" src="../js/react-dom.development.js"></script>
    <!--引入babel,用于将jsx转为js-->
    <script type="text/javascript" src="../js/babel.min.js"></script>
</head>
<body>
<!--准备好一个"容器""-->
<div id="test"></div>
<div id="test1"></div>
<div id="test2"></div>
<!--
react 中 他重新封装了这些事件, 他
-->
<button></button>
<!--babel,表示是jsx-->
<script type="text/babel">
    // 创建组件
    class Person extends React.Compent {
        state = {name:'tom',age:18, sex: 女}
        render() {
            // 从组建外部 来给他信息,也就是不能用state 来给他数据信息
            return (
                <ul>
                    <li>姓名: Tom</li>
                    <li>姓别: 女</li>
                    <li>年龄: 18</li>
                </ul>
            )
        }
    }

    // 渲染组件到页面
    ReactDOM.render()
</script>


</body>
</html>

```

![1615295711887](020_props%E5%9F%BA%E6%9C%AC%E4%BD%BF%E7%94%A8/1615295711887.png)


然后现在就不方便吧从test2的数据传递到test里面去了

>props应运而生
>

 
 
```javascript
    // 创建组件
    class Person extends React.Component {
        state = {name: 'tom', age: "18", sex: "女"}

        render() {
            const {name, age, sex} = this.props

            // 从组建外部 来给他信息,也就是不能用state 来给他数据信息
            return (
                <ul>
                    <li>姓名: {name}</li>
                    <li>姓别: {sex}</li>
                    <li>年龄: {age}</li>
                </ul>
            )
        }
    }

    // 渲染组件到页面
    ReactDOM.render(<Person name="tom" age="18" sex="女"/>, document.getElementById('test'))
    ReactDOM.render(<Person name="jack" age="17" sex="男"/>, document.getElementById('test2'))
    ReactDOM.render(<Person name="victor" age="19" sex="男"/>, document.getElementById('test3'))

```
 
基本写法


 
>语法糖
>

```javascript
const p = {name:'nancy',age:18, sex: '女'}
    // 渲染组件到页面
    ReactDOM.render(<Person {...p}/>, document.getElementById('test3'))
```
 
>这个前提是你要key和后端获取的key一样
>


 
 
 
 
