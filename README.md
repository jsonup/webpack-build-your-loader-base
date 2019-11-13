<!--
 * @Author: starkwang
 * @Contact me: https://shudong.wang/about
 * @Date: 2019-11-13 15:47:31
 * @LastEditors: starkwang
 * @LastEditTime: 2019-11-13 15:51:35
 * @Description: file content
 -->
<h1 align="center">构建自己的webpack loader 初体验👋</h1>

<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000" />
  <a href="https://shudong.wang" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
  <a href="#" target="_blank">
    <img alt="License: ISC" src="https://img.shields.io/badge/License-ISC-yellow.svg" />
  </a>
  <a href="https://twitter.com/wsd312" target="_blank">
    <img alt="Twitter: wsd312" src="https://img.shields.io/twitter/follow/wsd312.svg?style=social" />
  </a>
</p>

### 🏠 [BLOG](https://shudong.wang)

### 🏠 [项目地址](https://github.com/webpack-guide/webpack-build-your-loader-base)

## Install

```sh
yarn
```

## Author

👤 **starkwang**

* Website: https://shudong.wang
* Twitter: [@wsd312](https://twitter.com/wsd312)
* Github: [@wsdo](https://github.com/wsdo)
* segmentfault: [@shudong](https://segmentfault.com/blog/shudong)

## Show your support

Give a ⭐️ if this project helped you!

如果这个项目对您有帮助，请给一个️star！

---

## 项目介绍
构建自己的webpack loader

#### 编写loader
> ./loader/starkLoader.js
```js
module.exports = function(source) {
  // console.log('source',source);
	return source.replace('starkwang', 'shudong');
}

```

> 在webpack.config.js里面添加

```js
	resolveLoader: {
		modules: ['node_modules', './loaders']
	},
	module: {
		rules: [{
			test: /\.js/,
			use: [
				{
					loader: 'starkLoader',
				},
			]
		}]
	},
```

#### 开始
```
yarn
```

```
npm run build
```

> dist/main.js 里面的 starkwang 变成了 shudong

![2019-11-13-16-50-49](http://s.shudong.wang/2019-11-13-16-50-49.png)

> 变成 

![2019-11-13-16-50-34](http://s.shudong.wang/2019-11-13-16-50-34.png)
