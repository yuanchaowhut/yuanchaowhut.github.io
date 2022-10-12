

## 第一节：插入文本

a：当前字符的后一个位置插入

i：当前字符的前一个位置插入

o：当前编辑位置下面新起一行

A：在行最后位置插入

I：  在行最前的位置插入

O：在当前编辑位置的上面新起一行

w：保存

wq：保存并退出(w and q)



## 第二节：Vim模式

进入vim默认是normal模式

还有 : cmd命令模式 和 v(visual)可视化模式

命令模式：

保存  :w

退出  :q

保存并退出   :wq

纵向分屏  :vs

横向分屏  :sp

全局替换   :% s/foo/bar/g      （foo被替换的，bar替换后的）

设置显示行号  :set nu

Visual模式：

normal模式下使用 v 进入 visual 模式选择

使用 V 选择行

使用 ctrl+v 进行块状选择



## 第三节：快捷删除

### 输入模式下快速纠错

ctrl+h 删除上一个字符

ctrl+w 删除上一个单词

ctrl+u 删除当前行

ctrl+a (终端) 快速移动到开头

ctrl+e (终端)快速移动到结尾

ctrl+f (终端)光标后移

ctrl+b (终端)光标迁移

### 快速切换insert和normal模式

insert -> normal: ctrl+c 或者 ctrl+[

gi: normal 模式切换到 insert 模式，且到上次编辑的地方



## 第四节：快捷移动

### normal 移动的快捷方式

w/W: 移动到下一个word/WORD 开头

e/E: 移动到下一个 word/WORD 结尾

b/B: 移动到上一个 word/WORD 开头  (backword)

### 行间搜索移动

f{char}: 当前光标往行后搜索字符, 分号(;)下一个找到的字符，逗号(,)上一个找到的字符

F{char}: 当前光标往前搜索字符

0: 移动到行首第一个字符

^: 移动到第一个非空白字符

$: 移动到行尾

g_: 移动到行尾非空白字符

### 页面移动

gg: 文件开头

G: 文件结尾

H: 屏幕的开头(Head)

M: 屏幕的中间(Middle)

L: 屏幕的结尾(Lower)

crtl+u: 上翻页（upword）

ctrl+f: 下翻页（forword）

zz: 屏幕置为中间



## 第五节：增删改查

### 增加

Normal模式 a/i/o A/I/O

### 删除

Normal模式 

x 删除一个字符

4x 删除4个字符

d(delete)

daw 删除单词和周围空格（delete around word）

diw 删除单词（dw）

dd 删除行

dt{char} 删除直到

d$ 删除到结尾

d0 删除到开头

2dd 删除两行

R 不断替换多个字符

S 删除整行进行插入 

C 删除整行进行插入

### 修改

Normal模式下

r replace 替换一个字符

c change 

cw 删除单词进入插入模式 change word

ct{char} 删除到字符，进入插入模式	

s substitute 删除并进入插入模式 eg: 4s 删除4个字符进入插入模式 

### 查询

/ 前向搜索

? 反向搜索

n/N 下一个或者上一个

\		*/# 当前单词的前向和后向匹配

搜索结果高亮 :set hls (high light search)

:set incsearch



## 第六节：快速替换

### 替换命令

 **:[range] s[ubstitute]/{pattern}/{string}/[flags]**

**range表示范围：**
	10, 20 表示10-20行
	% 表示全部
	pattern是要替换的模式
	string是替换后文本
**Flags：**

​	g(global) 表示全局范围内执行
​	c(confirm)表示确认，可以确认或者拒绝修改
​	n(number)报告匹配到的次数而不替换，可以用来查询匹配次数

### 精确替换

```
//将quack替换为jiao
:% s/\<quack\>/jiao/g

//只统计quack出现的次数不执行替换
:% s/quack//n
```

### 退出搜索高亮

```
:noh
```


