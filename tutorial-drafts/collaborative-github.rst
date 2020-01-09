Sphinx多人协作开发（Github）
=========
速识Github
--------------
**Github** 是一个基于 **Git** （一个开源的分布式版本控制系统）的版本控制和协作的代码托管平台，因为只支持 git 作为唯一的版本库格式进行托管，因此得名 Github。使用 Github 只需要利用邮箱注册账户，访问 https://github.com 或下载 Github Desktop 既可。将 Github 作为一个协作开发工具，能够使团队工作更有效率，具有更高的生产力。

Github 使用手册
-----------
本教程将以 Github Desktop （目前仅支持支持Windows和macOS两个平台）为例，带同学们学习一些 Github 的基础操作。

安装 Github Desktop 
^^^^^^^^^^^^^^^^^^^^
注册 Github 账号
*****************
使用 GitHub Desktop 需要一个 GitHub.com 或 GitHub Enterprise 帐户，注册流程不再赘述，建议大家使用自己比较常用的邮箱地址注册账号，私人计划 (personal plan)可选择免费计划或付费计划，曾经免费用户只能创建开源仓库，但在GitHub 在被 Microsoft 收购后私有仓库已经可以免费使用了。

Github Desktop 下载以及快速入门
**********************************
GitHub Desktop 官网： https://desktop.github.com/

.. image:: https://github.com/yangzy1202/Docs-as-Code/blob/master/tutorial-drafts/images/github-desktop-official.png

根据自己的操作系统安装相应的 GitHub Desktop 版本，以下操作均基于GitHub Desktop for Windows (64bit)版（GitHub Desktop无法在32位Windows系统下工作），安装完成后需要登录到 GitHub 帐户，之后是“Configure Git（配置 Git）”步骤，用于设置名称和电子邮件地址。为确保提交正确到你的GitHub 帐户上， 这里需要填写GitHub 帐户关联的电子邮件地址（但如果同学们希望将自己的邮箱保密，可以使用 GitHub-提供的“no-reply（无需回复）”电子邮件地址， 默认为 ID+username@users.noreply.github.com ）。

.. image:: https://github.com/yangzy1202/Docs-as-Code/blob/master/tutorial-drafts/images/github-desktop-config.png

然后，同学们会看到 GitHub Desktop 的主界面，让我们从**Create a tutorial repository and clone it**开始快速创建我们的第一个Git仓库！

.. image:: https://github.com/yangzy1202/Docs-as-Code/blob/master/tutorial-drafts/images/github-desktop-create-repo.png

Tip：为减少设置开发环境的时间，建议同学们安装 Visual Studio Code 并将其作为 GitHub Desktop 的默认文本编辑器，并将 GitHub Desktop 的默认 Shell 设置为 PowerShell（或 Git Bash，如果同学们已经安装了Git SCM的话），这些可以在 File-Options-Advanced 中找到，本教程会在后面提到两者的使用。
.. image:: https://github.com/yangzy1202/Docs-as-Code/blob/master/tutorial-drafts/images/github-desktop-vscode.png
.. image:: https://github.com/yangzy1202/Docs-as-Code/blob/master/tutorial-drafts/images/github-desktop-options.png


Github 协作开发
---------------
Github 支持多人协作开发的三种模式：

- fork
此种模式下，开发者 fork 自己生成一个独立的分支，跟主分支完全独立，pull 代码后，项目维护者可根据代码质量决定是否 merge 代码。如果同学们想参与开发某个开源项目，可以将这个项目 fork 到自己的仓库中，此操作会创建一份完全相同的项目到自己的仓库中，也可以 clone 到本地，参与开发，但是对 fork 的项目进行的修改内容并不会影响原本的仓库。如果同学们在原仓库的基础上有修改，可以向原仓库提出 pull request 申请，请求 merge，原仓库的管理者会收到系统的消息提示，决定是否将修改合并到原仓库。

值得注意的是，fork 这种协作方式下，每个成员在开发时都是独立的，可以自行对项目的某一部分进行修改，之后请求合并，但将分支合并的时候，比较容易出现冲突，导致 merge 无法自动完成，最终必须手动处理这些冲突。所以同学们在 fork 模式下进行协作开发的时候，分工一定要明确，不能让两个人都对一个文件进行操作。

*具体操作*

进入 Repo，点击仓库右上角的 fork，还可以将项目克隆到本地。
.. image:: https://github.com/yangzy1202/Docs-as-Code/blob/master/tutorial-drafts/images/github-fork.jpg

- collaborator
此种模式下，代码仓库的所有者可以为单个仓库增加具备读写权限的合作者。被添加进来的成员就拥有了对该仓库的读写权限，可以将该仓库 clone 到本地进行开发，也同样拥有向该仓库远程提交的权限，但是该仓库不会出现在合作开发者的仓库中。每个合作者都能看到代码库页面访问状态的变化。

本教程的开发即是基于此种模式。

*具体操作* 

进入 Repo，点击 Settings-> Collaborators-> Add collaborator 即可邀请，被邀请者需要在邮箱中进行确认。

.. image:: https://github.com/yangzy1202/Docs-as-Code/blob/master/tutorial-drafts/images/github-settings.jpg

在设置中通过邮箱或用户名添加合作者

.. image:: https://github.com/yangzy1202/Docs-as-Code/blob/master/tutorial-drafts/images/github-collaborators.jpg

- organization
此种模式下，组织的所有者可以针对不同的代码仓库建立不同访问权限的团队。如果需要为监管的几个团队设置不同的权限级别，或者为不同的代码仓库增加不同的成员，希望项目既有 collaborator 同时又可以限制他们的读写权利，尤其是限制其“写”的权利，可利用 organization 来为成员赋予不同等级的权力。

*具体操作*



开发者在这三种模式下的权限依次为 fork < organization < collaborator

Github Pages
----------------
