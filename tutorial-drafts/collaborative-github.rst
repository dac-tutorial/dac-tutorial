Sphinx多人协作开发（Github）
=========
速识Github
--------------
**Github** 是一个基于 **Git** （一个开源的分布式版本控制系统）的版本控制和协作的代码托管平台，因为只支持 git 作为唯一的版本库格式进行托管，因此得名 Github。使用 Github 只需要利用邮箱注册账户，访问 https://github.com 或下载 Github Desktop 既可。将 Github 作为一个协作开发工具，能够使团队工作更有效率，具有更高的生产力。

Github 使用手册
-----------
Github 协作开发
---------------
Github 支持多人协作开发的三种模式：

- fork
此种模式下，开发者 fork 自己生成一个独立的分支，跟主分支完全独立，pull代码后，项目维护者可根据代码质量决定是否 merge 代码。如果同学们想参与开发某个开源项目，可以将这个项目Fork到自己的仓库中，这样该项目就会创建一份镜像到自己的仓库中，可以clone到本地，参与开发，但是修改的内容并不会影响它原本的仓库。如果同学们在原仓库的基础上有修改，可以向原仓库提出pull request申请，请求merge，原仓库的管理者就会收到消息提示，决定是否合并到原仓库中。

- collaborator
此种模式下，代码仓库的所有者可以为单个仓库增加具备读写权限的合作者。被添加进来的成员就拥有了对该仓库的读写权限，可以将该仓库 clone 到本地进行开发，也同样拥有向该仓库远程提交的权限，但是该仓库不会出现在合作开发者的仓库中。每个合作者都能看到代码库页面访问状态的变化。

*具体操作* 

进入 Repo，点击 Settings-> Collaborators-> Add collaborator 即可邀请，被邀请者需要在邮箱中进行确认。

https://github.com/yangzy1202/Docs-as-Code/blob/master/tutorial-drafts/images/github-settings.jpg

https://github.com/yangzy1202/Docs-as-Code/blob/master/tutorial-drafts/images/github-collaborators.jpg

- organization
此种模式下，组织的所有者可以针对不同的代码仓库建立不同访问权限的团队。如果你需要为你监管的几个团队设置不同的权限级别，或者为不同的代码仓库增加不同的成员，希望项目既有 collaborator 同时又可以限制他们的读写权利，尤其是限制其“写”的权利，可利用 organization 来为成员赋予不同等级的权力。

开发者在这三种模式下的权限依次为 fork < organization < collaborator

Github Pages
----------------
