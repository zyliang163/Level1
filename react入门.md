### 前沿知识
    Hey,小伙伴们~,很高兴能一起走入这片"新江湖" React.初入江湖,面对隐藏在web开发中的各种问题,
    如'变化多端的需求,臃肿庞大的项目变得脆弱易碎和不可预测',让我们力不从心.为打破这种困局,江湖上出现了新利器React.性能高效,代码逻辑简单,一款优秀的javascript库~
    react特性:
      1.声明式设计 −告诉React我们需要什么,怎么做你自己搞定。
      2.高效 −直接操作DOM很消耗性能的,因而React虚拟DOM结构，最大限度地减少与DOM的交互。
      3.灵活 −React可以很好搭配别的库或框架。
      4.JSX − JavaScript 语法扩展,xml和Javascript结合起来的语法风格。
      5.组件 − 通过 React 构建组件，使得代码更加容易得到复用，能够很好的应用在大项目的开发中。
      6.单向响应的数据流 − 采用单向响应的数据流，从而减少了重复代码。
      7.函数式编程 -React中基本都是函数,易于代码维护和自动化测试
                    
    ![logo512.png]
    That's it,当之无愧的宝剑~
    剑气如风,我们要有一定的内功基底:
      1. 掌握html、css、javascript基础知识
      2. 熟悉Es6
      3. npm基础

    小贴士:
     1 npm是nodeJs包管理工具
     2 React生态系统极其强大,React.js web开发,ReactNative移动端开发,ReactVr虚拟现实技术开发以及服务端应用,即所谓的'Learn Once, Write Anywhere'.

    ![2.jpg]
    趣味学习：山外有山,人外有人!优秀的你一定知道,React也有自己的对手.那就是vue,vue也是个优秀的前端轻量级web框架,社区强大,上手简单.有兴趣可以移步本站vue教程,从中品鉴出各自的逻辑思维方式~
    ![3.jpg]
### 环境搭建
    我们开始动手铸造一把宝剑,首先要搭建一个环境!
    我给大家引见几种方式.
    第一种：
      在线玩转:如果你习惯在线开发,CodePen, CodeSandbox, Glitch, or Stackblitz等是个不错的选择,拥有完整开发环境,方便编辑和预览,适合新手入坑~
    ![img05.png]
    第二种:
      原始方式,<script>标签引入,使用浏览器进行编译,效率较低,工作中不会用到的~
      get技巧1:
       CDN方式:staticFile CDN 或者 官方cdn等
          例如:
          <script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
          <script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
        <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
      get技巧2:你也可以官网下载react库(react.min.js,react-dom.min.js),此外我们还要提供一个babel，用于转换jsx为es5,离线环境下就可以直接用了
      注意:babel可以用cdn提供的,
          如<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
          也本地引入babel包
        ![img06.png]
    第三种:
      Create React App:这是官方提供的快速构建基于Webpack+ES6的react单页面应用的脚手架工具,这种方式会给我们创建一个最佳的单页面应用和最舒适的学习环境!
      get技巧:
        环境要求:机器版本需Node >= 8.10 and npm >= 5.6,
        我用的Node版本是v14.2.0,npm版本是6.14.5. 如果未安装,请前往node官网自行下载安装.
        环境就绪,打开终端:
        输入create-react-app project-name,或者npx create-react-app project-name
        例如：
          create-react-app my-app
          cd my-app
          yarn start
        正常运行效果如下图,即已完成,so Easy!
      ![img07.png]
      这也是工作中我们最常用方式了,后面我们都用这种方式为主线学习~

      小贴士:
          1 yarn是npm的优化版本包管理工具,弥补npm一些缺陷产生的.
          2 npx是npm>= 5.2版本而新增的命令,更方便使用内部安装的模块

      趣味学习:
        拓展一下,思考下我们还有别的构建方式吗?聪明的你一定能想到,可以的!
        其中最主要的是我们要熟悉构建工具webpack/browserify,如何进行安装配置,
        这样可以构建更大型灵活的App了~
        当然这需要一定层次知识,如果感兴趣,可移步本站webpack教程

### jsx基本使用
    什么是jsx?jsx是用于react中的一种语法扩展,由javascript与xml结合的一种语法格式.
    例如:
      const base = <h1>Hello, world!</h1>;
      这种奇怪的语法就是jsx~
    打开我们已经创建好的项目my-app,新建一个jsx文件Base.jsx，
    第一种方法组件(无状态组件):
        import React from 'react'
        const base = <h1>Hello, world!</h1>;
        const MyBase = ()=>base;
        export {MyBase};
    第二种es6 class状态组件:
        import React from 'react'
        const base = <h1>Hello, world!</h1>;
        class MyBase extends React.Component{
            render(){
                return base;
            }
        }
        export {MyBase};

    然后在我们入口文件index.js中引入:
    import {MyBase} from './T1'
    代码如下
        ReactDOM.render(
          <React.StrictMode>
            <App/>
          </React.StrictMode>,
         document.getElementById('root')
       );
       修改组件标签<App/>为<MyBase/>
    
    小贴士:
        原生 HTML 元素名以小写字母开头，而自定义的 React 类名以大写字母开头，比如 Tes1 不能写成 tes1。除此之外还需要注意组件类只能包含一个顶层标签，否则也会报错。
    
    趣味学习:
        案例中我们用到了es6的剪头函数,模块化导入导出,class类基本知识,需要您非常熟悉~
        相关知识,可以在本站查阅es6的教程

###  jsx中使用javascript表达式
     jsx表达式写在花括号 {} 中，支持基本运算,三元表达式,方法.
     我们在上一讲代码基础上编写代码
     基本运算:
     const base = (<div>
                        <h1>{1+1}</h1>
                        <h1>{1+'1'}</h1>
                        <h1>{/* 这是一个注释 */}</h1>
                        <h1>{null||2}</h1>
                        <h1>{0&&3}</h1>
                   </div>);

     三元表达式:
      const base = <h1>{1==1?'True':'False'}</h1>
     方法:
      const sum = (a,b)=>a=b
      const base = <h1>{sum(1,1)}</h1>
     
      小贴士:表达式之间可以相互嵌套,例如:<h1>{<span>{1+1+1}</span>}</h1>

      趣味学习:
          表达式语法在动态属性,动态样式,动态类的应用
          动态属性:属性名称={表达式}
          key={index} data-id={id} 
          注意:表达式内的index/id为上下文变量
          动态样式:style={表达式}  
          例如:  
          <h1 style={{color:'red',fontSize:'25px'}}>{1+'1'}</h1>
          动态类:
            className={表达式}
          例如:
            className={!1=='1'?'active':'blur'}
###  jsx条件使用
     使用 JavaScript 操作符 if 或条件运算符来创建表示当前状态的元素。
     代码练习:
     T1.jsx文件中:
        import React from 'react'
        const base = props=>{
                  if(props.isOk){
                      return <h1>I'm fine</h1>
                  }else{
                      return <h1>I'm not fine</h1>
                  }
            }
        const MyBase = props=>base(props);
        export {MyBase};
    入口文件index.js:
          ReactDOM.render(
              <React.StrictMode>
              <MyBase isOk={true}/>
              </React.StrictMode>,
              document.getElementById('root')
          );
      ![if.gif]
    小贴士:
        案例代码isOk={true},是props语法,单向数据流,主要父子间数据传递
    趣味学习:
       我们还可以使用逻辑运算符,进行条件使用:
        例如:
          三元运算符 const base = props=>props.isOk?<h1>I'm fine</h1>:<h1>I'm not fine</h1>
          短路 const base = props=>{return props.isOk&&<h1>I'm fine</h1>}

###  jsx列表渲染
     定义一个list:
     const list = [{name:'章三',age:25},{name:'赵凯',age:18},{name:'项少侠',age:22}]
     直接渲染:
     const base = <ul>
             <li key={0}><span>章三</span><span>25</span></li>
             <li key={1}><span>赵凯</span><span>18</span></li>
             <li key={2}><span>项少侠</span><span>22</span></li>
           </ul>
     map遍历:
     const base = <ul>{list.map((item,index)=><li key={index}><span>{item.name}</span>&nbsp;<span>{item.age}</span></li>)}</ul>
     ![list.png]
      小贴士:
        案例中key属性,标记唯一元素的属性,提高diff算法效率
      趣味学习:
        map是es6提供的一个遍历数组的方法,可以修改当前值,并返回一个的新数据~
        思考下es6下还有哪些数据遍历方法和各自的用法?
