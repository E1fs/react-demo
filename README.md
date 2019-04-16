# webpack-demo
1. ##### 初始化项目。
于任意空目录下，在命令行形式下，输入
```
npm init
```
初始化项目，之后一路回车直至命令结束，期间可以根据个人喜好修改对于内容，也可以在生成的`package.json`中进行修改。

2. ##### 安装必要依赖。
在命令行形式下，键入
```
yarn add webpack webpack-cli -D
```
使用`yarn`的原因是速度快。`-D`表示为`dev-dependencies`，开发时依赖包，打包后的js中不会包含开发依赖包。
如果没有yarn，输入如下指令安装：
```
npm install -g yarn
```
3. ##### 编写源码
在目录下新建一个`src`目录，里面新建一个文件，`index.js`，代码如下：
```javascript
document.getElementById('root').innerHTML = 'Hello Js'
```
再新建一个文件，`index.html`，代码如下：
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Demo</title>
    </head>
    <body>
        <div id='root'></div>
        <script src='../output/output.js'></script>
    </body>

</html>
```
4. ##### 编译运行
首先，修改package.json，增加一个scripts的键，效果如下：
```javascript
"scripts": {
    "build": "webpack src/index.js --output output/output.js"
}
```
然后，命令行键入
```
yarn build
```
使用webpack进行打包，打包结果文件为`output/output.js`，打包完成后，双击打开`src/index.html`，在浏览器看到`Hello Js`,说明成功了。