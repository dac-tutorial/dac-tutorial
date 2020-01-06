# 引言：文档代码化

**文档代码化** **([*Docs as Code*](http://www.writethedocs.org/guide/docs-as-code/))**，是一种新兴的的技术文档开发模式，特指使用代码开发的方式和工具进行文档开发。

文档代码化意味文档开发人员需遵从与产品开发团队相同的工作流程，使用代码开发的方式和工具开发文档，可有效节省工具成本，提升文档开发效率，并增强产品研发和文档写作的协同管理。

目前，微软、亚马逊和阿里等高科技公司已逐渐将文档代码化应用于生产实践，其文档开发流程大致包括五大步骤：

1. 使用 Markdown、reStructuredText 等标记语言写作；
2. 通过 Git 进行版本管理和协同写作；
3. 使用代码开发集成环境作为写作工具；
4. 通过文档发布工具将 Markdown、reStructuredText 文件发布为网页或PDF等格式；
5. 收集文档的用户使用数据，不断迭代改进文档质量。

本教程主要使用 Sphinx 文档开发工具向同学们介绍了文档代码化开发的完整流程，全教程包括三大部分的内容：

+ **快速入门：**详述了在 Windows 和 macOS 两大操作系统上配置 Sphinx 开发环境的方法，并以实例的形式介绍了创建一个 Sphinx 项目的完整流程 ；
+ **语法指南：**介绍了 Sphinx 的默认标记语言 reStructuredText 的基础语法，也介绍了如何添加 Sphinx 对 Markdown 标记语言的支持，以及 Markdown 的基础语法。
+ **专题学习：**以专题的形式介绍了更多 Sphinx 进阶应用，包括本地与云端发布、主题定制、多人协作开发等，前三个专题能够帮助同学们掌握一整套 “reStructuredText + Sphinx + Read the Docs” 的文档开发工具链，第四个拓展专题介绍了另一套由 “Markdown + Jekll + GitHub Pages” 组成的文档开发工具链