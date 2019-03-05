# 使用 Github pages + Hexo 建立个人博客网站

一直想做一个属于自己的博客网站  
曾经考虑过**WordPress**,**Github Pages + Jekyll**  
但最后我权衡利弊，选择了**Github pages + Hexo**  
如果你想直接看**Github pages + Hexo**的使用教程，请跳到[如何使用 Github pages + Hexo ?](#如何使用-github-pages--hexo-)

## 为什么我选择Github pages + Hexo?

回答这个问题之前我要先说一下为什么不选择前面两者  

### WordPress : 

>* WordPress的安装步骤非常简单
>* 使用WordPress建立个人网站不需要建站者有任何编码知识

如上所述，使用WordPress建立个人网站不需要你会任何技术，撰写文章、主题设置、信息管理...这些功能WordPress都能帮你搞定  
但正是这个优点在我看来变成了缺点，我可是一个程序员啊！WordPress所面向的用户是没有什么编程知识的人，如果我用WordPress建立个人网站岂不是显得很没技术?  
于是我把目光转向了**Github Pages**  

### Github Pages :

>* Github本身是一个技术交流社区，很好的将代码和社区联系在一起
>* 轻量级博客系统，配置方便
>* 可以绑定自己的域名

当然，光有Github Pages还是不够的，目前据我所知比较常用的模板系统有**Jekyll**和**Hexo**  

#### Jekyll :

>* 基于Ruby环境的模板系统
>* 官方提供的主题都不太顺眼 (个人感觉)

正当我考虑到底要不要使用Jekyll的时候，我遇到了**Hexo**

#### Hexo :

>* 基于Node环境的模板系统
>* 官方提供的主题要好看一些 (个人感觉)

对于一个前端来说，Node比Ruby要更有亲和力一些，更主要的是我发现Hexo上的主题有很多还是很不错的  
于是我正式开始学习Hexo

## 如何使用 Github pages + Hexo ?

### 注册Github

> 如何注册Github我就不多说了，不会的话网上有诸多教程

注册好了之后创建一个仓库

![1.jpg](https://i.loli.net/2019/02/23/5c70fce42892a.jpg)

如图 : 仓库名为 “你的用户名”.github.io，注意大小写，否则部署到github上之后你就只能看到404了

![3.jpg](https://i.loli.net/2019/02/23/5c70ffe4067ad.jpg)

选项打勾的话会默认创建一个Read.md文件在仓库中，你可以写一些关于该仓库的说明，当然也可以不勾选

点击Create repository创建该仓库

这时github识别到你建立了名为 “你的用户名”.github.io 的仓库，它会默认开启该仓库的**GitHub Pages**功能

![2.jpg](https://i.loli.net/2019/02/23/5c70fed9a51f4.jpg)

这时打开https://你的用户名.github.io/  
就可以看到你的个人网页了，当然上面什么都没有，就是一张白纸，因为仓库里并没有页面可以显示

### 安装Hexo

打开终端（命令行）依次运行如下命令:  

`npm install hexo-cli -g`  
`hexo init blog`  
`cd blog`  
`npm install`  
`hexo server`  

如上指令表示:

>* 在全局安装 hexo-cli 包
>* 初始化 hexo 博客，blog 为创建的博客名称
>* 转到当前的博客文件夹
>* 根据 package.json安装所有依赖的包
>* 开启 hexo 服务

默认的启动端口是http://localhost:4000/  
打开即可看到当前hexo为你搭建的博客  

![3634877046-5bc6cfb8be400_articlex.jpg](https://i.loli.net/2019/02/23/5c7104315ded0.jpg)

这是hexo的默认主题  
如果你认为不好看，那么可以在官网上寻找你喜欢的主题

### 自定义blog

https://hexo.io/themes/

该网站是官网主题站，可以在上面寻找自己喜欢的模板

![4.jpg](https://i.loli.net/2019/02/23/5c71052ac8fe6.jpg)

比如我选中了上图的模板，那么点击标题进入他的github(不是点击图片，点击图片进入的是该主题的预览页面)

![5.jpg](https://i.loli.net/2019/02/23/5c71060a03b04.jpg)

之后可以按照该模板中**README.md**文件上的说明来安装并使用该模板

## 如何写博客?

万事俱备，只差博客，那么博客应该怎么写呢? 同样的:  

`cd blog`  
`hexo new a`  

a指的是文章的标题，可以加双引号也可以不加，之后会有提示告诉你该博客于何处创建(默认为：blog/source/_posts/a.md)，你就可以在a.md中使用md语法来写博客了  
打开a.md，这时文章中应该有三个字段：  

````dash
title: a
date: 创建时间
tags: 
````  

title指的是文章标题  
data指的是该文章创建时间，至于时间格式，是根据 **_config.yml** 规定的格式显示的，一般格式是这样: 2019-02-26 09:28:01，如果不喜欢可以更改 _config.yml 文件的配置  
tags指的是该文章的标签，例如一个文章的内容涉及到了某样技术（例如JS），那么可以添加一个tag在里面，相当于给文章分类，这样以后想浏览也很方便  
写tags的格式也很简单:

````dash
tags: 
    - tag1
    - tag2
    - tag3
    ...
````

## 如何将部署到GitHub上?

有两种方法:

### 第一种

输入如下命令:  

`hexo g`  

会生成一个名为public的文件夹

回到GitHub，clone该仓库到本地

![6.jpg](https://i.loli.net/2019/02/23/5c710ab6a4e62.jpg)

这里推荐大家安装**GitHub DeskTop**软件，方便部署（这里我用的就是GitHub DeskTop）

点击 open in desktop ，这时GitHub DeskTop弹出请求框

![7.jpg](https://i.loli.net/2019/02/23/5c710b94d148b.jpg)

local path可以设置该仓库存放的位置（一定要记住）

之后将public文件夹中的文件全部复制到该仓库存放的文件夹下

这时 GitHub DeskTop 会有文件更改的提示:

![8.jpg](https://i.loli.net/2019/02/23/5c710c8651661.jpg)

如图，提示我README.md文件被修改了，这时我可以填写一个备注:Update README.md 表明我做了修改README.md的操作，下面的框框里可以写更多有关该操作的信息  
然后就可以点击commit

![9.jpg](https://i.loli.net/2019/02/23/5c710e80ce0f9.jpg)

这是上方会出现Push origin的选项，点击就可以将更改部署到github上了  
打开https://你的用户名.github.io/  
就可以看到完成的博客咯！

### 第二种

使用hexo d命令自动部署到github上

但操作有些麻烦，我就不说了，这里有个教程不错，可以去看看：  
https://blog.csdn.net/Greenovia/arcticle/details/60576985

## 部署github遇到的一些问题

### 网站显示异常

很多人在找到自己喜欢的主题之后，对某一些细节还是不太满意，自己更改了并且部署到github之后发现github并没有应用修改之后的样式，这是为什么呢?  
因为github并没有更新改之后的css，他只会更新_config.yml文件的改变  
解决办法:  

`hexo clean`  
`hexo deploy`  
`hexo generate`  

上述命令作用是:  
清除缓存文件 db.json 和已生成的静态文件 public  
自动生成网站静态文件，并部署到设定的仓库  
生成网站静态文件到默认设置的 public 文件夹  

问题解决O(∩_∩)O

### 删除文章之后，文章的**tags**或**categories**还在

很多人发现删除或更改了一篇文章之后，该文章所带的**tags**和**categories**还存在于列表中，并且点击也什么都没有，如何清除和更改呢?  
解决办法:  

`hexo clean`  

这样就可以清除无用的**tags**和**categories**了  

最后，我的主题是在Hexo官网上找的，名为[Archer](https://github.com/fi3ework/hexo-theme-archer)，感谢Archer的作者提供的主题，我真的很喜欢

