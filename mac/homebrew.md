# HomeBrew

Homebrew为Mac提供了非常方便的软件安装方式，解决了包的依赖问题，不再需要烦人的sudo，一键式编译，无参数困扰。

由于Homebrew的安装方式可能变化，请到[官方网站](http://brew.sh)查看最新的方法和文档。

安装Homebrew:

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

更新formula和Homebrew:

    brew update

显示已经安装的软件列表:

    brew list

搜索某个软件:

    brew search wget

安装某个软件:

    brew install wget

查看需要升级的软件:

    brew outdated

升级所有的软件:

    brew upgrade

升级某个软件:

    brew upgrade wget

删除某个软件:

    brew uninstall wget --force

查看软件包信息:

    brew info wget

列出软件包的依赖关系:

    brew deps wget

出错以后的处理:

    brew update
    brew doctor

# homebrew-cask

通常Mac下二进制软件是通过App Store安装的，homebrew-cask是一个基于HomeBrew的软件安装程序，使用homebrew-cask可以在命令行下安装软件包，相对Mac App Store，还有一些优势：

* 安装软件体验一致、简洁、优雅、快速
* 对常用软件支持更全面，例如MPlayerX已经宣布不在更新Mac App Store上的版本
* 软件更新速度快。例如Alfred 2.0已经出了很久，但在Mac App Store上还是1.2版本，QQ也是这样的情况
* Mac App Store生态圈远不完善，审核流程过长，限制太多，维护成本过高让很多应用开发者被迫离开。

homebrew-cask和Homebrew的区别：

* Homebrew安装的是源文件包, 下载源文件、编译、安装，比如安装wget, gnupg, mutt等。
* homebrew-cask安装的是二进制软件包, 比如QQ，Chrome，evernote等。homebrew-cask安装软件时自动创建软连接到Application目录，这样在Launchpad中也能查看到安装的软件，方便启动软件。

## 安装homebrew-cask

    brew install caskroom/cask/brew-cask

## 常用命令

列出所有可以被安装的软件：

    brew cask search

查找所有和drop相关的应用:

    brew cask search drop

查看迅雷应用的信息:

    brew cask info thunder

卸载QQ:

    brew cask uninstall qq

查看已安装的软件

    brew cask list

更新Casks:

    brew update && brew upgrade brew-cask

关于软件更新，目前homebrew-cask并不提供命令直接更新已安装的软件，软件更新主要是通过软件自身的更新流程，不过也可以通过以下命令先删除软件，再重新安装。

    brew cask uninstall APP && brew cask install APP


## 一键装机？有了homebrew-cask就可以

    brew cask install alfred
    brew cask install qq
    brew cask install skype
    brew cask install thunder
    brew cask install mplayerx
    brew cask install evernote
    brew cask install skitch
    brew cask install dropbox
    brew cask install google-chrome
    brew cask install mou
    brew cask install iterm2
    brew cask install sublime-text