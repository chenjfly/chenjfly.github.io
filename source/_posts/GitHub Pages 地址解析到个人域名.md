title: GitHub Pages 地址解析到个人域名
data: 2018/4/15 10:00:00
categories: 笔记

---
在前一篇博客中，已经完成了整个博客从无到有的搭建，有了自己的博客[https://chenjfly.github.io](https://chenjfly.github.io),但这还不是太完美。这是 GitHub Pages 自动给我们分配的域名，域名太长，也无法实现个性化的需求。下面我们要做的就是注册一个自己心仪的域名，并且把 GitHub Pages 地址解析到我们的个人域名上。
![](http://ognrba5g5.bkt.clouddn.com/18-4-15/55282211.jpg)	
<!--more-->

## 购买域名
个人域名当然是不会有人送给你的，所以先到各大域名注册网站上去申购一个域名，现在国内的域名注册机构注册域名貌似不管是企业还是个人，都需要进行备案，所以如果闲麻烦可以到国外的注册机构进行购买。我个人是在阿里云旗下万网申购的域名，个人备案在之前弄博客的时候就已经备案过，时间已经很久远了，但我记得也并不是很麻烦。这里提供一个阿里云域名购买的连接，方便进行跳转。[阿里云万网:www.net.cn](https://wanwang.aliyun.com)

这个就是我所购买的域名~哈哈，4 块钱 1 年，感觉很是划算。具体的注册购买流程，按照一步一步提示来就行了，相信都到买域名这一步了，不会就太捞了。

![](http://ognrba5g5.bkt.clouddn.com/18-4-15/67081653.jpg)

## 域名解析
- 配置 CNAME 文件

在 \hexo\source 文件夹下创建文件 CNAME，内容就是自己的域名，例如我的域名是：flyblog.top,然后运行`hexo g -d`进行提交。

- 设置域名解析
进入域名解析设置，设置相应的域名解析。

![](http://ognrba5g5.bkt.clouddn.com/18-4-15/56444144.jpg)

1. 记录类型选择 `CNAME`
2. 主机记录填 `www`
3. 解析线路选择`默认`
4. 记录值填 `yourname.github.io`
5. TTL 值为 `10 分钟`

![](http://ognrba5g5.bkt.clouddn.com/18-4-15/70380684.jpg)

1. 再添加一个解析，记录类型 `A`
2. 主机记录填 `@`
3. 解析线路选择`默认`
4. 记录值填个人 GitHub Pages 的 `ip 地址`（可以在 cmd 中 ping 一下）
5. TTL 值为 `10 分钟`

![](http://ognrba5g5.bkt.clouddn.com/18-4-15/83294760.jpg)

这时域名解析设置已经完成，在等待 1 分钟左右后，即可通过个人域名来访问博客了！

![](http://ognrba5g5.bkt.clouddn.com/18-4-15/86543355.jpg)
