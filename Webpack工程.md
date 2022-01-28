### Webpack自己的依赖安装
-  "webpack": "^5.67.0", `本体`
-  "webpack-cli": "^4.9.2", `命令行工具`
-  "webpack-dev-server": "^4.7.3" `本地开发的node服务器`
-  "webpack-merge" `用来合并webpack配置对象的工具，一般用来区分配置环境`

### Bebal转译器和相关依赖
- "@babel/core": "^7.16.12" `本体`
--- 
    bebel由于独立配置太复杂，所以官方集成了一些上手即用的配置方案，就是下方的preset方案，可以在.babelrc或者babel.config.js文件中进行加载，在webpack用使用babel-loader来进行babel的执行
---
- "@babel/preset-env": "^7.16.11" `babel预设的一些配置合集，可以把es高级版本语言降级为老浏览器可识别的版本`
- "@babel/preset-react": "^7.16.7" `babel对于react框架的一些预设配置`
- "@babel/preset-typescript": "^7.16.7" `babel对于typescript的支持预设`

### Webpack转译Module(loader)
--- 
    很多人习惯把这个配置块叫做loader模块，但是用过Ts你很容易把他联系到tsconfing.json中的module设置，而两者有着相似的功能，实际上都是在做转移工作
---
常用的loaders
- babel-loader 使webpack调用babel进行代码转译
- style-loader 将模块导出的内容作为样式并添加到 DOM 中
- css-loader 加载 CSS 文件并解析 import 的 CSS 文件，最终返回 CSS 代码
- file-loader 加载png,svg,mp3等文件类型
- postcss-loader 使用 PostCSS 加载并转换 CSS/SSS 文件
- ![更多loader可见]: https://webpack.docschina.org/awesome-webpack 'webpack5 loaders'
- 
--- 
    plugins一般是用来辅助loaders功能，或者是一些独立功能的工具
---
- mini-css-extract-plugin 该插件把CSS提取到单独的文件中。通过link标签嵌入打包出的html文件里。而style-loader是通过style标签内嵌在html文件里。
- html-webpack-plugin 该插件会生成一个HTML文件,把所有webpack打包后的文件用脚本标签嵌入进去。
- terser-webpack-plugin 压缩js
- CssMinimizerPlugin 压缩 css
- compression-webpack-plugin 用于打包Gzip文件，对应需要服务器支持Gzip
- webpack-bundle-analyzer 打包bundle大小分析
- copy-webpack-plugin 处理静态资源，复制到指定位置



### 相关参考
![webpack+react配置详细教程]: https://blog.csdn.net/qq_39261142/article/details/116176902 'webpack教程'
![webpack基础教程]:https://juejin.cn/post/6860129883398668296
![webpack官网]:https://webpack.docschina.org/concepts/