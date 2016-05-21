# Hexo and Github

**github pages** + **Hexo**，重点是他们两个怎么产生关系的，这里只是纯实践操作，原理去百度上其他文章看

### Hexo

网上很多，总结一下无非（我是windows）：

1. 下载nodejs --> 安装
2. 安装Hexo --> 生成一个Hexo项目 
3. 下载一款你觉得炫酷的主题，放到themes里 --> 配置“根目录”下的_config.yml里，将主题换成你下载的

### github pages

这个网上也很容易百度到

1. 创建工程（注意工程名）
2. 然后没然后了

## 重点来了，如何关联？

(这里有两种方法上传文章，一种使用deploy，这个需要SSH，我没整明白，我采用第二种，手动)

其实说白了，github pages我们就理解成是一个仓库，它存的东西，其实

就是hexo项目里的一个文件夹，哪个呢？ ** public **

1. 文章都是放在source/_post里的md文件
2. 当我们写完文章后，使用hexo g(即 hexo generate的简写)，此时public里的文件就更新了
3. 把public里的内容，通过git传到我们的github工程里，搞定