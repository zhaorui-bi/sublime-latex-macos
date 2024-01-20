# sublime+latex+skim //macos版本

## 下载mactex

下载地址：

```
https://tug.org/mactex/mactex-download.html
```

下载.pkg文件正常安装即可

---

## 下载sublime

下载地址：

```
https://www.sublimetext.com
```

同样正常下载即可

---

## 下载sublime上的插件

1. 按command+shift+p打开Command pallet，输入“Install Package”按回车；

2. 输入“LaTeX”找到“LaTeX Tools”按回车安装，同样方法安装“LaTeX-cwl”
3. 重新启动sublime

---

## 下载skim

下载地址：

```
https://skim-app.sourceforge.io
```

//可能需要用到vpn加速

----

## skim设置修改

skim—>preference—>sync—>preset

将preset修改为sublime text

上面的check for file changes和reload automatically 对勾打上

//skim：command+shift+左键单击 反向定位！！！很好用

---

## 测试配置

首先 shift+command+b选择xelatex编译如下测试代码

```
\documentclass{article}

\usepackage{fontspec, xunicode, xltxtra}

\setmainfont{Hiragino Sans GB}

\title{Title}

\author{Elijah}

\begin{document}

\maketitle{}

\section{Introduction}

\end{document}
```

shift+command+鼠标点击skim可以反向定位

---

## sublime的一些设置

打开settings...——setting, 替换成如下的内容

//当然很多东西也可以自己来设置

```
{
	"added_words":
	[
		"reactance"
	],
	"auto_complete": true,
	"auto_complete_delay": 100,
	"auto_complete_selector": "source, text",
	"auto_complete_triggers":
	[
		{
			"characters": "<",
			"selector": "text.html"
		},
		{
			"characters": "\\",
			"selector": "text.tex.latex"
		}
	],
	"auto_match_enabled": true,
	"color_scheme": "Packages/Color Scheme - Default/Mariana.sublime-color-scheme",
	"font_size": 18,
	"ignored_packages":
	[
		"Vintage"
	],
	"spell_check": true,
	"tab_completion": false,
	"update_check": false
}
```

## 一些快捷键配置

打开settings...——key bindings

//当然很多东西也可以自己来设置

```
[
	{ "keys": ["f5"], "command": "build" },
	{ "keys": ["command+r"], "command": "show_panel", "args": {"panel": "replace", "reverse": false} },
	{ "keys": ["command+["], "command": "jump_back" },
	{ "keys": ["command+]"], "command": "jump_forward" },
	{ "keys": ["command+t"], "command": "title_case" },
	{ "keys": ["command+l"], "command": "lower_case" },
	{ 	"keys": ["command+1"], 
		"context":  [
			{"key": "selector", "operator": "equal", "operand": "text.tex.latex"}],
		"command": "jump_to_pdf", "args": {"from_keybinding": true}},
	{ "keys": ["command+2"],
		"args": {"only_current_file": true},
		"context":  [
			{"key": "selector", "operator": "equal", "operand": "text.tex"}],
		"command": "latex_toc_quickpanel"},
]
```

## 设置snippet

打开settings...——browse packages 打开

将usersnappets文件夹 放到此处即可

//当然很多东西也可以自己来设置
