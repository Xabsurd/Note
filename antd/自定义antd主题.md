### 前置:[安装 react](/react/%E5%AE%89%E8%A3%85react.md)

### 安装 craco

```shell
npm install @craco/craco --save
```

### 安装 craco-less

```shell
npm install craco-less
```

### 添加 src/App.less 并添加以下代码

```css
@import "~antd/dist/antd.less";
```

### 在 src/App.js 中引用

```js
import "./App.less";
```

### 添加 craco.config.js 文件并添加以下代码

```js
const CracoLessPlugin = require("craco-less");
module.exports = {
  plugins: [
    {
      plugin: CracoLessPlugin,
      options: {
        lessLoaderOptions: {
          lessOptions: {
            modifyVars: { "@primary-color": "#1DA57A" },
            javascriptEnabled: true,
          },
        },
      },
    },
  ],
};
```
