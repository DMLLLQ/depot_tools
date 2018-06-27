# depot_tools

这是[Dimole](https://dmlgzs.ga/)创建的<!--，以让国人免番羽土啬来下载depot_tools最新版。--><br>
以下使用说明为机器翻译结果，如有不准请谅解。（其实我校正过的）<br>

＃depot_tools

使用Chromium开发工具。它需要python 2.7。


##工具

最重要的工具是：

- "fetch"：一个"gclient"包装器来检出一个项目。使用`fetch --help`
  更多细节。
- "gclient"：一个元检验工具。认为
  [回购]（https://source.android.com/source/using-repo.html）或[git
  子模块]（https://git-scm.com/docs/git-submodule），只是它支持
  操作系统特定的规则，例如不要签出Windows时只依赖关系
  检查Android。使用"gclient help"获取更多细节和
  [README.gclient.md]（README.gclient.md）。
- "git cl"：与Rietveld或Gerrit交互的代码审查工具。使用"git cl
  帮助"获取更多细节和[README.git-cl.md]（README.git-cl.md）。
- "roll-dep"：提供_dep roll_的gclient依赖关系管理工具，
  将依赖关系更新为更新的修订版本。

有很多git工具包含在内。


##更新

运行"gclient"工具时，"depot_tools"会自动更新。至
禁用自动更新，设置环境变量"DEPOT_TOOLS_UPDATE = 0"。（中国人建议使用）

要手动更新软件包，请在Windows上运行"update_depot_tools.bat"，
或Linux或Mac上的"./update_depot_tools"。

在Windows上，运行`gclient`会安装"git"和"python"。


##贡献

为评论做出贡献改变：

    git new-branch <somename>
    ＃黑客
    git add。
    git commit -a -m "Fixes goat teleporting"
    ＃找到评论者
    git cl owners
    git log - <yourfiles>

    ＃请求审查。
    git cl upload -r reviewer1 @ chromium.org，reviewer2 @ chromium.org --send-mail

    ＃编辑更改描述，如果需要。
    git cl desc

    ＃如果更改被批准，请将其标记为已提交。
    git cl set-commit

    ＃如果变化需要更多工作。
    git rebase-update
    ...
    git cl upload -t "Fixes goat teleporter destination to be Australia"

另请参阅[打开错误]（https://bugs.chromium.org/p/chromium/issues/list?can=2&q=component%3AInfra%3ESDK），
[打开评论]（https://chromium-review.googlesource.com/q/status:open+project:chromium%252Ftools%252Fdepot_tools），
[论坛]（https://groups.google.com/a/chromium.org/forum/#!forum/infra-dev）或
[报告问题]（https://bugs.chromium.org/p/chromium/issues/entry?components=Infra%3ESDK）。

### cpplint.py

要更新cpplint.py，请先在上游提交更改
https://github.com/google/styleguide/tree/gh-pages/cpplint 然后将其复制下来。
