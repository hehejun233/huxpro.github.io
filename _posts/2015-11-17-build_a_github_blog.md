---
title: 利用Github Pages搭建一个个人博客
author: Eric G
layout: dq
date: 2015-11-17
categories: blog
tags: [Github]
description: 请阅读全部内容！
---
#前言

##为什么选择Github Pages?

Github Pages 有以下诸多优点：
1、github pages有300M免费空间，资料自己管理，保存可靠；

2、学着用 github，享受 github 的便利，上面有很多牛人，眼界会开阔很多；

3、顺便看看 github 工作原理，最好的团队协作流程；

4、github 是趋势；

5、就算 github 被墙了，还可以搬到国内的 gitcafe 中去。

![](http://cdnzz.ifanr.com/wp-content/uploads/2014/06/github.png)

##什么是Github Pages?

[Github Pages](http://pages.github.com/)是用来介绍你托管在Github上面的项目的，不过由于空间免费而且资源稳定，用来搭建自己的网站再好不过了。

#目录

1.0 [前言](http://www.computereric.xyz/blog/build_a_github_blog/#section)

1.0.1 [为什么选择 Github Pages?](http://www.computereric.xyz/blog/build_a_github_blog/#github-pages)

1.0.2 [什么是Github Pages?](http://www.computereric.xyz/blog/build_a_github_blog/#github-pages-1)

1.1 [目录](http://www.computereric.xyz/blog/build_a_github_blog/#section-1)

2.0 [注册Github](http://www.computereric.xyz/blog/build_a_github_blog/#github)

3.0 [新建仓库](http://www.computereric.xyz/blog/build_a_github_blog/#section-2)

3.1 [仓库个性化主题](http://www.computereric.xyz/blog/build_a_github_blog/#section-3)

4.0 [Jekyll详解](http://www.computereric.xyz/blog/build_a_github_blog/#jekyll)

4.1 [什么是Jekyll](http://www.computereric.xyz/blog/build_a_github_blog/#jekyll-2)

4.2 [Jekyll基本结构](http://www.computereric.xyz/blog/build_a_github_blog/#jekyll-3)

4.3 [博客必要文件](http://www.computereric.xyz/blog/build_a_github_blog/#section-5)

4.4 [博客自定义文件](http://www.computereric.xyz/blog/build_a_github_blog/#section-6)

4.5 [Jekyll的配置](http://www.computereric.xyz/blog/build_a_github_blog/#jekyll-4)

5.0 [YAML Front Matter和模版变量](http://www.computereric.xyz/blog/build_a_github_blog/#yaml-front-matter)

6.0 [使用Github Desktop同步](http://www.computereric.xyz/blog/build_a_github_blog/#github-desktop)

7.0 [绑定你的域名](http://www.computereric.xyz/blog/build_a_github_blog/#section-7)


#注册Github

首先，注册或者登录[Github](http://github.com/)。
![](http://www.computereric.xyz/cache/img/ghpages/1.png)

进去之后套餐选择<code>Free</code>就可以了，除非是有特殊需要，<code>Free</code>套餐基本上可以满足你的需求了。
![](http://www.computereric.xyz/cache/img/ghpages/2.png)

#新建仓库

接下来找到<code>Your Respositories</code>，你应该没有任何仓库，选择<code>+ New respositories</code>
![](http://www.computereric.xyz/cache/img/ghpages/3.png)

这时你需要注意的是，主仓库命名必须为<code>username.github.io</code>。其实<code>.io</code>换成<code>.com</code>也是可以的，但是不推荐。

至此为止，你的仓库算是建造完成了。你应该会看到这样的页面。
![](http://www.computereric.xyz/cache/img/ghpages/7.png)

##仓库个性化主题

登陆[Jekyll](http://jekyllthemes.org)，找到一个自己喜欢的主题，选择<code>Home</code>。在右上角找到<code>fork</code>，然后你在自己的仓库里就有了一个一模一样的仓库。不过你要做的就是把仓库的名称改为<code>username.github.io</code>，是不是非常简单呢！

#Jekyll详解

##什么是Jekyll

GitHub Pages为了提供对HTML内容的支持，选择了Jekyll作为模板系统，Jekyll是一个强大的静态模板系统，作为个人博客使用，基本上可以满足要求，也能保持管理的方便，你可以查看Jekyll官方文档。

你可以直接fork我的项目，然后改名，就有了你自己的满足Jekyll要求的文档了，当然你也可以按照下面的介绍自己创建。

##Jekyll基本结构

Jekyll的核心其实就是一个文本的转换引擎，用你最喜欢的标记语言写文档，可以是Markdown、Textile或者HTML等等，再通过layout将文档拼装起来，根据你设置的URL规则来展现，这些都是通过严格的配置文件来定义，最终的产出就是web页面。

##博客必要文件

<code>_config.yml</code>是该网页的配置文件，设置好了之后就不用理它了。

<code>includes</code>是用于存放一些小的可复用的模块，一般不用设置。

<code>_layouts</code>是用于存放该网页的模版文件的。

<code>_posts</code>是用来存放博客博文的，需要注意的是，这里面的文件名必须要<code>year-month-date-title.后缀</code>，例如这篇文章就是<code>2015-11-17-build_a_github_blog.md</code>，后缀可以选择<code>.md</code>，<code>.html</code>，或是<code>.textile</code>，这里推荐使用.md。

##博客自定义文件

<code>404.html</code>网址访问错误时弹出的错误信息。

<code>CNAME</code>用于绑定域名

其他文件或文件夹是可以随意创建的，例如我在<code>username.github.io</code>下创建了<code>project</code>文件夹，在此文件夹中上传了<code>project.docx</code>，你可以通过<code>http://username.github.io/project/project.docx</code>访问。例如我在主分支中创建了<code>cache</code>文件夹，在其中创建了<code>files</code>又在其中储存了<code>crazysong6.mp3</code>，你可以通过[<code>http://www.computereric.xyz/cache/files/crazysong6.mp3</code>](http://www.computereric.xyz/cache/files/crazysong6.mp3)访问。

##Jekyll的配置

Jekyll的配置写在<code>_config.yml</code>文件中，可配置项有很多，我们不去一一追究了，很多配置虽有用但是一般不需要去关心，官方配置文档有很详细的说明，确实需要了可以去这里查，我们主要说两个比较重要的东西，一个是<code>permalink</code>，还有就是自定义项。

<code>permalink</code>项用来定义你最终的文章链接是什么形式，他有下面几个变量：

<code>year</code> 文件名中的年份

<code>month</code> 文件名中的月份

<code>day</code> 文件名中的日期

<code>title</code> 文件名中的文章标题

<code>categories</code> 文章的分类，如果文章没有分类，会忽略

<code>i-month</code> 文件名中的除去前缀0的月份

<code>i-day</code> 文件名中的除去前缀0的日期

看看最终的配置效果：

<code>permalink: pretty</code> /2015/11/17/build_a_github_blog/

<code>permalink: /:month-:day-:year/:title.html</code> /11-17-2015/build_a_github_blog/

<code>permalink: /blog/:year/:month/:day/:title</code> /blog/2009/04/29/build_a_github_blog/
我使用的是：

<code>permalink: /blog/:title</code> /blog/build_a_github_blog/

自定义项的内容，例如我们定义了<code>title</code>这样一项，那么你就可以在文章中使用<code>{{site.title }}</code>来引用这个变量了，非常方便定义些全局变量。

引用的例子：{{site.title}}

#YAML Front Matter和模板变量

对于使用YAML定义格式的文章，Jekyll会特别对待，他的格式要求比较严格，必须是这样的形式：

<pre><code>---
layout: post
title: test123
---</code></pre>

这是本文章的例子：

<pre><code>---
title: 利用Github Pages搭建一个个人博客
layout: post
date: 2015-11-17
categories: blog
tags: [Github]
description: 请阅读全部内容！
---</code></pre>

前后的<code>---</code>不能省略，在这之间，你可以定一些你需要的变量，<code>layout</code>就是调用<code>_layouts</code>下面的某一个模板，他还有一些其他的变量可以使用：

<code>permalink</code> 你可以对某一篇文章使用通用设置之外的永久链接

<code>published</code> 可以单独设置某一篇文章是否需要发布

<code>category</code> 设置文章的分类

<code>tags</code> 设置文章的tag

上面的title就是自定义的内容，你也可以设置其他的内容，在文章中可以通过<code>{{ page.title }}</code>这样的形式调用。

模板变量，我们之前也涉及了不少了，还有其他需要的变量，可以参考官方的文档：[<code>https://github.com/mojombo/jekyll/wiki/template-data</code>](https://github.com/mojombo/jekyll/wiki/template-data)

#使用Github Desktop同步

PS:本人使用OS X， Windows操作应该与本教程相差无几。

首先登陆[<code>desktop.github.com</code>](http://desktop.github.com/)，下载<code>Github Desktop</code>。接下来在应用界面登陆你的Github账号。然后再打开你的Github仓库，找到<code>Clone to Desktop</code>，就会同步到本地了。

本地文件更改之后，在<code>Github Desktop</code>中会弹出<code>{num} Uncommited Changes</code>。接下来在底下填上同步信息和描述就可以了，这些信息随便填，没有什么用处。

#绑定你的域名

当你的仓库发布了之后，你可以通过<code>http://username.github.io/</code>访问。可是如果你想要一个个性化的域名呢？
这里以[<code>Dot TK</code>](http://dot.tk/)为例。首先登陆dottk，然后填一个你喜欢的域名。接下来进入DNS设置，填写你在终端<code>ping</code>的ip地址，现在是<code>103.245.222.133</code>，总之是一串带点的数字就好了。接下来返回你的仓库，在根目录处创建一个<code>CNAME</code>文件。里面填上你的域名，不要带<code>http://</code>和结尾的<code>/</code>。别的收费注册域名商操作方法也是类似的，找到解析就好。推荐使用<code>DNSPOD</code>
