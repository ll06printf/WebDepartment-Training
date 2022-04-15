# NPM 1
- NPM的使用
- NPX
- 引入TailwindCSS

## 准备软件
### 下载Node.js
[下载Node.js](https://nodejs.org/en/)
点击左边的**LTS版本**，下载并安装，一路Next即可。
### 验证安装
1. 打开命令行
   - 电脑的搜索栏中输入`cmd`，打开“命令提示符”
   - 或者搜索栏中输入`powershell`，打开“Windows Powershell”
2. 输入`node -v`，如果显示版本，则安装成功。如果没有成功，可以重启后再试。

## NPM
- Node.js & NPM

### NPM基本操作
<!-- follow -->
- 创建新项目：初始化项目
  - 介绍`json`文件: JavaScript Object Notation
    - 对象
    - 数组
  - `package.json`文件
    - `script`：存放的是项目的命令，可以通过`npm run [命令名称]`来运行预先在这里定义的命令。
- 包的安装
  - `dependencies`
  - `devdependencies`
- 包的卸载
- **如何恢复项目的包(dependencies)**：如果发现项目中没有`node_modules`这个文件夹（无论是出于传输项目时减小项目文件夹体积，还是其他的原因），可以使用`npm install`这个指令，从项目中的`package.json`中还原所有包。*这里的`test/`文件夹中的项目就删除了`node_modules/`文件夹，使用时可以使用上述的指令进行恢复。*

## TailwindCSS
### 介绍
- CSS框架
- 特点：只需编写少量CSS代码即可实现一个完整的HTML页面；CSS由TailwindCSS根据源文件自动生成，文件小；具有各种现代特性（如断点，深色模式等）

### 通过NPM安装并配置Tailwind
👉 [源文件](./resources/index.html)

👉 [成品](./tailwind_test/src/index.html)

安装TailwindCSS
```bash
npm install -D tailwindcss
```

初始化Tailwind，创建配置文件
```
npx tailwindcss init
```

更改配置文件（详见 [生成CSS](https://www.tailwindcss.cn/docs/installation#css)， 与PostCSS无关）
```js
// tailwind.config.js
module.exports = {
  content: ["/src/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

创建Tailwind依赖的CSS，也方便以后使用
```css
/* style.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

将Tailwind加入到npm项目的启动命令中（也可以直接执行）
```bash
npx tailwindcss -i ./src/style.css -o ./src/tailwind.css --watch
```

在html文件中引用
```html
<link href="/src/tailwind.css" rel="stylesheet">
```

### Tailwind的使用
新建项目的时候首先记得在HTML里面引用TailwindCSS
TailwindCSS [中文文档](https://www.tailwindcss.cn/docs)

TailwindCSS [在线运行环境](https://play.tailwindcss.com/)

#### 示例属性
背景颜色 https://www.tailwindcss.cn/docs/background-color
```html
<div class="bg-blue-500"></div>
```

宽度（高度同理）https://www.tailwindcss.cn/docs/width
```html
<div class="w-64 h-64"></div>
```

所有属性的文档详见TailwindCSS文档

## 练习
所有练习示例源文件详见`/test/src`
- `/test/src`
  - `/test/src/index.html`：[测试页面](./test/src/index.html)
  - `/test/src/card.html`：卡片
  - `/test/src/responsive.html`：响应式实验

### 练习1：制作一个消息卡片
转到[源文件](./test/src/card.html)

![练习1](./Practice_1.png)

### 练习2：响应式实验
转到[源文件](./test/src/responsive.html)