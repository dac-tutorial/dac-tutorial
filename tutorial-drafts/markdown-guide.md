# Markdown 教程

- [Markdown 教程](#markdown-教程)
- [1 简介](#1-简介)
  - [优点](#优点)
  - [编辑器](#编辑器)
- [2 标题](#2-标题)
  - [使用 = 和 - 标记一级和二级标题](#使用--和---标记一级和二级标题)
  - [使用 # 号标记多级标题](#使用--号标记多级标题)
- [3 格式](#3-格式)
  - [段落](#段落)
  - [字体](#字体)
  - [分隔线](#分隔线)
  - [删除线](#删除线)
  - [任务列表](#任务列表)
  - [下划线](#下划线)
  - [*脚注（GFM 暂不支持）](#脚注gfm-暂不支持)
- [4 列表](#4-列表)
  - [无序列表](#无序列表)
  - [有序列表](#有序列表)
  - [列表嵌套](#列表嵌套)
- [5 区块](#5-区块)
  - [区块中使用列表](#区块中使用列表)
  - [列表中使用区块](#列表中使用区块)
- [6 代码](#6-代码)
  - [单行代码](#单行代码)
  - [代码区块](#代码区块)
- [7 链接](#7-链接)
  - [普通链接](#普通链接)
  - [行内链接](#行内链接)
  - [参考链接](#参考链接)
  - [锚点链接](#锚点链接)
- [8 图片](#8-图片)
  - [插入图片](#插入图片)
  - [更改图片格式](#更改图片格式)
- [9 表格](#9-表格)
  - [插入表格](#插入表格)
  - [对齐方式](#对齐方式)
- [10 高级技巧](#10-高级技巧)
  - [HTML 支持](#html-支持)
  - [转义字符](#转义字符)
  - [数学公式](#数学公式)
- [参考资料](#参考资料)

---

![commonmark-cheatsheet](images/commonmark-cheatsheet.png)

---

# 1 简介

![icon_markdown_](images/icon_markdown_.png)

Markdown 是一种轻量级标记语言，创始人为约翰·格鲁伯（John Gruber）。

Markdown 允许人们使用易读易写的纯文本格式编写文档，让写作者专注于写作而不用关注样式。

目前许多网站都广泛使用 Markdown 来撰写说明文件或是用于论坛上发表讯息，例如：GitHub、reddit、Diaspora、Stack Exchange、OpenStreetMap 、SourceForge等。Markdown 甚至能被使用来撰写电子书（如 GitBook）。


## 优点

- 专注你的文字内容而不是排版样式。
- 轻松的导出 HTML、PDF 和本身的 .md 文件。
- 纯文本内容，兼容所有的文本编辑器与字处理软件。
- 可读，直观，是适合所有人的写作语言。


## 编辑器

本教程使用 [Typora](https://typora.io/) 编辑器来讲解 Markdown 的语法，Typora 支持 macOS 、Windows、Linux 平台，且包含多种主题，编辑后直接渲染出效果。Typora 支持导出HTML、PDF、Word、图片等多种类型文件。

> **注意：** 不同平台对于 Markdown 语法的支持不尽相同，表现效果可能会出现些许偏差。本教程主要采用 [Github Flavored Markdown (GFM)](https://help.github.com/articles/basic-writing-and-formatting-syntax/) 标准，并做了适当的内容补充。


# 2 标题

Markdown 标题有两种表示方法。

## 使用 = 和 - 标记一级和二级标题

在标题文本下面添加下划线至少三个`=`或`-`表示一级或二级标题。

```
一级标题
========

二级标题
--------
```

渲染结果如下：

> 一级标题
> ========
>
> 二级标题
> --------
>


## 使用 # 号标记多级标题

使用 **#** 号可表示 1-6 级标题，一级标题对应一个 **#** 号，二级标题对应两个 **#** 号，以此类推。

```
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

渲染结果如下：

> # 一级标题
> ## 二级标题
> ### 三级标题
> #### 四级标题
> ##### 五级标题
> ###### 六级标题



# 3 格式

本节介绍Markdown中的段落和字体格式。


## 段落

Markdown 通过在文本行之间留一个空白行，创建新段落。

对于段落内的文本换行，可以在行尾留下两个空格或者插入一个换行标记 `<br>`。

例如：

```markdown
<!--通常以下两行将被解析为同一段落-->
First paragraph.
The second paragraph. 

---

<!--通过空白行分隔两段文本-->
First paragraph.

The second paragraph. 

---

<!--通过在行尾留下两个空格实现段落换行-->
First paragraph.  
The second paragraph. 

---

<!--通过在行尾添加换行标记实现段落换行-->
First paragraph.<br>
The second paragraph. 
```

渲染效果如下：

> <!--通常以下两行将被解析为同一段落-->
> First paragraph.
> The second paragraph. 
>
> ---
>
> <!--通过空白行分隔两段文本-->
> First paragraph.
>
> The second paragraph. 
>
> ---
>
> <!--通过在行尾留下两个空格实现段落换行-->
> First paragraph.  
> The second paragraph. 
>
> ---
>
> <!--通过在行尾添加换行标记实现段落换行-->
> First paragraph.<br>
> The second paragraph. 



## 字体

Markdown 默认可以使用以下几种字体：

```
*斜体文本*
_斜体文本_

**粗体文本**
__粗体文本__

***粗斜体文本***
___粗斜体文本___
```

渲染结果如下：

> *斜体文本*
> 
> _斜体文本_
> 
> **粗体文本**
> 
> __粗体文本__
> 
> ***粗斜体文本***
> 
> ___粗斜体文本___

也可以用HTML标签表示其他文本样式

```
<span style="color:red">this text is red</span>

<font face="黑体" color=red size=5>这是红色黑体5号字</font>
```

渲染结果如下：

> <span style="color:red">this text is red</span>
> 
> <font face="黑体" color=red size=5>这是红色黑体5号字</font>



## 分隔线

你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：

```
***
* * *
*****
- - -
----------
```

渲染结果如下所示：

> ***
>
> * * *
>
> *****
>
> - - -
>
> ----------


## 删除线

如果段落上的文字要添加删除线，只需要在文字的两端加上两个波浪线 **~~** 即可，实例如下：

```
~~Markdown~~
```

渲染结果如下所示：

> ~~Markdown~~


## 任务列表

在每行前面添加`- [ ]`或 `- [x]`标记为任务列表

```
- [ ] Incomplete item
- [x] Complete item
```

渲染结果如下：

> - [ ] Incomplete item
> - [x] Complete item


## 下划线

下划线可以通过 HTML 的 `<u>` 标签来实现：

```
<u>带下划线文本</u>
```

渲染结果如下：

> <u>带下划线文本</u>

## 脚注

脚注是对文本的补充说明，内容将会在文档底部看到。

语法如下:

```
Here is a footnote[^FOOTNOTE].

[^FOOTNOTE]: Let's try markdown!
```

以下实例演示了脚注的用法：

Here is a footnote[^FOOTNOTE].

[^FOOTNOTE]: Let's try markdown!

# 4 列表

Markdown 支持有序列表和无序列表。

## 无序列表

无序列表使用星号 (`*`)、加号 (`+`) 或减号 (`-`) 作为列表标记：

```
* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项

- 第一项
- 第二项
- 第三项
```

渲染结果保持一致：

> * 第一项
> * 第二项
> * 第三项
>
> + 第一项
> + 第二项
> + 第三项
>
> - 第一项
> - 第二项
> - 第三项



## 有序列表

有序列表使用任意数字并加上 `.` 号表示，Markdown 会自动将其渲染为有序数字如：

```
1. 第一项
1. 第二项
5. 第三项
9. 第四项
```

渲染结果如下：

> 1. 第一项
> 1. 第二项
> 5. 第三项
> 5. 第四项


## 列表嵌套

列表嵌套只需在子列表中的选项添加 4 个空格（或 1 个制表符）即可：

```markdown
1. 第一项：
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2. 第二项：
    - 第二项嵌套的第一个元素
    - 第二项嵌套的第一个元素
```

渲染结果如下：

> 1. 第一项：
>     - 第一项嵌套的第一个元素
>     - 第一项嵌套的第二个元素
> 2. 第二项：
>     - 第二项嵌套的第一个元素
>     - 第二项嵌套的第一个元素



# 5 区块

Markdown 区块引用是在段落开头使用 `>` 符号 ，然后紧跟一个`空格`：

```
> 区块引用
```

渲染结果如下：

> 区块引用


区块是可以嵌套的，一个 `>` 符号是最外层，两个 `>` 符号是第一层嵌套，以此类推退：

```
> 最外层
> > 第一层嵌套
> > > 第二层嵌套
```

渲染结果如下：

> 最外层
> > 第一层嵌套
> >
> > > 第二层嵌套



## 区块中使用列表

区块中使用列表实例如下：

```
> 区块中使用列表
> 1. 第一项
> 2. 第二项
> + 第一项
> + 第二项
> + 第三项
```

渲染结果如下：

> 区块中使用列表
> 1. 第一项
> 2. 第二项
> + 第一项
> + 第二项
> + 第三项



## 列表中使用区块

如果要在列表项目内放进区块，那么就需要在 `>` 前添加四个空格的缩进。

区块中使用列表实例如下：

```
* 第一项
    > GitHub
    > Markdown
* 第二项
```

渲染结果如下：

* 第一项
     > GitHub
     > Markdown
 * 第二项



# 6 代码

本节介绍Markdown中插入代码的方法。


## 单行代码

单行代码可使用一对反引号 (**`**) 把它包起来，例如：

```
`inline code`
```

渲染结果如下：

> `inline code`

如果要在代码区段内插入反引号，你可以用多个反引号来开启和结束代码区段，例如

```
``There is a literal backtick (`) here.``
```

> ``There is a literal backtick (`) here.``



## 代码区块

代码区块可使用使用一对 ``` 或 ~~~ 包裹一段代码，还可同时指定相应的编程语言，Markdown 会根据指定的代码语言对该段代码进行语法高亮，例如：

~~~markdown
```python
def hanoi(n, a, b, c):
    if n == 1:
        print(a, '-->', c)
    else:
        hanoi(n-1, a, c, b)
        print(a, '-->', c)
        hanoi(n-1, b, a, c)

print(hanoi(5, 'a', 'b', 'c'))
```
~~~

渲染结果如下：

```python
def hanoi(n, a, b, c):
    if n == 1:
        print(a, '-->', c)
    else:
        hanoi(n-1, a, c, b)
        print(a, '-->', c)
        hanoi(n-1, b, a, c)

print(hanoi(5, 'a', 'b', 'c'))
```

GFM 中还可以显示 `diff` 效果，即展示一个文件内容的增加与删除（绿色表示新增，红色表示删除）。在三个反引号后面加上 `diff` 标识符，并且其代码块行头以 `+` 开头表示新增，`-` 开头表示删除。例如：

~~~markdown
```diff
+ print('Hello!')
- print('Goodbye!')
```
~~~

渲染结果如下：

```diff
+ print('Hello!')
- print('Goodbye!')
```



# 7 链接

GFM 支持 URL 链接、行内链接、参考链接和锚点链接：


## 普通链接

GitHub 可自动从标准 URL 创建链接，例如：http://www.baidu.com

也可通过 `<>` 包裹 URL 来创建链接，例如：

```
<https://www.baidu.com/>
```

其渲染结果与标准 URL 相同：
> <https://www.baidu.com/>



## 行内链接

在`[]`里输入链接文本，在其后的`()`中输入 URL 和可选的标题。

> **提示：** 链接文本不必一定是文本。图片或其他 HTML 元素都可以成为链接。

例如：
```
This is [an example](http://example.com/ "Title") inline link.
```

渲染效果如下：

> This is [an example](http://example.com/ "Title") inline link.



## 参考链接

链接也可以添加上一个 `id`，然后可在任意位置定义`id`的 URL，例如：

```
This is [an example][id] reference-style link.

[id]: http://example.com/  "Optional Title Here"
```

渲染效果如下：

> This is [an example][id] reference-style link.
>
> [id]: http://example.com/  "Optional Title Here"



## 锚点链接

每一个标题都是一个锚点（不包括`#`等字符），也可以用 HTML 方式定义锚点 id，不过要注意使用标题锚点时：

- 标题中的英文字母都要被转化为**小写字母**
- 空格换成 `-`
- 去除句号、括号等 HTML 字符
- 标题名相同时，第2个锚点引用时加后缀，如 `标题-2`
- GFM 锚点也支持中文

我们可以使用锚点来创建 GFM 标准下的 Mardown 文档目录，本教程目录的源码如下所示：

```

```



# 8 图片

Markdown 中插入图片的方法和插入链接的方法类似，只需要在链接前添加一个 `!`。

##  插入图片

```
![alt 属性文本](图片地址 "可选标题")
```

使用实例：

```markdown
![GitHub Desktop](https://desktop.github.com/images/desktop-icon.svg "GitHub Desktop Icon")
```

渲染结果如下：

![github-desktop-icon](images/github-desktop-icon.svg "GitHub Desktop Icon")



## 更改图片格式

可以使用 html 中的 `<img>` 标签对图片格式进行限定，例如：

```html
<img src="https://desktop.github.com/images/desktop-icon.svg" alt="GitHub Desktop Icon" title="GitHub Desktop Icon" width="50%"/>
```

渲染结果如下：

<img src="images/github-desktop-icon.svg" alt="A GitHub Desktop Icon" title="GitHub Desktop Icon" width="50%" />


# 9 表格

本节介绍Markdown的表格制作方法。


## 插入表格

Markdown 表格使用 **|** 来分隔每列，使用 **-** 来分隔表头和其他行。

必须在表格前包含空白，以便其正确呈现，表格末尾的竖线可选。

语法格式如下：

```
| Column 1 | Column 2 | Column 3 |
| -------- | -------- | -------- |
| Value 1  | Value 2  | Value 3  |
```

渲染结果如下：

| Column 1 | Column 2 | Column 3 |
| -------- | -------- | -------- |
| Value 1  | Value 2  | Value 3  |


## 对齐方式

单元格中的内容默认左对齐，可通过对齐标记改变表格内容对齐方式：

- `-:` 设置内容和标题栏居右对齐；
- `:-` 设置内容和标题栏居左对齐；
- `:-:` 设置内容和标题栏居中对齐；
-  `:` 和 `-` 之间不能有空格，`-` 的数量无限制；

例如：

```
| default | centered | right-aligned | left-aligned |
| ------- | :------: | ------------: | :----------- |
| a       |    b     |             c | d            |
```

渲染结果如下：

| default | centered | right-aligned | left-aligned |
| ------- | :------: | ------------: | :----------- |
| a       |    b     |             c | d            |


# 10 高级技巧

本节介绍一些常用的 Mardown 高级技巧，更多内容请参考 [Commonmark](https://spec.commonmark.org/ ) 的说明。

##  HTML 支持

不在 Markdown 涵盖范围之内的标签，可以直接在文档里面使用 HTML 撰写。

例如要在 Markdown 中表示键盘按键可使用 `<kbd>` 标签：

```
<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 
```

渲染结果为：
> <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd>


## 转义字符

Markdown 使用了很多特殊符号来表示特定的意义，如果需要显示特定的符号则需要使用转义字符 `\`。

```
**一对星号表示文本加粗** 

\*\*使用转义字符可正常显示星号\*\*
```

渲染结果如下：

> **一对星号表示文本加粗** 
>
> \*\*使用转义字符可正常显示星号\*\*

Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：

```
\   反斜线
`   反引号
*   星号
_   下划线
{}  花括号
[]  方括号
()  小括号
5#   井字号
+   加号
-   减号
.   英文句点
!   感叹号
```

## 数学公式

Markdown 可使用 Mathjax 对 LaTeX 数学公式进行渲染。

如果要写一小段行内数学公式，使用一对 `$` 把它包起来，例如：

```
$\begin{aligned}  f(x) &=(m+n)^2 \\ & =m^2+2m+n^2 \end{aligned}$
```

渲染结果如下：

> $\begin{aligned}  f(x) &=(m+n)^2 \\ & =m^2+2m+n^2 \end{aligned}$

如果要插入数学公式块，需要一对`$$`表示开启和结束，例如：

```
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$ 
```

渲染结果如下：

> $$
> \mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
> \mathbf{i} & \mathbf{j} & \mathbf{k} \\
> \frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
> \frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
> \end{vmatrix}
> $$


# 参考资料

+ [Markdown 教程 | 菜鸟教程](https://www.runoob.com/markdown/md-tutorial.html)
+ [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
+ [Commonmark Markdown Reference](https://commonmark.org/help/) 