# 013_初始化state


## 案例

今天天气

```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>06_组件实例三大属性1_state.html.html.html</title>

</head>
<body>
<!--准备好一个"容器""-->
<div id="test"></div>
<!--引入 react 核心库-->
<script type="text/javascript" src="../js/react.development.js"></script>
<!--引入 react-dom ,用于支持react 操作Dom-->
<script type="text/javascript" src="../js/react-dom.development.js"></script>
<!--引入babel,用于将jsx转为js-->
<script type="text/javascript" src="../js/babel.min.js"></script>
<!--babel,表示是jsx-->
<script type="text/babel">
    // 1. 创建组件
    class Weather extends React.Component{
        constructor(props) {
            super(props);
            // 初始化状态
            this.state = {isHot:false}
        }
        render() {
            console.log(this);
            // 读取状态
            const {isHot} = this.state.isHot
            return <h1>今天天气很{isHot ? '炎热' : '凉爽'}</h1>
        }
    }

    // 2.  渲染 组件到页面
    ReactDOM.render(<Weather/>, document.getElementById('test'));

    // idea 运行 React ,alt+F2
</script>


</body>
</html>

```