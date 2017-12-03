# reactnews
this is a item about react.
1,在命令行输入cd reactnews
2,npm init 
3,安装相关依赖npm install --save react react-dom babelify babel-preset-react
4，要用es6安装依赖 npm install babel-preset-es2015 –save
5, 新建文件index.html，
<div id='example'>123</div>
<script src='./src/js/index.js'></script>
创建src文件夹，并且在其中创建一个js文件夹，新建index.js
var React = require('react');
var ReactDOM = require('react-dom');

ReactDOM.render(
    <h1>hello world</h1>,
    document.getElementById('example')
);
6,webpack打包。新建文件webpack.config.js
var webpack =require('webpack');
var path = require('path');

module.exports={
    context:__dirname + '/src',
    entry:"./js/index.js",
    module:{
        loaders:[{
            test:/\.js?$/,
            exclude:/(node_modules)/,
            loader:'babel-loader',
            query:{
                presets:['react','es2015']
            }
        }]
    },
    output:{
        path:__dirname + "/src/",
        filename:"bundle.js"
    }
};
7, 全局安装npm install –g webpack 
Npm install –g webpack-dev-server 
再目录文件安装npm install webpack --save
Npm install webpack-dev-server –save

8,运行webpack,自动生成bundle.js相应的index.html
<div id='example'>123</div>
<script src='./src/ bundle.js'></script>

9,改变相应页面内容数据，就要重新webpack一次，生成新的bundle.js,才能渲染到页面上。所以在命令行输入webpack –watch自动更新bundle.js。再重新打开一个命令行窗口，输入webpack-dev-server;  打开网址http://localhost:8080/webpack-dev-server/；这样保存文件，页面就会自动刷新。
10,重启webpack-dev-server --contentbase src --inline --hot,打开网址http://localhost:8080/，可以自动刷新；


项目内容：
1：引入ant.design框架设计样式和布局；
2：构建内容分为移动端和pc端，当为移动端时显示移动端界面，当为pc端显示pc端界面，导航用的是Menu控件；
3：网络请求使用fetch模块；
