# 02022_对props进行限制

```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>1_props基本使用.html.html.html.html</title>
    <!--引入 react 核心库-->
    <script type="text/javascript" src="../js/react.development.js"></script>
    <!--引入 prop-types 核心库-->
    <script type="text/javascript" src="../js/prop-types.js"></script>
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
<div id="test3"></div>

<!--
react 中 他重新封装了这些事件, 他
-->
<button></button>
<!--babel,表示是jsx-->
<script type="text/babel">
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
                    <li>年龄: {age + 1}</li>
                </ul>
            )
        }
    }
    // Person.属性规则 = {
    //     name: '必传, 字符串'
    // }
    // 这个属性的名字不能改
    // 创建的时候 找这个属性,要是有就帮你限制
    // TODO 对标签属性进行类型,必要性的限制
    Person.prototypes = {
        // PropTypes 大写的是一个React 的属性
        // 注意这个string 开头是小写的
        // 在React 15.xxx 有
        // 在React 16 之后就被弃用了
        // name:React.PropTypes.string
        // React 有点臃肿 这么整
        name: PropTypes.string.isRequired,    // 字符串 必须传
        sex: PropTypes.string,// 限制rex没说必传 
        age: PropTypes.number,// 限制 age为数值
        speak:PropTypes.func,// 限制speak为函数
    }
    // 指定默认标签属性值
    Person.defaultProps = {
        sex:'男', // sex默认值为难
        age:18  // 年龄 默认为18
    }
    ReactDOM.render(<Person name="jerry" age={19} sex="男"/>, document.getElementById('test1'))
    ReactDOM.render(<Person name="tom" age={17} sex="女"/>, document.getElementById('test2'))
    ReactDOM.render(<Person {...p}/>, document.getElementById('test3'))

    const p = {name: 'nancy', age: 18, sex: '女'}
    // 渲染组件到页面
    ReactDOM.render(<Person {...p}/>, document.getElementById('test3'))
</script>


</body>
</html>

```



```javascript
ar ReactPropTypes = {
                    array: shim,
                    bool: shim,
                    func: shim,
                    number: shim,
                    object: shim,
                    string: shim,
                    symbol: shim,

                    any: shim,
                    arrayOf: getShim,
                    element: shim,
                    elementType: shim,
                    instanceOf: getShim,
                    node: shim,
                    objectOf: getShim,
                    oneOf: getShim,
                    oneOfType: getShim,
                    shape: getShim,
                    exact: getShim,

                    checkPropTypes: emptyFunctionWithReset,
                    resetWarningCache: emptyFunction
                };
```

>function 应该用func