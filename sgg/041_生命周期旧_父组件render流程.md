# 041_生命周期(旧)_父组件render流程

> componentWillReceiveProps被调用的时机


* 有人建议他改成 componentWillReceiveNewProps
* 以为 组件将要接收新的 props ,一开始第一次传的不算
* 但是我这边我还是调用了





```javascript
    class A extends React.Component {
        // 存储骑车的名字
        // 初始化状态
        state = {carName: 'BMW'}
        changeCar = () => {
            // 更新车你的信息
            this.setState({carName: "奥迪"})
        };

        render() {
            return (
                <div>
                    <div>我是A组件</div>
                    <button onClick={this.changeCar}>换车</button>
                    {/*然后B组件来展示这个骑车的信息*/}
                    <B carName={this.state.carName}/>
                </div>
            )
        }
    }

    class B extends React.Component {
        // 这个有瑕疵
        /*
        * 有人建议他改成 componentWillReceiveNewProps
        * 以为 组件将要接收新的 props ,一开始第一次传的不算
        * 但是我这边我还是调用了
        * */

        // 所以应该叫做: 组件将要接收新的props的钩子
        componentWillReceiveProps(props) {
            console.log("componentWillReceiveProps", props);
        }


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
             console.log("render");
            return (
                <div>
                    我是B组件,接收到的车是:{this.props.carName}
                </div>
            )
        }
    }

    // A是父组件 B是子组件
    //渲染组件
    ReactDOM.render(<A/>, document.getElementById('test'))
```

![1615377514569](041_%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E6%97%A7_%E7%88%B6%E7%BB%84%E4%BB%B6render%E6%B5%81%E7%A8%8B/1615377514569.png)

