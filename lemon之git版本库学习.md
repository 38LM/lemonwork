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



## 三、git和github链接

1、当github上的文件更新时，怎么更新到本地仓库中

1.1、查看是否链接成功：

```
$ ssh -T git@github.com
```

显示表示成功

![image-20210910155236750](C:\Users\11304\AppData\Roaming\Typora\typora-user-images\image-20210910155236750.png)



1.2、配置当前fork的仓库的原仓库地址

```
git remote add upstream (原仓库github地址)  git@github.com:38LM/lemonwork.git
```



1.3、查看当前仓库的远程仓库地址和原仓库地址

```
git remote -v
```



1.4、获取原仓库的更新。使用fetch更新，fetch后会被存储在一个本地分支upstream/master上

```
git fetch upstream
```



1.5、合并到本地分支。切换到本地master分支，合并upstream/master分支。

```
git merge upstream/master
```



1.6、这时候使用git log就能看到原仓库的更新

```
git log
```



2、当本地仓库中被修改时，将本地仓库通过git更新到github的方法

```
git push origin master
```



## 四、git基本操作

1、删除仓库中的文件

```
git rm 文件名（test.cpp）
```

2、删除仓库中的文件夹

```
git rm -r 文件夹/
```

如果是空的文件夹，使用

```
git clean -fd untracked 文件夹
```

3、

## 五、linux基本操作命令

1、建立文件

```
$ touch 文件名（test.cpp） 
```

2、建立文件夹

```
$ mkdir 文件夹（test）
```

3、删除文件

```
$ rm 文件名（test.cpp）
```

4、删除文件夹

```
$ rm -r 文件夹
```

