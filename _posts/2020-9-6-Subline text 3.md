---
layout: post
title: Sublime text 3安装和常用插件安装
date: 2020-9-6 
tags: Subline text3  
---

### Sublime text 3安装和配置
一：Sublime3下载

1. [下载地址](http://www.sublimetext.com/3){:target="_blank"}：<http://www.sublimetext.com/3>{:target="_blank"}
2. 我选择下载Win64位安装程序
![](/images/posts/Subline text3/xiazai_2020-09-06_23-39-14.png)

二：安装

1. 按步骤傻瓜式安装，一直点下一步即可。
2. 安装**Package Control**（Package Control是一个管理Sublime Text插件的插件，通过Package Control我们可以直接使用Sublime Text控制台来安装其他插件，快捷简单。）

	1. `Ctrl+Shift+P`打开命令面板;
	2. 输入`Install Package Control`静等一会儿，菜单栏点击Perferences如果出现Package Settings和Package Control说明安装成功了，结果如下图所示。（如果没出现，重启一下sublime）

	![](/images/posts/Subline text3/package-control_2020-09-07_02-17-34.png)

### Sublime text 3插件的安装和配置
1. 组合键`Ctrl+Shift+P` 调出命令面板
2. 输入`install`回车
3. 在搜索框中输入要安装的包名（一个一个，不能同时安多个）
4. 静待几秒即可安装成功

### 前端常用插件介绍

#### 1. Emmet
(一种快速编写html/css的方法)
[插件介绍以及演示](https://packagecontrol.io/packages/Emmet){:target="_blank"}
***
#### 2. AutoFileName
(自动完成文件名的输入，如图片选取选择路径时)
[插件介绍以及演示](https://packagecontrol.io/packages/AutoFileName){:target="_blank"}
***
#### 3. JavaScript Completions
(支持javascript原生语法提示，妈妈再也不用担心我输入document.getElementById(id)。)
[插件介绍以及演示](https://packagecontrol.io/packages/JavaScript%20Completions){:target="_blank"}
***
#### 4. HTML-CSS-JS Prettify
(THML、CSS、JS代码格式化，压缩过后的代码可以通过该工具复原。)
[插件介绍以及演示](https://packagecontrol.io/packages/HTML-CSS-JS%20Prettify){:target="_blank"}
安装完成后，需要设置node路径：`Ctrl+Shift+P`后输入`htmlprettify`

![](/images/posts/Subline text3/nodelujing_2020-09-07_03-47-35.png)

格式化代码的快捷健为`Ctrl+Shift+H`
***
#### 5. A File Icon
(显示侧边栏图标)

### 6. Sublime Text3 的 Markdown 实时预览

|  :----:  | :----:  |
| MarkdownPreview  | 支持在浏览器中预览markdown文件 |
| LiveReload  | 是一个可实时刷新的插件 |

先安装两个插件，安装完成后

1. 组合键 `Ctrl+Shift+P` 调出命令面板
2. 输入`mdp`找到并选中`Markdown Preview： Preview in Browser`
3. 出现两个选项：`github`和`markdown`。选择`markdown`
4. Sublime Text支持自定义快捷键，Markdown Preview默认没有快捷键，我们可以自己为Markdown Preview： Preview in Browser设置快捷键。
方法是在Preferences -> Key Bindings打开的文件的右侧栏的中括号中添加一行代码：快捷健设置成了`alt+m`
```
{ "keys": ["alt+m"], "command": "markdown_preview", "args": {"target": "browser", "parser":"markdown"}  }
```
5. 再次`Ctrl+shift+p`, 输入`dpi`选择`LiveReload: Enable/disable plug-ins`, 回车, 选择 `Simple Reload with delay (400ms)`或者`Simple Reload`，两者的区别仅仅在于后者没有延迟。


