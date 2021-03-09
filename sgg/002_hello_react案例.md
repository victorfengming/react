# 002_hello_react案例.md


```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
<!--准备好一个"容器""-->
<div id="test"></div>
<!--引入 react 核心库-->
<script type="text/javascript" src="js/react.development.js"></script>
<!--引入 react-dom ,用于支持react 操作Dom-->
<script type="text/javascript" src="js/react-dom.development.js"></script>
<!--引入babel,用于将jsx转为js-->
<script type="text/javascript" src="js/babel.min.js"></script>
<!--babel,表示是jsx-->
<script type="text/babel">
    /*
    * 此处一定要写babel
    * */
    // 1. 创建虚拟Dom
    const VDOM = <h1>Hello,React</h1>;   // 此处一定不要写引号,因为不是字符串
    // 这里不用加单引号,因为他是jsx
    // jS 和JSx 差不多
    // 2. 渲染虚拟DOM到页面
    // ReactDOM.render(虚拟Dom,容器)
    ReactDOM.render(VDOM, document.getElementById('test')); // 这个地方你不服
</script>


</body>
</html>

```


>ReactDOM.render(VDOM, document.getElementById('test'));
>

这个只能写一行

