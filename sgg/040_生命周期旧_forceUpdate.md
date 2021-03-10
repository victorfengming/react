# 040_生命周期(旧)_forceU


> 强制更新 
>
> 你可以不对组件里面的状态做更改,也可以更新组件的渲染

`forceUpdate()`

正常更新需要走阀门,但是强制更新,他不走阀门

```javascript
// 定义组件
class Count extends React.Component {

    // 第一个调用的当然是构造器
    constructor(props) {
        console.log("count-constructor");
        super(props);
        // 初始化状态
        this.state = {count: 0}
        // 这里count 和类名 Count 没关系

    }

    //加1按钮的回调
    add = () => {
        // 获取原来的状态
        const {count} = this.state;
        // 更新状态
        this.setState({count: count + 1})
    };

    // 卸载组件按钮的回调
    death = () => {
        ReactDOM.unmountComponentAtNode(document.getElementById("test"))
    };
    // 强制组件按钮的回调
    force = () => {
        this.forceUpdate();
        // 阀门关了也能更新
    };



    // 组件将要挂载的钩子
    componentWillMount() {
        console.log("componentWillMount");
    }

    // 组件挂载完毕的钩子
    componentDidMount() {
        console.log("componentDitMount")
    }

    /*
    * 你如果不写,底层默认帮你返回一个true,如果您i要是自己写,一定要返回布尔
    * */

    // 控制组件更新的阀门
    shouldComponentUpdate() {
        console.log("shouldComponentUpdate");
        // 这里 必须要返回一个 布尔值
        return true;    // 返回true 就能正常走
        // return false;   // 返回 f 就凉了
    }

    // 组件将要更新的钩子
    componentWillUpdate() {
        console.log("componentWillUpdate");
    }
    // 组件将要更新的钩子
    componentDidUpdate() {
        console.log("componentDidUpdate");
    }

    render() {
        console.log("render")
        const {count} = this.state;
        return (
            <div>
                <h2>当前求和为:{count}</h2>
                <button onClick={this.add}>点我+1</button>
                <button onClick={this.death}>西在</button>
                <button onClick={this.force}>强制</button>
            </div>
        )
    }
}

//渲染组件
ReactDOM.render(<Count/>, document.getElementById('test'))
```
