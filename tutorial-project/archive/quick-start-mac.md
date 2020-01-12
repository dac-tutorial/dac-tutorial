### 1.2 macOS 环境配置

在mac上配置 Sphinx，可以通过 Anaconda，Homebrew，MacPorts 等方式来完成，这里介绍使用 Anaconda，pip，和Homebrew 完成 Sphinx 安装与配置。

这三种相同点在于都是软件包管理工具，不同点在于 Homebrew 是一个通用的软件包管理工具，终端安装的很多软件包都可以用它来安装；Pip 一般安装一些与 Python 环境相关的软件包，conda 功能与 Pip 类似，目的是为了解决对 Python 以外的依赖环境问题，Pip 在任何环境中安装 Python 包; conda 在 conda环境中装任何包。

#### Anaconda 安装与配置

> **注意：**
>
> + 以下步骤不需要同学们预先安装 Python 解释器，而是直接使用 Anaconda 内集成的 Python 解释器；
> + 如果同学们先前已经安装过单独的 Python 解释器（运行 Sphinx 必须预先安装 Python 3.5 及以上版本），可查看下一小节 - 使用 pip 安装 Sphinx [TODO: 添加页内链接]；
> + 更加推荐使用 Anaconda 来完成 Sphinx 开发环境配置，因为 conda 将几乎所有的工具、第三方库都当做 package 对待，甚至包括 python 和 conda 自身，它可以帮助我们方便地管理自己的 Python 开发环境，不仅能够将不同开发项目所依赖的开发环境完全独立开来，还可轻易地复制整个 Python 环境到其他机器上。

1. 打开 [Anaconda 官方下载页](https://www.anaconda.com/distribution/)，下载适合的安装包：

![anaconda-download-mac](images/anaconda-download-mac.jpg)

> **提示：** 如果官网下载速度较慢，可到清华大学开源软件镜像站下载 [Anaconda 安装包](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/)。

2. 下载完成后，运行可执行文件进行安装：

> **注意：** 请在 “Advanced Options” 中将勾选两个可选选项：**这里重装暂时没搞定，待补充**
>
> - **第一个选项** 会将 Anaconda 的安装目录添加至系统环境变量的 path 中，有利于我们之后在 VS Code 中快速激活 conda 环境，以及直接使用 base 环境中已安装的库和脚本，简化操作流程。
>   - 如上图红字所示，Anaconda 官方不建议勾选此选项，而建议使用 Anaconda Prompt (或 Anaconda Powershell Prompt，以下将两者统称为 Anaconda Prompt) 。这是因为勾选此选项会将 Anaconda 的若干目录添加至 path 目录中的最前面；如果用户之前已经安装了其他 Python 解释器，勾选此选项会导致用户直接调用 Python 时优先调用 Anaconda 内置的 Python 解释器，而不是用户单独安装的 Python 解释器，如下图所示：
>   - 假如同学们希望系统默认调用先前单独安装的 Python 解释器，一个较好的解决方法是在勾选此选项并完成安装 Anaconda 后，手动将原 path 中 Python 路径移动到 Anaconda 系列目录的前面，操作方法如下：
>   - 此时，在命令行调用 Python 时会优先调用单独安装的 Python 解释器，只有在激活 conda 环境后才会调用 conda 里的 Python 解释器。（可以看到两个 Python 解释器的版本和版权说明有所区别。）
> - **第二个选项** 可使其他 Python 开发工具（如 VS Code）自动探测到 Anaconda。

3. Anaconda 预装了 Sphinx。完成1-2步 Anaconda 安装后，检查 Sphinx 是否已安装：

点击启动台-其他-终端，输入`conda list`，回车：

此指令会列出当前 conda 环境 (base) 下所有已安装的包，正常情况下可以看到若干以 Sphinx 开头的包：

![conda-list-mac](images/conda-list-mac.jpg)

![conda-list-sphinx-mac](images/conda-list-sphinx-mac.png)

4. *（可选）* Sphinx 预装在 Anaconda 的默认环境下，同学们可以进一步通过 Anaconda Navigator 中检查 Sphinx 包配置情况，安装更多的包。

> 提示 ：Anaconda 通常数月才更新一次，但其内部包含的包通常具有更快的更新频次，可使用 Anaconda 的包管理器对包进行单独更新。这里可通过 Anaconda Prompt 输入命令行操作，也可以通过 Anaconda Navigator 进行可视化操作，相对上手更快。

点击启动台 - Anaconda Navigator，左侧菜单选择 Environments，检索框输入 Sphinx ，得到以下列表：

进一步勾选，点击右下角 Apply 进行安装。

![conda-navigator-mac](images/conda-navigator-mac.jpg)



#### Pip 安装与配置

1. 使用 Pip 配置 Sphinx 也是方便快捷的方式。如果同学们先前安装过单独的 Python 解释器（运行 Sphinx 必须预先安装 Python 3.5 及以上版本），可直接使用第4步中的命令行安装 Sphinx。

   > 提示：如果不确定自己是安装过，可以在终端输入`pip`进行检测。如果出现`-bash: /usr/local/bin/pip: No such file or directory` 提示说明，则尚未安装 Pip，需要进行第2-3步。

2. 终端输入`sudo easy_install pip`，输入 mac 密码，进入安装：

![pip-install-mac](images/pip-install-mac.jpg)

3. 最终显示`Finished processing dependencies for pip`，Pip 配置完成。可以通过`pip --version` 查看 Pip 版本。

![pip-complete-mac](images/pip-complete-mac.jpg)4. 终端运行`pip install sphinx`，完成安装。

![](images/pip-sphinx-mac.jpg)

5. 完成安装后，可以检查 Sphinx 配置情况：

终端输入`pip list`，回车，正常情况下可以看到若干以 Sphinx 开头的包：

![pip-list-mac](images/pip-list-mac.jpg)

![pip-check-mac](images/pip-check-mac.jpg)



#### Homebrew 安装与配置

Homebrew 可以视为套件管理器。它是一款 Mac OS 平台下的软件包管理工具，拥有安装、卸载、更新、查看、搜索等很多实用的功能，不需要关注各种依赖和文件路径的情况。配置好 Homebrew 后，安装包、补充缺失的包比较比较便捷。

1. Homebrew 依赖于 Xcode Command Line Tools，所以会自动先安装 Xcode Command Line Tools；如果有报错，也可以用命令手动安装：`xcode-select --install`。

![homebrew-xcode-mac](images/homebrew-xcode-mac.jpg)

2. 前往 [homebrew 官网](https://brew.sh)，复制首页代码行到终端执行。

![homebrew-website-mac](images/homebrew-website-mac.jpg)

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

![homebrew-install-mac](images/homebrew-install-mac.jpg)

中间需要输入一次 mac 密码：

![homebrew-password-mac](images/homebrew-password-mac.jpg)

3. 出现`Installation successful!`的提示即为 Homebrew 配置完成。

![homebrew-complete-mac](images/homebrew-complete-mac.jpg)

4. 完成 Homebrew 配置后，终端输入`brew install sphinx-doc`，安装 Sphinx 。

![homebrew-sphinx-mac](images/homebrew-sphinx-mac.jpg)

5. 完成安装后，可以检查 Sphinx 配置情况：

终端输入`brew list`，回车，正常情况下可以看到 Sphinx 的包：

![homebrew-list-mac](images/homebrew-list-mac.jpg)
