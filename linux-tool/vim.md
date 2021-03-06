# vim

## 先导说明

### 如何判断vim当前的模式

1. 普通模式(normal)，使用vim打开一个文本文件后,默认进入的就是普通模式
2. 插入模式(insert)，左下角有`-- INSERT --`字样
3. 可视化模式(visual)，左下角有`-- VISUAL --`、`-- VISUAL BLOCK --`字样
4. 替换模式(replace)，左下角有`-- REPLACE --`字样

### 注意事项

1. 在vim中，大写字母和小写字母的命令是有区别的
2. vim中的句子是以./!/?结尾且结尾处有至少一个空格
3. vim中的段落指整个有文本区域的前后是否有至少一个空行

## 模式

```
v        可视化选择模式
V        可视化整行选择模式
ctrl+v   可视化块状选择模式
R        进入替换模式
```

## 编辑查找

**Normal模式**
```
ra       将光标位置的字符修改为a
R        进入replace模式,输入的字符会替换现有的字符
s        删除光标位置的字符,并进入insert模式
5s       删除光标位置向后的5个字符,并进入insert模式
S        删除光标位置的整行内容,并进入insert模式
cw       从光标位置向后删除当前单词,并进入insert模式
ct.      从光标位置向后删除到.字符,并进入insert模式
cc       删除整行,并进入insert模式
x        从光标位置向后删除一个字符,并复制被删除的字符(vim内置剪切板)
5x       从光标位置向后删除5个字符,并复制被删除的字符(vim内置剪切板)
X        从光标位置向前删除一个字符,并复制被删除的字符(vim内置剪切板)
5X       从光标位置向前删除5个字符,并复制被删除的字符(vim内置剪切板)
daw      从光标位置向后删除一个单词(包括单词间隔)
dw       从光标位置向后删除一个单词(daw命令缩写)
5dw      从光标位置向后删除5个单词(包括单词间隔)
diw      从光标位置向后删除一个单词
5diw     从光标位置向后删除5个单词
dt;      从光标位置向后删除到;符号之间的所有内容
ds       删除一个句子
dp       删除一个段落
d0       从光标位置删除到行首
d$       从光标位置删除到行尾
d1G      从光标位置删除到第一行
dG       从光标位置删除到最后一行
dd       删除当前行
5dd      从光标所在行向下删除3行
D        从光标位置删除到行尾
u        撤销修改
yy       复制当前行(vim内置剪切板)
Y        复制当前行(vim内置剪切板)
5yy      从光标所在行向下复制3行
ys       复制一个句子
yp       复制一个段落
p        粘贴到光标位置的下方(vim内置剪切板)
P        粘贴到光标位置的上方(vim内置剪切板)
5p       从光标位置向下粘贴5次
5P       从光标位置向上粘贴5次
gi       快速进入上次编辑位置
a        光标位置后追加
i        光标位置插入文本
o        在当前行下面新增行
A        在行尾追加
I        在行首插入
O        在当前行上面新增行
*        向下查找光标位置的单词
##        向上查找光标位置的单词
fa       在当前行向后查找字母a,并跳转到第一个匹配项
ta       在当前行向后查找字母a,并跳转到第一个匹配项的前一个字符
Fa       在当前行向前查找字母a,并跳转到第一个匹配项
Ta       在当前行向前查找字母a,并跳转到第一个匹配项的前一个字符
,        在当前行继续向前查找字母(配合f、t、F、T命令)
;        在当前行继续向后查找字母(配合f、t、F、T命令)
ZZ       写入更改并退出
```

## 光标或行移动

**Normal模式**
```
h        向前移动光标
j        向下移动光标
k        向上移动光标
l        向后移动光标
e        移动光标到下一个单词末尾
w        移动光标到下一个单词开头
b        移动光标到上一个单词开头
E        移动光标到下一个单词末尾(空格分隔)
W        移动光标到下一个单词开头(空格分隔)
B        移动光标到上一个单词开头(空格分隔)
n        移动光标到下一个查找匹配项
N        移动光标到上一个查找匹配项
0        移动光标到行首
^        移动光标到行首第一个非空白字符
$        移动光标到行尾
g_       移动光标到行尾最后一个非空白字符
L        移动光标到当前屏幕下方
M        移动光标到当前屏幕中间
H        移动光标到当前屏幕上方
gg       移动光标到第一行
G        移动光标到最后一行
5gg      移动光标到第5行
5G       移动光标到第5行
ctrl+o   返回前一次记忆的光标位置
ctrl+i   返回后一次记忆的光标位置
ctrl+u   向上移动半屏
ctrl+d   向下移动半屏
zz       将当前光标所在的行置于屏幕中间
zt       将当前光标所在的行置于屏幕上方
zb       将当前光标所在的行置于屏幕下方
%        移动光标到下一个或上一个括号匹配
```

## Insert模式

```
ctrl+h   删除一个字符
ctrl+w   删除一个单词
ctrl+u   删除一行
```

## Visual模式

**下面的命令主要是在可视化选择模式中使用,可视化整行选择和块状选择模式中部分命令不适用**
```
y        复制所选
x        删除所选字符(单字符选择)
d        删除所选行(行选择或块状选择)
T#       向前选中到第一个匹配的#符号之间所有文本
t;       向后选中到第一个匹配的;符号之间所有文本
aw       选中单词(包括单词间隔)
iw       选中单词
a{       选中括号和括号里面的内容(其它类型的括号或引号也支持)
i{       选中括号里面的内容(其它类型的括号或引号也支持)
as       选中整个句子(包括空格)
ap       选中整个段落(包括空格)
is       选中整个句子
ip       选中整个段落
u        将选中区域的英文字母转换为小写
U        将选中区域的英文字母转换为大写
```

## 多文件操作

**可以通过光标的闪烁或者窗口左下方的文件名加粗显示来判断当前是处于哪一个窗口**
```
:e f       打开当前路径下名称为f的文件
:ls        查看当前缓冲区打开的所有文件
:b n       选择缓冲区中的第n个文件
:b f       选择缓冲区中文件名为f的文件
ctrl+w+s   水平切分窗口
ctrl+w+v   垂直切分窗口
ctrl+w+w   循环切换所有已经打开的窗口
ctrl+w+h   切换到当前所在窗口左边的窗口(左方向键也可以)
ctrl+w+l   切换到当前所在窗口右边的窗口(右方向键也可以)
ctrl+w+k   切换到当前所在窗口上边的窗口(上方向键也可以)
ctrl+w+j   切换到当前所在窗口下边的窗口(下方向键也可以)
ctrl+w+H   移动当前所在窗口到左边
ctrl+w+L   移动当前所在窗口到右边
ctrl+w+J   移动当前所在窗口到上边
ctrl+w+K   移动当前所在窗口到下边
ctrl+w+=   重置窗口宽高
ctrl+w+|   设置当前窗口为最大宽度
ctrl+w+_   设置当前窗口为最大高度
```

## 命令

**必须在Normal模式下输入":"符号打开命令输入**
```
:q       退出
:q!      忽略更改并退出
:wq      写入更改并退出
:x       写入更改并退出
:w       写入
:e       重新加载当前文件
:e!      放弃所有改动,重新加载当前文件
:vs      垂直分屏
:vs f    垂直分屏,并打开名称为f的文件
:sp      水平分屏
:sp f    水平分屏,并打开名称为f的文件
/vim     向后搜索字符串vim
?vim     向前搜索字符串vim

:% s/a/b/g       搜索所有行,查找替换所有a为b(%表示搜索所有行,后面的g[lobal]表示全部替换)
:% s/a/b/c       搜索所有行,查找替换所有a为b(后面的c[onfirm]表示每次替换都进行确认)
:% s/a//n        搜索所有行,查找所有a(后面的n[umber]表示不替换但查找匹配数量)
:10,20 s/a/b/g   搜索10到20行,查找替换所有a为b
:% s#/a#/b#g     搜索所有行,查找替换所有/a为/b(#也可以作为分隔符)
```

**标签页(Tab)比较少使用，简单了解下即可**
```
:tabe f    在新的tab页编辑名称为f的文件
ctrl+w+T   将当前窗口移动到新的tab页
:tabc      关闭当前标签页和其中所有窗口
:tabo      保留关闭非活动的标签页和其中所有窗口
:tabn      切换到后一个tab页
gt         切换到后一个tab页
:tabn N    切换到指定编号的tab页(N为数字)
Ngt        切换到指定编号的tab页(N为数字)
:tabp      切换到前一个tab页
gT         切换到前一个tab页
```

## vim配置
**括号中的是设置项的单词缩写**
```
set number        行号(nu)
set hlsearch      高亮搜索(hls)
set incsearch     实时搜索
set showcmd       展示命令
set shiftwidth=4  自动缩进时的宽度(sw)
set tabstop=4     tab的宽度(ts)
set expandtab     tab换成空格
syntax on         代码语法高亮
```
## vim按键

**映射按键与某个连续的操作绑定，C表示Crtl按键，CR表示回车，按键和命令可以相互组合**

下面的示例表示按下Ctrl+X不保存并退出和按下Ctrl+R忽略更改重新加载所有内容
```
map <C-X> <Esc>:q!<CR>
imap <C-X> <Esc>:q!<CR>
map <C-R> <Esc>:e!<CR>
imap <C-R> <Esc>:e!<CR>
```

Last Modified 2021-03-08