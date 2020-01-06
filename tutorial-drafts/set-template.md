# Sphinx定制主题


##  使用既定主题


下载 Sphinx 后，其安装包中即含有名为 "themes" 的文件夹，文件夹内含Sphinx自带的模板，包括  "epub"、"agogo" 等。只需简单几步，同学们便可以使用其内置模板：

### 修改配置文件

假设我们想使用 "haiku" 主题，则需要在 "conf.py" 中进行如下设置：

     html_theme = "haiku"

### 生成网页

命令行中再次输入 `make html`, 即可生成相应主题的网页（"test" 是我的Sphinx文件所在的文件夹）：

     C:\Users\hp\Desktop\test>make html

![haiku主题展示](images/haiku-theme.png)

而其实，Sphinx中最常使用的主题是 [sphinx-rtd-theme](https://sphinx-rtd-theme.readthedocs.io/en/latest/)，但是在 "themes" 文件夹里却没有，因此我们需要先安装该主题，再进行设置。

### 安装主题模板

     C:\Users\hp>pip install sphinx-rtd-theme

出现如下代码段即可表示安装成功：

	  Installing collected packages: sphinx-rtd-theme
	  Successfully installed sphinx-rtd-theme-0.4.3

### 修改配置文件：

在 "conf.py" 中进行如下设置：

    html_theme = 'sphinx_rtd_theme'

### 生成网页

 命令行中再次输入 `make html`, 即可生成相应主题的网页：

     C:\Users\hp\Desktop\test>make html

![rtd主题展示](images/sphinx-rtd-theme.png)




##  用户自定义主题（无Python/HTML/CSS基础请跳过）
Sphinx里面的模板是已经定义好了的，但是如果我们想修改样式、添加内容该怎么办呢？

### 增添内容
如若想对主题增添内容，那我们需要使用 ***jinja2*** 语言， ***jinja2*** 是 ***Flask*** 作者开发的一个模板系统，起初是仿 ***django*** 模板的一个模板引擎，为 ***Flask*** 提供模板支持，由于其灵活，快速和安全等优点被广泛使用。

在sphinx中使用 ***jinja2***，可以在继承原有主题的基础上，对网站内容进行增添改写。

####  安装 ***jinja2***
命令行中输入 `pip install jinja2 `，如下所示：

     C:\Users\hp>pip install jinja2

出现如下代码块即表示安装成功：

     Installing collected packages: jinja2
     Successfully installed jinja2-2.10.3

#### 创建 “layout.html”
要自定义文档的输出，可以通过将与原始文件名同名的文件添加到模板目录中来覆盖所有的模板。Sphinx将首先在 "config.py" 中的 “template_path” 中查找模板，如果找不到它正在寻找的模板，将回退到所选主题的模板。

Sphinx安装目录下的 “themes”-“basic” 中包含 “basic” 主题，该主题中的 “layout.html” 为基本模板提供了几个块，这些块将首先填充数据，并由所有内置的Sphinx主题使用。而在 “templates_path” 中具有相同名称的模板会覆盖所选主题提供的模板。

因此，我们需要在文件夹里找到 "source"-"templates" 文件夹，然后在 "templates" 文件夹下创建 “layout.html”。

使用 ***jinja2*** 在 "layout.html" 中编写如下代码：

     {# Import the theme's layout. #}
     {% extends "!layout.html" %}
    
     {# Add some extra stuff before and use existing with 'super()' call. #}
     {% block footer %}
     <h2>My footer of awesomeness.</h2>
     {{ super() }}
     {% endblock %}

对以上代码块解释如下：

+ `{#...#}` 相当于注释，是为了方便理解代码。

+  `{% extends "!layout.html" %}` 在带有感叹号的被覆盖模板的名称前面加上前缀，Sphinx将从底层HTML主题加载布局模板。

+ `{% block footer %}` 表示对 *footer* 代码块进行改写。

+ `{{ super() }}` 表示继承原模板，即呈现块的原始内容。

+ `{% endblock %}` 表示代码块结束。

此段代码的作用是在网页底端加入 *My footer of awesomeness* 这句话。

#### 修改配置文件

与此同时，在 "config.py" 中进行如下设置：

     templates_path = ['_templates']


#### 生成网页
点击保存后，重新在命令行中键入  `make html`，即可生成如下网页：

![添加内容至网页](images/add-footer.png)


### 修改样式

如若想对主题增添内容，那我们需要使用 ***css*** 语言

#### 创建样式文件


在文件夹里找到 "source"-"static" 文件夹，然后在 "static" 文件夹下创建 “my-styles.css”.

使用 ***css*** 语言 在 "my-styles.css" 中编写如下代码：

     footer {
     background-color: red;
     }

该行代码的作用是把网页脚注背景色设置为红色。


#### 修改配置文件

与此同时，在 "config.py" 中进行如下设置：

     html_static_path = ["_static"]

+ 如果同学们的Sphinx版本<=1.5, 请在 "config.py" 添加如下代码：

      {# Import the theme's layout. #}
      {% extends "!layout.html" %}

      {# Custom CSS overrides #}
      {% set css_files = css_files + ['_static/my-styles.css'] %}

+ 如果同学们的Sphinx版本>1.5, 请在 "config.py" 添加如下代码：

          def setup(app):
          app.add_stylesheet("my-styles.css") # also can be a full URL
          #app.add_stylesheet("ANOTHER.css")
          #app.add_stylesheet("AND_ANOTHER.css")

#### 生成网页

点击保存后，重新在命令行中键入  `make html`，即可生成如下网页：

![改变网页样式](images/change-footer-color.png)

## 扩展内容（ ***jinja2、html、css*** 基础）

### ***HTML***


超文本标记语言（英语：HyperText Markup Language，简称：HTML）是一种用于创建网页的标准标记语言。

同学们可以使用 ***HTML*** 来建立自己的 WEB 站点，***HTML*** 运行在浏览器上，由浏览器来解析。

#### 示例

     <!DOCTYPE html>
     <html>
     <head>
     <meta charset="utf-8">
     <title>菜鸟教程(runoob.com)</title>
     </head>
     <body>
     <h1>我的第一个标题</h1>
     <p>我的第一个段落。</p>
     </body>
     </html>

#### 代码解释

+ `<!DOCTYPE html>` 声明为HTML5文档

+ `<html>` 是 ***HTML*** 页面的根元素

+ `<head>` 元素包含了文档的元数据，如 `<meta charset="utf-8">`表示网页编码格式为 ***utf-8***

+ `<title>` 描述了文档的标题

+ `<body>` 包含了可见的页面内容

+ `<h1>` 定义一级标题

+ `<p>` 定义一个段落

#### 推荐学习

网上有很多免费的 ***HTML*** 教程，推荐如下：

+ [HTML菜鸟教程](https://www.runoob.com/html/html-tutorial.html)

+ [SiKi学院JavaEE WEB前端第一季](https://www.bilibili.com/video/av35875257?from=search&seid=1420480764639162062)


### ***CSS***

 ***CSS*** 用于控制网页的样式和布局。


#### 示例

     body
     {
     background-color:red;
     }
     h1
     {
     color:orange;
     text-align:center;
     }
     p
     {
     font-family:"Times New Roman";
     font-size:20px;
     }

#### 代码解释

+         body
          {
          background-color:#d0e4fe;
          } 
     这段代码表示网页主题的背景色为红色


+         h1
          {
          color:orange;
          text-align:center;
          }
     这段代码表示标题1字体颜色为橘色，居中显示

+         p
          {
          font-family:"Times New Roman";
          font-size:20px;
          }
     这段代码表示段落文字的字体为 ***Times New Roman***，字体大小为 ***20px***


#### 推荐学习

网上有很多免费的 ***CSS*** 教程，推荐如下：

+ [CSS菜鸟教程](https://www.runoob.com/css/css-tutorial.html)


### ***jinja2***

***Jinja*** 模版是一个文本文件，通过它可以生成任何文本格式的文件，例如 ***.html***、***.xml***、***.csv*** 等等。一个 ***Jinja*** 模版并不需要有一个特定的扩展名，完全可以自定义或是不定义.

***Jinja*** 模版包含了变量、表达式和标签，当模版被渲染时，变量和表达式会被替换为特定的值，标签用来控制模版的逻辑。模版的语法受到了 ***Django*** 和 ***python*** 的启发.

在本教程中，我们使用Flask框架来辅助jinja2的讲解。





#### 示例

     <!DOCTYPE html>
     <html lang="en">
     <head>
     <title>My Webpage</title>
     </head>
     <body>
     <ul id="navigation">
     {% for item in navigation %}
          <li><a href="{{ item.href }}">{{ item.caption }}</a></li>
     {% endfor %}
     </ul>

     <h1>My Webpage</h1>
     {{ a_variable }}

     {# a comment #}
     </body>
     </html>


#### 代码解释

+ `{% ... %}` 表示循环结构

+ `{{...}}` 里内含变量，需要对其进行赋值

+ `{#...#}` 用于注释，方便理解代码，并不会输出到结果文件中

+ `{% endfor %}` 表示循环体的结束

+ `{{ item.href }}` 表示访问 ***item*** 这个变量的 ***href*** 属性










