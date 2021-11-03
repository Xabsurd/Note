### 前置:[[安装antd|安装antd]]
### 安装 craco
```shell
npm install @craco/craco --save
```
### 安装 craco-less
```shell
npm install craco-less
```
### 添加src/App.less并添加以下代码
```css
 @import '~antd/dist/antd.less';
```
### 在src/App.js中引用
```js
import './App.less';
```
### 添加craco.config.js文件并添加以下代码

```js
const CracoLessPlugin = require('craco-less');
module.exports = {
	 plugins: [
		 {
			 plugin: CracoLessPlugin,
			 options: {
				 lessLoaderOptions: {
					 lessOptions: {
						 modifyVars: { '@primary-color': '#1DA57A' },
						 javascriptEnabled: true,
					 },
				 },
			 },
		 },
	 ],
};