---
title: Git学习笔记
showcopyright: true
showdonate: true
date: 2017-11-07 15:42:48
type:
top:
comments:
categories: [技术, Git]
tags: [Git, Git学习]
---

### 学习Git需要清楚的几个术语
![](http://www.yiibai.com/uploads/images/201707/1207/683090701_88630.jpg)

**Workspace**：工作区

**Index/Stage**：暂存区，也叫索引
<!--more-->

**Repository**：仓库区（或本地仓库），也存储库

**Remote**：远程仓库

**工作区**: 通过git init创建的代码库的所有文件但是不包括.git文件(版本库)

**暂存区**: 通过git add ./*/*Xxx/Xxxx* 添加的修改,都是进入到暂存区了,肉眼不可见 通过 git status 可以看到修改的状态。

### 三种状态

Git 有三种状态，你的文件可能处于其中之一：已提交(committed)、已修改(modified)和已暂存(staged)。 已提交表示数据已经安全的保存在本地数据库中。 已修改表示修改了文件，但还没保存到数据库中。 已暂存表示对一个已修改文件的当前版本做了标记，使之包含在下次提交的快照中。

由此引入 Git 项目的三个工作区域的概念：Git 仓库、工作目录以及暂存区域。工作目录、暂存区域以及 Git 仓库如下图所示
![](http://www.yiibai.com/uploads/images/201707/0607/744160702_48164.png)

Git 仓库目录是 Git 用来保存项目的元数据和对象数据库的地方。 这是 Git 中最重要的部分，从其它计算机克隆仓库时，拷贝的就是这里的数据。

工作目录是对项目的某个版本独立提取出来的内容。 这些从 Git 仓库的压缩数据库中提取出来的文件，放在磁盘上供你使用或修改。

暂存区域是一个文件，保存了下次将提交的文件列表信息，一般在 Git 仓库目录中。 有时候也被称作‘索引’，不过一般说法还是叫暂存区域。

### 用户信息

当安装完 Git 应该做的第一件事就是设置用户名称与邮件地址。这样做很重要，因为每一个 Git 的提交都会使用这些信息，并且它会写入到每一次提交中，不可更改：
```
$ git config --global user.name "maxsu"
$ git config --global user.email maxsu@yiibai.com
```

### 设置文本编辑器
```
$ git config --global core.editor atom
```

### 检查配置信息
如果想要检查你的配置，可以使用 `git config --list` 命令来列出所有 Git 当时能找到的配置。

### 常用基础命令
`git add ` 指定跟踪文件，然后执行 `git commit` 提交
```
$ git add hello.py
$ git commit -m '修改说明'
```
要查看哪些文件处于什么状态，可以用 `git status` 命令。

#### 忽略文件

总会有些文件无需纳入 Git 的管理，也不希望它们总出现在未跟踪文件列表。我们可以创建一个名为 `.gitignore` 的文件，列出要忽略的文件模式。

`.gitignore` 的格式规范如下：

- 所有空行或者以 `＃` 开头的行都会被 Git 忽略。
- 可以使用标准的 `glob` 模式匹配。
- 匹配模式可以以(`/`)开头防止递归。
- 匹配模式可以以(`/`)结尾指定目录。
- 要忽略指定模式以外的文件或目录，可以在模式前加上惊叹号(`!`)取反。

所谓的 `glob` 模式是指 `shell` 所使用的简化了的正则表达式。

> 提示：GitHub 有一个十分详细的针对数十种项目及编程语言的 .gitignore 文件列表，你可以在 http://github.com/github/gitignore 找到它。

#### 查看已暂存和未暂存的修改

如果 `git status` 命令的输出对于你来说过于模糊，你想知道具体修改了什么地方，可以用 `git diff` 命令。

请注意，`git diff` 本身只显示尚未暂存的改动，而不是自上次提交以来所做的所有改动。 所以有时候你一下子暂存了所有更新过的文件后，运行 git diff 后却什么也没有，就是这个原因。

然后用 `git diff --cached` 查看已经暂存起来的变化：(`--staged` 和 `--cached` 是同义词)

#### 跳过使用暂存区域

Git 提供了一个跳过使用暂存区域的方式， 只要在提交的时候，给 `git commit` 加上 `-a` 选项，Git 就会自动把所有已经跟踪过的文件暂存起来一并提交，从而跳过 `git add` 步骤。

#### 移除文件

 `git rm` 移除已跟踪文件（同时会删除工作目录中的文件）。
 如果删除之前修改过并且已经放到暂存区域的话，则必须要用强制删除选项 `-f`(注：即 `force` 的首字母)。 这是一种安全特性，用于防止误删还没有添加到快照的数据，这样的数据不能被 Git 恢复。

另外一种情况是，想让文件保留在磁盘，但是并不想让 Git 继续跟踪。 当你忘记添加 `.gitignore` 文件，不小心把一个很大的日志文件或一堆 `.a` 这样的编译生成文件添加到暂存区时，可以使用 `--cached` 选项：
```
$ git rm --cached mytext.txt
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        deleted:    mytext.txt
```
`git rm` 命令后面可以列出文件或者目录的名字，也可以使用 glob 模式。

#### 移动文件

```
$ git mv file_from file_to
```

#### 查看提交历史

默认不用任何参数的话，`git log` 会按提交时间列出所有的更新，最近的更新排在最上面。

显示最近两次提交内容差异：
```
$ git log -p -2
```
每次提交的简略的统计信息：
```
$ git log --stat
```
另外一个常用的选项是 `--pretty` 。 这个选项可以指定使用不同于默认格式的方式展示提交历史。 这个选项有一些内建的子选项供你使用。 比如用 `oneline` 将每个提交放在一行显示，查看的提交数很大时非常有用。 另外还有 `short` ，`full` 和 `fuller` 可以用，展示的信息或多或少有些不同。
```
$ git log --pretty=oneline
ca82a6dff817ec66f44342007202690a93763949 changed the version number
085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7 removed unnecessary test
a11bef06a3f659402fe7563abf99ad00de2209e6 first commit

$ git log --pretty=format:"%h - %an, %ar : %s"
ca82a6d - Scott Chacon, 6 years ago : changed the version number
085bb3b - Scott Chacon, 6 years ago : removed unnecessary test
a11bef0 - Scott Chacon, 6 years ago : first commit
```

#### 撤消操作

有时候我们提交完了才发现漏掉了几个文件没有添加，或者提交信息写错了，可以运行带有 `--amend` 选项的提交命令尝试重新提交：
```
$ git commit --amend
```
这个命令会将暂存区中的文件提交。 如果自上次提交以来你还未做任何修改(例如，在上次提交后马上执行了此命令)，那么快照会保持不变，而你所修改的只是提交信息。

例如，提交后发现忘记了暂存某些需要的修改，可以像下面这样操作：
```
$ git commit -m 'initial commit'
$ git add forgotten_file
$ git commit --amend
```
最终你只会有一个提交 - 第二次提交将代替第一次提交的结果。

#### 取消暂存的文件

`reset` 后面不跟参数就是取消所有。
```
git reset HEAD mytext.txt
```

#### 撤消对文件的修改

```
git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   123

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   123
```
按照说明输入命令撤销
```
git checkout -- 123
```

#### 隐藏(Stash)操作

要切换任务做其他的，但不想提交一直在做的工作; 那么可以把当前工作的改变隐藏起来。 要将一个新的存根推到堆栈上，运行 `git stash` 命令。通过使用 `git stash list` 命令来查看已存在更改的列表。执行 `git stash pop` 命令即可从堆栈中删除更改并将其放置在当前工作目录中。

**查看远程仓库**

如果想查看你已经配置的远程仓库服务器，可以运行 `git remote` 命令。 它会列出你指定的每一个远程服务器的简写。

指定选项 `-v`，会显示需要读写远程仓库使用的 Git 保存的简写与其对应的 URL。

#### 添加远程仓库

```
 git remote add <shortname> <url>
```

#### 从远程仓库中抓取与拉取
```
git fetch [remote-name]
```
这个命令会访问远程仓库，从中拉取所有还没有的数据。执行完成后，将会拥有那个远程仓库中所有分支的引用，可以随时合并或查看。

如果使用 `clone` 命令克隆了一个仓库，命令会自动将其添加为远程仓库并默认以 “origin” 为简写。 所以，`git fetch origin` 会抓取克隆(或上一次抓取)后新推送的所有工作。 必须注意 `git fetch` 命令会将数据拉取到本地仓库, 它并不会自动合并或修改当前的工作。
如果你有一个分支设置为跟踪一个远程分支，可以使用 `git pull` 命令来自动的抓取然后合并远程分支到当前分支。 这对你来说可能是一个更简单或更舒服的工作流程；默认情况下，`git clone` 命令会自动设置本地 master 分支跟踪克隆的远程仓库的 `master` 分支(或不管是什么名字的默认分支)。 运行 `git pull` 通常会从最初克隆的服务器上抓取数据并自动尝试合并到当前所在的分支。

#### 推送到远程仓库

推送命令： `git push [remote-name] [branch-name]` 。
```
$ git push origin master
```

#### 查看远程仓库

查看远程仓库的更多信息：  `remote show [remote-name]` 。
```
$ git remote show origin
```

#### 远程仓库的移除与重命名

```
$ git remote rename old new
```

更多详细命令请参考 http://www.yiibai.com/git/
