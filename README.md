# Hexo and Github

**github pages** + **Hexo**，重点是他们两个怎么产生关系的，这里只是纯实践操作，原理去百度上其他文章看，
我希望你有一定基础再来看下面的文章。

### Hexo

网上很多，总结一下无非（我是windows）：

1. 下载nodejs --> 安装
2. 安装Hexo --> 生成一个Hexo项目 
3. 下载一款你觉得炫酷的主题，放到themes里 --> 配置“根目录”下的_config.yml里，将主题换成你下载的

### github pages

这个网上也很容易百度到（有人说做个人网站需要新建一个***分支，我反正实在master里弄的）

1. 创建github工程（注意工程名）（这一步其实就是该页面，我这个工程） 
2. 然后没然后了

## 重点来了，如何关联？

(这里有两种方法上传文章，一种使用deploy，这个需要SSH，我没整明白，我采用第二种，手动)

其实说白了，github pages我们就理解成是一个仓库，它存的东西，其实

就是hexo项目里的一个文件夹，哪个呢？ **public**，这个只有在你generate后才会生成（貌似是把md变成了html）

你不妨把你生成的public文件夹打开，对比一下，是不是和我的这个工程里面的文件很像？

1. 文章都是放在source/_post里的md文件
2. 当我们写完文章后，使用hexo g(即 hexo generate的简写)，此时public里的文件就更新了
3. 把public里的内容，通过git commit、push到我们的github工程里(就是本工程)，搞定

## 绑定个人域名

要执行这一步，首先确保你上面都over了，咋知道？访问下yourName.github.io，看看内容对不，至少不能是404吧。OK，next

1. 用命令行ping一下你的github pages，即  ping yourName,github.io（以此来获得其IP地址）
2. 把你自己购买的域名，解析，填上刚刚获得的IP地址，然后耐心等待即可
3. 很多伙计都说域名解析时：“添加两条记录f1g1ns1.dnspod.net和f1g1ns2.dnspod.net”，我没加，目前不晓得有啥后果

（以下都是个人理解）至于网友说的什么CNAME，跟上面的目的是反向的。上面的目的是，当访问我们自己的域名时，显示的其实是yourName.github.io里的内容

而添加了CNAME的目的是：当访问yourName.github.io时，自动跳转到我们的域名，具体操作如下

1. 在hexo的工程的source里添加一个文件（无后缀），文件名为CNAME
2. 在该文件中仅添加一行，即你的域名，如：flowerfat.com（不要www）
3. hexo g一下，这时public里会自动生成一个CNAME（其实就是复制过去的。。。）

## Tips

1. 网站里输入的中文是乱码，这个可能跟hexo里的language: zh-CN无关，而是你使用了记事本来编辑，记事本保存的编码格式并不是utf-8（用其他编辑器或者另存为utf-8）
2. 

## 相关链接

- [怎样将域名绑定到github pages 博客上](http://jingyan.baidu.com/article/3c343ff70fb6e60d3779632f.html)
