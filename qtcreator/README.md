# QtCreator相关配置
## 主题配置
### 1. 黑色主题
`工具->选项->环境` 选择dark主题

### 2. 配色方案
`工具->选项->文本编辑器` 选择适合的配色方案

### 3. 自定义配色
在目录 `Qt5.8.0\Tools\QtCreator\share\qtcreator\styles` 下，有若干xml配置文件，自定义一个xml文件，修改文件内容，即可实现自定义配色方案。

这里有两个我自定义的配色方案，目前使用monokai-2，可以修改对应项的前景色、背景色、是否斜体等等。
> monokai-2.xml

> monokai-3.xml

## 其他设置
### 1. 更改默认构建目录
使用QtCreator编译工程时，默认会生成一个与工程目录同级的构建目录（build directory），而且目录名贼长，为了使目录结构简化，就要修改默认的构建目录选项。

`工具->选项->构建和运行->Default build directory`

**默认的构建目录**为

`../build-%{CurrentProject:Name}-%{CurrentKit:FileSystemName}-%{CurrentBuild:Name}`

其中，各部分元素的意义如下

`../` 当前目录的父目录，这部分用来指定构建目录处在什么位置，其中当前目录是指当前工程目录下

`build-` 固定不变的字符，在目录名中原样显示

`%{CurrentProject:Name}` 变量值，即当前的工程名

`-` 固定不变的字符，在目录名中原样显示

`%{CurrentKit:FileSystemName}` 变量值，当前构建套件名，比如使用的是桌面版的MinGW，Qt版本为5.8，则为`Desktop_Qt_5_8_0_MinGW_32bit`

`-` 固定不变的字符，在目录名中原样显示

`%{CurrentBuild:Name}` 变量值，当前构建类型，比如是Debug还是Release

**修改后的构建目录**为

`./%{CurrentBuild:Name}`

此时Qt项目在编译之后的目录中的tree结构为

```
test
│  test.pro
│  test.pro.user
│  main.cpp
│
└─Debug
    │  .qmake.stash
    │  Makefile
    │  Makefile.Debug
    │  Makefile.Release
    │
    ├─debug
    │      test.exe
    │      main.o
    │
    └─release
```
