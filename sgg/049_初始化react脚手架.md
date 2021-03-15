# 049_初始化react脚手架



![img](img/pic34.nipic.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg)



 ## 使用create-react-app创建react应用
### react脚手架
1. xxx脚手架: 用来帮助程序员快速创建一个基于xxx库的模板项目
    1. 包含了所有需要的配置（语法检查、jsx编译、devServer…）
    2. 下载好了所有相关的依赖
    3. 可以直接运行一个简单效果
2. react提供了一个用于创建react项目的脚手架库: create-react-app
3. 项目的整体技术架构为:  `react` + `webpack` + `es6` + `eslint`
4. 使用脚手架开发的项目的特点: **模块化, 组件化, 工程化**

> 前端里面的3大框架

Angular,React,Vue 都有自己的脚手架

我们创建脚手架的全称应该叫"创建一个基于React脚手架的模板项目"

> 工程化: 你通过这种构建工具批量的完成

###  创建项目并启动
第一步，全局安装：``npm i -g create-react-app`

第二步，切换到想创项目的目录，使用命令：`create-react-app hello-react`

第三步，进入项目文件夹：`cd hello-react`

第四步，启动项目：`npm start`



---



React 创建好项目后

```cmd
Success! Created react_staging at D:\IdeaProjects\react\code\react_staging
Inside that directory, you can run several commands:

  npm start
    Starts the development server.

  npm run build
    Bundles the app into static files for production.

  npm test
    Starts the test runner.

  npm run eject
    Removes this tool and copies build dependencies, configuration files
    and scripts into the app directory. If you do this, you can’t go back!

We suggest that you begin by typing:

  cd react_staging
  npm start

Happy hacking!

D:\IdeaProjects\react\code>
```

> 提示你已经安装成功,是不是要打开文件夹并启动他