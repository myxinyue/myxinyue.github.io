---
layout: post
title: 配置文件详解  (ini， yaml, xml)
categories: [零碎, 配置]
description: 配置文件详解  (ini， yaml, xml) 主要介绍yaml
keywords: 零碎
---



**常用的配置文件格式：**

ini文件: 这个在windows下用的比较多,只支持一层参数，太复杂的项目就不适用了。

xml文件：上古时代就开始用了，每个标签可以自定认，但是格式很复杂，容易搞混。

json文件：现在前后端交互的行业标准，搞互联网的没有人不认识，但有个头痛的地方就是不能注释（可以写一个不用的字段把注释内容写进去，但不建议）。

yaml文件：比较新的一种配置文件格式，通俗易懂。但也有个头痛的地方，就是对齐和空格要注意雨露均沾，这个有点像Python的语法（Python开发者要随身带一把游标卡尺）。

**Yaml文件初识：**

以下为yaml文件的一个示例：

```yaml
student:
    name: chen
    age: 18
    sex: 男
    class: 11
```

转换为json格式时：

```json
{
  "student": {
    "name": "chen",
    "age": 18,
    "sex": "男",
    "class": 11
  }
}
```

以上可以看出，yaml的基本写法是比较简单的，注意的是，**同一级的字段要对齐，冒号后面要带上空格。**切记！切记！

**yaml基本语法：**

- 大小写敏感
- 使用缩进表示层级关系
- 缩进不使用tab ，只是用空格
- 所进的空格不重要，只要相同层级的元素对其即可
- **#** 表示解释

**yaml基本数据类型:**

yaml文件支持的数据类型不多，但也足够了。可以通过嵌套来解决不层级间的关系。



**几个示例：**

key-value对像

![2023-01-05_165757](/images/posts/2023-01-03-yaml-lingsui/2023-01-05_165757.png)

嵌套的key-value对像

![2023-01-05_165815](/images/posts/2023-01-03-yaml-lingsui/2023-01-05_165815.png)

包含数组的key-value对像

![2023-01-05_165829](/images/posts/2023-01-03-yaml-lingsui/2023-01-05_165829.png)

注意：**空格，空格，空格！**

上面三个示例就是使用最多的三种类型，在实际应用过程中，可以通过不同的嵌套来实现，但大多大同小异。注意yaml很反人类的地方就是冒号后面要带空格，如果看不懂，可以通过yaml转json工具来转换成易于读懂的json格式。

**yaml学习网站和转换工具：**

yaml和json互转在线工具：[https://oktools.net/json2yaml](https://link.zhihu.com/?target=https%3A//oktools.net/json2yaml)

yaml入门教程：[YAML 入门教程 | 菜鸟教程](https://link.zhihu.com/?target=https%3A//www.runoob.com/w3cnote/yaml-intro.html)

**后语：**

时代的车轮滚滚而来，没有人能当挡车的螳螂。yaml尽管有这样或那样的问题，但不会妨碍它是一种优秀的语言。业余时间学习一下新知识，是一种爱好，也是一种态度。