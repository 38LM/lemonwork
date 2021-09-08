# lemon之git版本库学习

对git学习中可能会混杂着一些linux的命令。

## 一、git安装（ubuntu16）

1、输入 

```
$ sudo apt-get install git
```

注意：此时可能出现如下错误情况：

```
E: Could not get lock /var/lib/dpkg/lock - open (11: Resource temporarily unavailable)
E: Unable to lock the administration directory (/var/lib/dpkg/), is another process using it?
```

解决方案：即把/var/lib/dpkg/目录下的lock文件删除即可

```
$ cd /var/lib/dpkg

$ sudo rm -rf lock
```

删除之后再输入安装命令即可（sudo apt-get install git）

2、查看是否安装成功

```
$ git --version
```

当出现git版本时即表示git安装成功：

```
git version 2.7.4（这是我安装成功之后出现的git版本号）
```

## 二、git基本操作学习

我们已经把git安装成功了，接下来需要学习git的一些基本操作。

### 1、git中添加用户名和用户邮箱

```
$ git config --global user.name "lemon(这里填写用户名)"
$ git config --global user.email "xxxx@qq.com(这里填写用户邮箱)"
```

如果需要修改用户和用户邮箱，直接重复上述操作即可。

如果需要查看当前用户和用户邮箱，执行：

```
$ git config user.name
$ git config user.email
```

### 2、初始化git版本库

（此时在文件目录下会出现.git隐藏文件，使用   'ls -a'   即可查看）

```
$ git init
```

### 3、新建文件夹和文件的方法

这个属于常用命令，可以先了解一下。

```
$ mkdir lemon（文件夹）  *文件夹：不需要后缀名
$ touch lemon.txt (文件名)  *文件：需要后缀名，可以是.txt、.c、.py
```

### 4、查看版本库状态

```
$ git status
```

使用这个命令可以查看目前文件的一些状态，包括：unstaged（待添加，使用add添加）、stage（添加但是未提交，使用commit提交）

### 5、添加文件到版本库中

当我们新建文件时，此时文件的状态是unstaged状态，需要添加到版本库中，变成stage状态:

```
$ git add 文件名
$ git add .(添加全部文件到版本库中)
```

### 6、提交改变

我们已经将文件添加到版本库中了，现在的文件状态是stage状态，需要将文件改变提交到版本库中，使用：

```
$ git commit -m "改变的内容"
```

![2-1-1.png](https://static.mofanpy.com/results/git/2-1-1.png)

整个git的流程图

