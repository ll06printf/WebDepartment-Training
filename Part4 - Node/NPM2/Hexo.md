# Hexo
## 介绍
~

## 安装
### Hexo
```bash
npm install hexo-cli -g
hexo init blog
cd blog
npm install
hexo server
```
#### 更改语言
到blog目录里的`_config.yaml`中将语言改为`zh-CN`，如下
```yml
language: zh-CN
```

### 主题
以[Icarus](https://ppoffice.github.io/hexo-theme-icarus/uncategorized/icarus%E5%BF%AB%E9%80%9F%E4%B8%8A%E6%89%8B/)主题为例
1. [下载](https://github.com/ppoffice/hexo-theme-icarus/releases)主题压缩包
2. 转到`config.yaml`将主题修改为icarus
```yml
theme: icarus
```
3. 执行清理`hexo clean`，如果出现报错，按照报错安装依赖
4. 启动服务`hexo s`

#### 切换主题
到安装Hexo的根目录，找到`config.yml`文件

## 使用
### 创建一篇新帖子/文章
终端转到blog目录，执行`hexo new [文章名称]`，如
```bash
hexo new MyFirstPost
```
然后转到`\source\_posts\MyFirstPost.md`中进行编辑。需要使用`Markdown`语言编写文章内容。

### 修改生成的文章信息
```md
---
title: MyFirstPost
date: 2022-04-20 15:49:38
tags:
---
```
|项|含义|
|--|--|
|`title`|文章标题|
|`date`|文章发布日期时间|
|`tags`|文章标签，使用`Array`的形式编写，如`["tag1","tag2"]`|

### 清除生成的内容
当整个博客的结构发生巨大变化时（如切换主题），需要清理生成的文件
```bash
hexo clean
```
### 生成博客
写完文章后需要生成整个博客，文章才能在生成文件中更新出来
```bash
hexo g
```

### 启动博客（预览)
```bash
hexo s
```
> 在命令行中使用<kbd>Ctrl</kbd>+<kbd>C</kbd>可以取消当前命令