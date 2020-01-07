Sphinx 可以为我们提供多种发布的格式，如 HTML、LaTeX、ePub、Texinfo、纯文本等。在这里我们主要为同学们介绍几种常见的发布格式。

本地发布
========

发布 HTML
------------
发布 HTML 格式是 Sphinx 发布最基础的操作，如我们在学习生成第一个 Sphinx 项目时所看到的，只需在发布时使用 make html 语法即可。 
（图片）

发布 PDF
------------

生成PDF的前提是安装了texlive，如果要生成中文PDF，还需要确认安装了东亚语言包和字体包(texlive-lang-cjk, texlive-fonts-recommands之类）。
然后配置conf.py，在latex_elements中加入:
latex_elements = {
# The paper size ('letterpaper' or 'a4paper').
#'papersize': 'letterpaper',

# The font size ('10pt', '11pt' or '12pt').
#'pointsize': '10pt',

# Additional stuff for the LaTeX preamble.
'preamble': '''
\\hypersetup{unicode=true}
\\usepackage{CJKutf8}
\\AtBeginDocument{\\begin{CJK}{UTF8}{gbsn}}
\\AtEndDocument{\\end{CJK}}
''',
最后运行 make latexpdf 即可。

发布纯文本
------------

云端发布
========
使用 Read the Docs 进行发布
-----------------------------
使用 Github Pages 进行发布
-----------------------------
