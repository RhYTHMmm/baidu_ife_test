parcel-极简WEB应用打包工具
===========
## 1. 安装
- **全局安装parcel**
```
npm install -g parcel-bundler
```
- **添加项目初始化package.json**
```
mkdir 02 && cd 02 && npm init -y
```
- **添加index.html和index.js**
```
// index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>parcel</title>
</head>
<body>
    <div>
        hello world!! parcel
    </div>
<script src="./index.js"></script>
</body>
</html>

```
```
// index.js
console.log('hello world');
```

- **接下来输入一个命令就运行起来啦**
```
percel index.html
```
> 如果想写在配置文件里
```
// package.json
{
  "name": "02",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "dev": "parcel index.html"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```
> 接下来输入 npm run dev 就可以了！

## 2.JavaScript
 Parcel 同时支持 CommonJS 和 ES6 两种模块语法来导入文件
 ```
 // 使用 CommonJS 语法导入模块
const dep = require('./path/to/dep');

// 使用 ES6 语法导入模块
import dep from './path/to/dep';

// 引入 CSS 文件
import './test.css';

// 引入包含 CSS 模块的 CSS 文件
import classNames from './test.css';

// 以 URL 的形式引入图片
import imageURL from './test.png';
 ```
 ## 3.SASS
你需要安装node-sass
```
npm install node-sass
```
安装了 node-sass，你就可以在 JavaScript 文件中引入 SCSS 文件。
 ```
 import './index.scss'
 ```
 ## 4.生产环境构建
 输入npm run build 会构建一次，构建后的代码可指定文件位置，例如build文件夹下。
 ```
 {
  "name": "02",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "dev": "parcel index.html",
    "build": "parcel build index.js -d build/"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "node-sass": "^4.9.0"
  }
}
 ```
 ## 5. babel
```
cnpm i -D babel-preset-env 
```
```
{
  "presets": [
      "env"
  ]
}
```
 
 ## 6. SAN 
 [San gitgub](https://github.com/baidu/san/)
 ```
 <!DOCTYPE html>
<html>

<head>
    <title>Quick Start</title>
    <script src="https://unpkg.com/san@latest"></script>
</head>

<body>
    <script>
        const MyApp = san.defineComponent({
            template: `
                <div>
                    <input type="text" value="{=name=}">
                    <p>Hello {{name}}!</p>
                </div>
            `
        });

        let myApp = new MyApp({
            data: {
                name: 'San'
            }
        });
        myApp.attach(document.body);
    </script>
</body>

</html>
 ```