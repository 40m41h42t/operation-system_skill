

# [如何在 GitHub.com 上删除某个 Repository 中的某个文件夹？](https://www.zhihu.com/question/20418177)

步骤：（以删除.idea文件夹为例）

```bash
git rm -r --cached .idea  #--cached不会把本地的.idea删除
git commit -m 'delete .idea dir'
git push -u origin master
```

[git 修改用户名以及提交邮箱](https://blog.csdn.net/helinlin007/article/details/52266169)

想搞一个没人会关注的Github，又想看自己的contribution情况。然而电脑里还是上一个账户的settings，所以要改一下咯

修改当前 project 的内容：

```bash
git config user.name 你的目标用户名
git config user.email 你的目标邮箱名
```

修改全局内容：

```bash
git config --global user.name 你的目标用户名
git config --global user.email 你的目标邮箱名
```

# [How to solve the GitHub error fatal: HttpRequestException encountered](https://codeshare.co.uk/blog/how-to-solve-the-github-error-fatal-httprequestexception-encountered/)

大概意思就是GitHub用了TLS1.2，然而本地git的时候还想用TLS1.0就会导致这个错误。

解决方案：安装GCMW，重启；如果还有问题，安装最新的git。

别说了我重启去了~

PS：没重启测试成功。

# 重命名github仓库

开始是按照[这里](http://gohom.win/2015/12/17/git-rename-repo/)配置的，之后出现了

```bash
fatal: Could not read from remote repository.
```

这么一个错误。stackoverflow上翻到了[解决办法](https://stackoverflow.com/questions/13509293/git-fatal-could-not-read-from-remote-repository)

最终整理如下：

```bash
git remote set-url origin https://github.com/username/newrepo.git
```

另外，

```bash
git remote -v
```

可以列出所有远程仓库信息，包括网址。

# 下载GitHub上某个文件夹/文件

[如何从 GitHub 上下载单个文件夹？](https://www.zhihu.com/question/25369412)

- [DownGit|Create GitHub Resource Download Link](https://minhaskamal.github.io/DownGit/#/home)

- - 实测效果：由于网络质量问题，速度并不是很快，但是至少可以用。

```bash
svn checkout https://github.com/Mooophy/Cpp-Primer/trunk/ch03
```

# git 设置代理

```bash
git config --global https.proxy http://127.0.0.1:1080
git config --global https.proxy https://127.0.0.1:1080
git config --global --unset http.proxy
git config --global --unset https.proxy
```

# 查看 git 设置

```
查看仓库级的 config，命令：git config –local -l
查看全局级的 config，命令：git config –global -l
查看系统级的 config，命令：git config –system -l
查看当前生效的配置，  命令：git config -l
```

