---
layout: post
title: idea 常见出错整理
categories: Idea
description: 整理常见的maven项目构建等idea出错怎么更改
keywords: Idea , 项目
---



### idea  spring构建中无效发行版本17 

此时我们需要修改项目jdk版本为1.8（不一定非得是，但是推荐）

查看以下位置

#### 1、setting中

maven runner

![image-20221116133453139](/images/posts/idea/image-20221116133453139.png)



Java -compiler版本是不是

上面是总体。下面是单个模板

![image-20221116133624404](/images/posts/idea/image-20221116133624404.png)

#### 2、project structure

![image-20221116133956131](/images/posts/idea/image-20221116133956131.png)

![image-20221116134058802](/images/posts/idea/image-20221116134058802.png)

   模板需要的

![image-20221116134142726](/images/posts/idea/image-20221116134142726.png)

![image-20221116134228792](/images/posts/idea/image-20221116134228792.png)

![image-20221116134257990](/images/posts/idea/image-20221116134257990.png)

#### 3、最后如果还不行就修改 maven 文件 conf/settings.xml

![image-20221116134411177](/images/posts/idea/image-20221116134411177.png)

​     ![img](/images/posts/idea/cbe477d3a03162a412dab393f281543a.gif)
