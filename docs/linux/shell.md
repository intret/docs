## shebang

为了让.sh文件可执行，需要把下面的代码添加到.sh文件到第一行，然后给.sh文件添加可执行属性：`chmod +x myshell.sh`。

```shell
#!/usr/bin/env bash
```

## shell

### oh-my-zsh

oh-my-zsh 让终端更性感：https://ohmyz.sh/

#### 安装方法

通过curl命令安装：

```shell
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

或者通过wget命令安装：

```shell
sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

## 命令行

### cheat 命令

查看命令行常见用法的命令行工具。

不记得怎么把curl下载的文件另存为一个新文件？输入：cheat curl

不记得怎么使用tar解压文件？输入：cheat tar

> cheat on GitHub
>
> [cheat/cheat: cheat allows you to create and view interactive cheatsheets on the command-line. It was designed to help remind *nix system administrators of options for commands that they use frequently, but not frequently enough to remember.](https://github.com/cheat/cheat)

