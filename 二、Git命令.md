# 二、Git命令

创建项目

git init

克隆别的地方的项目

git clone

查看仓库状态

git status

## 2\.1  git init

使用该git init命令在当前目录中创建一个新的空存储库。

*我们将看一下\.git目录……不过，这对本课程来说并不重要，所以不要担心记住任何东西，如果你想更深入地了解 Git 是如何工作的，它就在这里。*

以下是目录中每个项目的简要概要\.git：

- __config 文件__\- 存储所有*项目特定*的配置设置。  
来自[Git 书](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration" \t "_blank)：

*Git 在您当前使用的任何存储库的 Git 目录 \(\.git/config\) 的配置文件中查找配置值。这些值特定于该单个存储库。*

例如，假设您设置 Git 的全局配置使用您的个人电子邮件地址。如果您希望您的工作电子邮件用于特定项目而不是您的个人电子邮件，则该更改将添加到此文件中。

- __描述文件__——这个文件只被GitWeb程序使用，所以我们可以忽略它
- __hooks 目录__——这是我们可以放置客户端或服务器端脚本的地方，我们可以使用这些脚本来挂钩 Git 的不同生命周期事件
- __info 目录__\- 包含全局排除文件
- __objects 目录__\- 这个目录将存储我们所做的所有提交
- __refs 目录__\- 该目录包含指向提交的指针（基本上是“分支”和“标签”）

请记住，除了“钩子”目录之外，您不应该乱弄这里的任何内容。“hooks”目录*可*用于挂钩 Git 工作流程的不同部分或事件，但这是一个更高级的主题，我们不会在本课程中涉及。
![image](https://user-images.githubusercontent.com/55593483/225319538-4f1e07e9-06a3-4533-9fd7-5d6cee5e6855.png)


## 2\.2  git clone

创建相同副本

$ git clone <path\-to\-repository\-to\-clone>

实例：

$ git clone https://github\.com/udacity/course\-git\-blog\-project

![image](https://user-images.githubusercontent.com/55593483/225319747-f7aba233-5e15-49f0-90d7-3d1e2075d3e4.png)

重命名：

git clone [https://github\.com/udacity/course\-git\-blog\-project](https://github.com/udacity/course-git-blog-project) xxxxname

所以你已经将项目克隆到你的计算机上，并且你已经cd编辑了它。您不认为是时候在浏览器中查看它的外观了吗？

在您喜欢的浏览器中打开文件index\.html
![image](https://user-images.githubusercontent.com/55593483/225319839-a625d060-eabe-412a-be85-36560b0a2aa3.png)
![image](https://user-images.githubusercontent.com/55593483/225319869-4897df98-2d96-4cb1-9b0b-b552e6df3e36.png)


## 2\.3  git status

$ git status

你怎么知道什么时候应该或不应该运行某些 Git 命令？Git 准备好让我运行命令了吗？如果我运行一个命令但我认为它不起作用怎么办……我怎样才能找到它？所有这些问题的答案就是git status命令！

git status是我们了解 Git 的关键。它会告诉我们 Git 的想法以及 Git 看到的存储库的状态。当您第一次开始时，您应该一直使用该git status命令！严重地。您应该养成在任何其他命令之后运行它的习惯。这将帮助您了解 Git 的工作原理，并帮助您避免（可能）对文件/存储库的状态做出错误的假设。

git status命令将根据文件的状态、工作目录和存储库显示大量信息。不过，您不必太担心这些……只需运行git status，它就会显示您需要知道的信息。

### 2\.3\.1  实例1
![image](https://user-images.githubusercontent.com/55593483/225319907-ab7cd70e-8a0f-4b61-921b-73a6dcf957e7.png)


On branch master

Your branch is up\-to\-date with 'origin/master'\.

nothing to commit, working directory clean

输出告诉我们两件事：

1. On branch master– 这告诉我们 Git 在master分支上。您的条款表上有一个分支的描述，所以这是“主”分支（这是默认分支）。我们将在第 5 课中更多地了解分支
2. Your branch is up\-to\-date with 'origin/master'\.– 因为git clone用于从另一台计算机复制此存储库，这告诉我们我们的项目是否与我们复制的项目同步。我们不会在另一台计算机上处​​理项目，因此可以忽略此行。
3. nothing to commit, working directory clean– 这就是说没有待处理的更改。

将此输出视为“静止状态”（这不是官方描述 \- 这是我喜欢描述的方式！）。这是静止状态，因为没有新文件，没有对文件进行任何更改，暂存区域中没有任何要提交的内容\.\.\.\.\.\.没有任何更改或操作未决，所以我喜欢称它为静止状态状态。

### 2\.3\.2  实例2

返回主目录：cd\\

cd d:/git/udacity\-git\-course/new\-git\-project
![image](https://user-images.githubusercontent.com/55593483/225319969-1a5e47d6-a601-47c7-a0eb-537f612132b8.png)


$ git status

On branch master

Initial commit

nothing to commit \(create/copy files and use "git add" to track\)

完全清楚的是，我还没有在我的项目中做出任何提交。如果您已提交，那么您的输出应该与 course\-git\-blog\-project 项目的输出完全相同。

如果您将其git status与 course\-git\-blog\-project 项目的输出进行比较，您会发现它们非常相似。需要注意的不同之处在于，此输出包含行Initial commit\. 这是最令人困惑的一点，因为这个存储库中实际上还没有任何提交！我们还没有讨论过提交，但是当我们这样做时，我们将能够进行初始提交。

尝试运行命令git log并查看其响应：
![image](https://user-images.githubusercontent.com/55593483/225320037-8a53b940-ccd8-46a5-8550-3ab9093f326c.png)


$ git log

fatal: your current branch 'master' does not have any commits yet

嗯，看起来有点吓人。“致命的”？幸运的是，事实证明这只是意味着 Git 程序正在退出，因为它找不到任何工作要做。Git 告诉我们这好像是一个错误，但它真的不是问题。我们知道我们还没有在这个 repo 中提交任何提交。

从响应中可以清楚地看出没有任何提交！

我们刚刚简单地看了一下这个git status命令。请记住，输出git status将根据文件是否已添加/删除/修改、暂存索引上的内容以及存储库的状态而变化。我们将git status在整个课程中使用该命令，因此请放心运行它！

当您第一次学习 Git*时*，我无法强调始终使用此命令的重要性。该命令将：

- 告诉我们在工作目录中创建但 Git 尚未开始跟踪的新文件
- Git*正在*跟踪的已修改文件
- 在接下来的课程中，我们将学习一大堆其他东西；\-\)
