---
title: hexo指令
date: 2017-08-03 08:29:02
tags: hexo
---
# 安装和使用 Hexo
## 安装 Hexo
所有必备的应用程序安装完成后，即可使用 npm 安装 Hexo。

npm install -g hexo-cli
## 安装git插件
> 1. cd 定位到项目文件夹。
> 2. 执行命令`npm install hexo-deployer-git --save`

***
# 指令
## init
新建一个网站。如果没有设置 folder ，Hexo 默认在目前的文件夹建立网站。

    hexo init [folder]
## new
新建一篇文章。如果没有设置 layout 的话，默认使用 _config.yml 中的 default_layout 参数代替。如果标题包含空格的话，请使用引号括起来。

	$ hexo new [layout] <title>
## generate
生成静态文件。

| 选项 | 描述 |
| :- | :- |
| `-d, --deploy` | 文件生成后立即部署网站 |
| `-w, --watch` | 监视文件变动 |
<br/>

	$ hexo generate
该命令可以简写为：

	$ hexo g
## publish
发表草稿。

	$ hexo publish [layout] <filename>
## server
启动服务器。默认情况下，访问网址为： http://localhost:4000/。

|选项|描述|
|:-|:-|
|`-p, --port`|重设端口|
|`-s, --static`|只使用静态文件|
|`-l, --log`|启动日记记录，使用覆盖记录格式|
<br/>

	$ hexo server
## deploy
部署网站。

|参数|描述|
|:-|:-|
|`-g, --generate`|部署之前预先生成静态文件|
<br/>

	$ hexo deploy
该命令可以简写为：

$ hexo d
## clean
	hexo clean
清除缓存文件 (*db.json*) 和已生成的静态文件 (*public*)。在某些情况（尤其是更换主题后），如果发现您对站点的更改无论如何也不生效，您可能需要运行该命令。
***
# 选项
## 安全模式
	hexo --safe
在安全模式下，不会载入插件和脚本。当您在安装新插件遭遇问题时，可以尝试以安全模式重新执行。
## 调试模式
	hexo --debug
在终端中显示调试信息并记录到 debug.log。当您碰到问题时，可以尝试用调试模式重新执行一次，并 提交调试信息到 GitHub。
## 简洁模式
	hexo --silent
隐藏终端信息。

       