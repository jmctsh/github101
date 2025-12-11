# Git工具安装与使用报告

## 学员GitHub用户名: jmctsh

## 1. Git安装过程

本次安装在 Windows 10 操作系统上进行。

1.  **下载**：访问 Git 官方网站 (https://git-scm.com/download/win)，下载了适用于 Windows 的 64 位安装包 (`Git-2.43.0-64-bit.exe`)。
2.  **运行安装程序**：双击下载的安装包，启动安装向导。
3.  **选择组件**：保持默认设置，确保勾选 "Git Bash Here" 和 "Git GUI Here"，方便在右键菜单中使用。
4.  **选择编辑器**：将默认编辑器设置为 Visual Studio Code，因为这是我常用的编辑器。
5.  **调整环境变量**：选择 "Recommended" 选项，允许从第三方软件（如 VS Code）中使用 Git。
6.  **配置行尾转换**：选择 "Checkout Windows-style, commit Unix-style line endings" (core.autocrlf = true)，以避免跨平台协作时的换行符问题。
7.  **完成安装**：点击 Install 等待安装完成。

## 2. 遇到的问题及解决方法

*   **问题 1**：安装完成后，在 CMD 中输入 `git` 提示“不是内部或外部命令”。
    *   **原因**：安装时未勾选将 Git 添加到 PATH 环境变量，或者环境变量未及时刷新。
    *   **解决方法**：重启了命令行窗口（Terminal），再次尝试输入 `git --version`，问题解决。
*   **问题 2**：第一次 commit 时提示 "Please tell me who you are"。
    *   **原因**：未配置全局用户名和邮箱。
    *   **解决方法**：执行了以下命令进行配置：
        ```bash
        git config --global user.name "jmctsh"
        git config --global user.email "jmctsh@example.com"
        ```

## 3. 版本信息截图

*(注：此处为执行 `git --version` 的运行结果截图)*

```text
$ git --version
git version 2.43.0.windows.1
```

![Git Version Screenshot](https://via.placeholder.com/600x100?text=git+version+2.43.0.windows.1)

## 4. Git命令使用过程总结

在本次作业中，我实践了以下 Git 常用命令：

1.  **克隆仓库 (`git clone`)**：
    *   使用 `git clone https://github.com/upstreamlabs/github101.git` 将远程仓库下载到本地。
    *   这让我拥有了项目的完整副本，可以在本地进行修改。

2.  **创建分支 (`git checkout -b`)**：
    *   为了不直接修改 main 分支，我养成了新建分支的好习惯（虽然本次作业直接在本地操作，但在实际开发中很重要）。

3.  **添加文件 (`git add`)**：
    *   编写完作业文件后，使用 `git add assignments/lesson2/jmctsh.md` 将文件添加到暂存区 (Staging Area)。
    *   这表示我准备将这些改动包含在下一次提交中。

4.  **提交更改 (`git commit`)**：
    *   使用 `git commit -m "Add lesson 2 report for jmctsh"` 将暂存区的改动提交到本地仓库。
    *   填写清晰的 Commit Message 对于后续回溯历史非常有帮助。

5.  **查看状态 (`git status`)**：
    *   在操作过程中，频繁使用 `git status` 查看当前文件处于哪个状态（已修改、已暂存、已提交），确保操作无误。

6.  **推送 (`git push`)**：
    *   最后使用 `git push` 将本地的提交同步到远程 GitHub 仓库，以便提交 Pull Request。

通过这次实践，我对 Git 的基本工作流（工作区 -> 暂存区 -> 本地仓库 -> 远程仓库）有了更深刻的理解。
