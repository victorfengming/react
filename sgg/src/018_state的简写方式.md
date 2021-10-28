# 018_state的简写方式


自己写的方法,基杰上是健为事件触发后要执行的方法来使用的o


90%以上都是这样


## 来来来回顾一下
>


```JavaScript
class Car{
        constructor(name,price) {
            this.name = name;
            this.price = price;
            this.wheel = 4;
        }

        // 类 中可以直接写复制语句
        a = 1;
        // 上述dia代码的含义是: 给Car的实例对象添加一个属性,名为a,值为1
    }

    const c1 = new Car("奔驰c63",199);
    const c2 = new Car("奔驰c63",299);
    console.log(c1);
    console.log(c2);
```

>就是说,我这个类里面可以写成员属性

## 然后这么写
>



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
<!--
react 中 他重新封装了这些事件, 他
-->
<button></button>
<!--babel,表示是jsx-->
<script type="text/babel">
    // 1. 创建组件
    class Weather extends React.Component {

        // 初始化状态
        // 成员属性.,放到外面
        state =  {isHot: false, wind: '威风'}

        render() {
            const {isHot,wind} = this.state
            return <h1 onClick={this.demo}>今天天气很{isHot ? '炎热' : '凉爽'},{wind}</h1>

        }

        // 自定义方法 -- 要用赋值 语句的形式+ 箭头函数
        // 这样就赋值到自身了
        // 剪头函数的this用的外层的this
        changeWeather = ()=>{
            const isHot = this.state.isHot
            this.setState({isHot: !isHot})      // 这是错误的写法
        }
    }

    // 2.  渲染 组件到页面
    ReactDOM.render(<Weather/>, document.getElementById('test'));

</script>


</body>
</html>

```
