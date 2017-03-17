# Webpack
关于webpack的方面的介绍和总结在网上已经和齐全了。在这里也是将一些好的和内容齐全的东西简单的说一说。

## [webpack doc](http://webpackdoc.com/)
webpack的一个官方文档，基本关于webpack的相关东西都在里面可以找到。

下面简单的介绍一下关于webpack：

### 安装

安装webpack，需要在node环境下，如果没有安装node，你需要上网上下载并且安装。安装node的同时，npm也会被安装。webpack需要Node.js v0.6以上支持，建议使用最新的Node.js。

使用npm安装webpack:
```bash
$ npm install webpack -g
```

此时 Webpack 已经安装到了全局环境下，可以通过命令行 webpack -h 试试。

通常我们会将 Webpack 安装到项目的依赖中，这样就可以使用项目本地版本的 Webpack。

如果使用webpack开发工具，要单独安装:
```bash
$ npm install webpack-dev-server --save-dev
```

### 使用

首先创建一个静态页面 index.html 和一个 JS 入口文件 entry.js：
```html
<!-- index.html -->
<html>
<head>
  <meta charset="utf-8">
</head>
<body>
  <script src="bundle.js"></script>
</body>
</html>
```

```js
// entry.js
document.write('It works.')
```

然后编译 entry.js 并打包到 bundle.js：

```bash
$ webpack entry.js bundle.js
```
打包过程会显示日志：
```bash
Hash: e964f90ec65eb2c29bb9
Version: webpack 1.12.2
Time: 54ms
    Asset     Size  Chunks             Chunk Names
bundle.js  1.42 kB       0  [emitted]  main
   [0] ./entry.js 27 bytes {0} [built]
```
用浏览器打开 index.html 将会看到 It works. 。

接下来添加一个模块 module.js 并修改入口 entry.js：
```js
// module.js
module.exports = 'It works from module.js.'
```
```js
// entry.js
document.write('It works.')
document.write(require('./module.js')) // 添加模块
```
重新打包 webpack entry.js bundle.js 后刷新页面看到变化 It works.It works from module.js.
```bash
Hash: 279c7601d5d08396e751
Version: webpack 1.12.2
Time: 63ms
    Asset     Size  Chunks             Chunk Names
bundle.js  1.57 kB       0  [emitted]  main
   [0] ./entry.js 66 bytes {0} [built]
   [1] ./module.js 43 bytes {0} [built]
```

Webpack 会分析入口文件，解析包含依赖关系的各个文件。这些文件（模块）都打包到 bundle.js 。Webpack 会给每个模块分配一个唯一的 id 并通过这个 id 索引和访问模块。在页面启动时，会先执行 entry.js 中的代码，其它模块会在运行 require 的时候再执行。

### 更多内容
更多内容，详见[这里](http://webpackdoc.com/)。

## [webpack loader lists](http://webpack.github.io/docs/list-of-loaders.html)

loader是webpack的核心之一，而到底都有什么loader可以使用，这对于开发者来说是一个很重要的事情。webpack由此为开发者列出了一个`loader list`。在这里你可以找到所有可用的loader，并且官网也为这些loader做了分类，供开发者进行选择搭配。虽然不是中文，但是英文都是很容易明白的。详情[这里](http://webpack.github.io/docs/list-of-loaders.html)

## webpack&xxxxx 系列
在webpack之前也有很多构建工具，比如gulp、grunt等，而在功能上他们有重叠的地方，也有各自的特色。有些开发者通过合理的组合他们来更好的完成项目。下面是我在网上搜集的一些其他构建工具和webpack组合使用的文章，如果你也有更好或者这里没有的方案，请issue我，thx。

### [webpack&gulp集成简介](http://www.jianshu.com/p/8c9c8f5649c9)

### [webpack入门指南](http://www.w2bc.com/Article/50764)

最后部分讲了一点点关于与gulp和grunt组合的内容。

## 其他的入门教程
这里还有一些其他的入门教程，感觉也很不错。

### [Webpack 入门指迷](https://segmentfault.com/a/1190000002551952)