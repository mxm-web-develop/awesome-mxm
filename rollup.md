# 关于Rollup
  - 必须以.js文件为入口
  - Rollup默认只能加载ES6模块的js,默认会去找module.default
  - Rollup本身支持ES6模块化规范，因此不需要额外配置即可进行Tree Shaking

### 基本配置
export default {

  // 核心选项
  input,     // 必须
  external,
  plugins,

  // 额外选项
  onwarn,

  // 高危选项
  acorn,
  context,
  moduleContext,
  legacy
  // 必须 (如果要输出多个，可以是一个数组)
  output: { 

    // 核心选项
    file,    // 必须
    format,  // 必须
    name,
    globals,

    // 额外选项
    paths,
    banner,
    footer,
    intro,
    outro,
    sourcemap,
    sourcemapFile,
    interop,

    // 高危选项
    exports,
    amd,
    indent
    strict
  },
};


### 常用插件
- rollup-plugin-json 读取JSON数据
- rollup-plugin-commonjs 使rollup可以导入CommonJs的模块
- rollup-plugin-node-resolve 通常配合commonjs插件一起使用，用来解析引入的node_modules第三方模块
- rollup-plugin-serve 静态资源服务器：
- rollup-plugin-vue：解析vue文件
- rollup-plugin-postcss：解析、转换、提取css文件
- rollup-plugin-alias：提供modules名称的alias和reslove功能
- rollup-plugin-babel：babel转换
- rollup-plugin-eslint：eslint代码检测
- rollup-plugin-uglify：js代码压缩
- rollup-plugin-replace：类似Webpack的DefinePlugin, 可在源码中通过process.env.NODE_ENV用于构建区分环境.