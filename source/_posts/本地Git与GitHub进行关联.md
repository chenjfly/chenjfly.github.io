title: 本地Git与GitHub进行关联
data: 2018/5/6 22:30:00
categories: 笔记

---
Git 作为 GitHub 所使用的一个工具，如果不把它与 GitHub 账号关联起来，那它的使用价值和体验就会大打折扣。这篇文章主要介绍如何把本地的 Git 与 GitHub 账号进行关联。

![](http://ognrba5g5.bkt.clouddn.com/18-5-6/87922415.jpg)
<!--more-->

## SSH 授权
 GitHUb 上是基于 SSH 进行授权的，SSH 是一种网络协议，用于计算机之间进行远程加密的登陆。所以首先需要为本地的 Git 添加 SSH key 配置。

## 配置SSH key
Windows 主机在安装了 Git 之后，即可在 Git Bash 里输入：

`ssh-keygen -t rsa`

这个命令的意思是执行 ssh-keygen.exe 这个程序，并且指定 SSH key 的秘钥采取 rsa 算法来生成。输入命令后连续输入三个回车即可在本地用户目录下看到一个 .ssh 的文件夹，里面是刚才所生成的秘钥和公钥。

![](http://ognrba5g5.bkt.clouddn.com/18-5-6/99081924.jpg)

接下来要做的是把 id_rsa.pub 的内容添加到 GitHub 上，这样本地的 id_rsa 密钥跟 GitHub 上的 id_rsa.pub 公钥进行配对，就可以进行授权的认证了。

## GitHub 上添加 SSH key
在 GitHub 设置里找到 SSH and GPG keys，就可以看到在右边有个添加新 SSH key 的地方，点击 New SSH key 进行配置。

![](http://ognrba5g5.bkt.clouddn.com/18-5-6/99027939.jpg)

在 Title 里随便命一个名标识这一个 key 就行，如果你有多台电脑，多可以进行授权。下方的 Key 就把之前生成在 .ssh 文件夹里的 id_rsa.pub 文件里的内容复制出来。完成后点击 Add SSH Key即可。

![](http://ognrba5g5.bkt.clouddn.com/18-5-6/20225077.jpg)

## 测试关联是否成功
我们要做的工作都已经完成了，最后一步就是验证是否已经成功把本地的 Git 与 GitHub 进行了关联。验证方法也很简单，在 Git Bash 下输入

`ssh -T git@github.com`

如果看到下面这个提示，就说明已经关联成功。可以愉快的和 GitHub 玩耍了。

![](http://ognrba5g5.bkt.clouddn.com/18-5-6/79334544.jpg)

