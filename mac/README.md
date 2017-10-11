# 基本设置

## Xcode Command Line Tools

Xcode是Apple的一个开发工具和库集合，Xcode Command Line Tools是Xcode的一部分。安装很多Unix软件都需要使用GCC编译器等开发工具，Xcode Command Line Tools就包含这些工具。

检查Xcode Command Line Tools是否已经安装：

    $ xcode-select -p
    /Applications/Xcode.app/Contents/Developer

没有安装的话，打开一个终端窗口(Terminal)，运行命令：

    xcode-select --install

然后点击"Install"按钮，安装Xcode的命令行工具

## HomeBrew

[HomeBrew配置](https://github.com/uniqueyehu/config-files/blob/master/mac/homebrew.md)

## iTerm2 + oh-my-zsh

[iTerm2配置](https://github.com/uniqueyehu/config-files/blob/master/mac/iterm2.md)