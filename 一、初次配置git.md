# 初次配置 Git

配置sublime text3为git默认编辑器

在开始使用 Git 之前，你需要配置 Git。在命令行工具中运行以下每行，确保所有选项都已被配置好。

*\# 设置你的 Git 用户名*

git config \-\-global user\.name "<Your\-Full\-Name>"

*\# 设置你的 Git 邮箱*

git config \-\-global user\.email "<your\-email\-address>"

*\# 确保 Git 输出内容带有颜色标记*

git config \-\-global color\.ui auto

*\# 对比显示原始状态*

git config \-\-global merge\.conflictstyle diff3

git config \-\-list

## 一、Git 与代码编辑器

最后一个配置步骤是让 Git 能与你的代码编辑器结合使用。以下是三个最热门的代码编辑器。如果你使用的是其他编辑器，则在 Google 中搜索“修改 Git 默认编辑器为 X 编辑器”（将 X 替换为你的代码编辑器的名称）。

### Atom Editor 设置

git config \-\-global core\.editor "atom \-\-wait"

### Sublime Text 设置

git config \-\-global core\.editor "'C:/Program Files/Sublime Text 2/sublime\_text\.exe' \-n \-w"

### VSCode 设置

git config \-\-global core\.editor "code \-\-wait"
