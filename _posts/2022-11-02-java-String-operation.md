---
layout: post
title: 字符串操作合集，不断添加常用的
categories:  Java
description:  字符串操作合集，不断添加常用的用法，
keywords: Java
---



### 1、 判断字符串数组中是否包含某个字符串



#### 方式一

```java
String[] strArr = {"aa", "bb", "cc"};
boolean res = Arrays.asList(strArr).contains("aa"); // true
```

#### 方式二

```java
String[] strArr = {"aa", "bb", "cc"};
long count = Arrays.stream(strArr).filter(str -> str.equals("aa")).count(); // 1
```

### 2、将字符串转化为char数组

```java

String a= "abcdefg";
char[] arr = a.toCharArray();

```

```java
StringBuilder sb = new StringBuilder();
```

// 对象名.length() 序列长度

```java
System.out.println(sb.length());  // 0
```



// 对象名.append() 追加到序列

```java
sb.append("hello")
System.out.println(sb);  // hello
```

// 97代表的是是'a'

```java
sb.appendCodePoint(97);
System.out.println(sb);  // helloa
```



// 链式编程

```java
sb.append(1).append("world").append(2);
System.out.println(sb);  // helloa1world2
```



// 索引是5的位置替换成空格

```java
sb.setCharAt(5, ' ');
System.out.println(sb);  // hello 1world2
```



// 指定位置0前插入0

```java
sb.insert(0, 0);
System.out.println(sb);  // 0hello 1world2
```



// 删除索引6(包含)至索引14(不包含)的字符串

```java
sb.delete(6, 14);
System.out.println(sb);  // 0hello
```



// StringBuilder类型转换成String类型

```java
String s = sb.toString();
System.out.println(s);  // 0hello
```



### 3、判断字符数组是否包含某个字符、方法解决

```java
public class OneDay {

	public static void main(String[] args) {
		// 创建一个字符数组
		char[] str = { 'a', 'a', 'c', '-', 'a' };
		// 搜索该字符是否存在字符数组中
		int index = search(str,'-');
		// 判断字符数组中是否存在该字符
		if (index == -1) {	// index为-1时，表示字符不存在
			System.out.println("该字符不存在");
		} else {
			System.out.println("字符在字符数组中第一次出现的位置" + index);
		}
	}

	// search方法
	private static int search(char[] aStr, char aIndex) {
		int index = -1;	// 将index的值初始化为-1
		if (aStr == null) {	// 如果str值为null，则抛出非法数据异常
			new IllegalArgumentException().printStackTrace();	// IllegalArgumentException非法数据异常
		} else {
			for (int i = 0; i < aStr.length; i++) {
				if (aIndex == aStr[i]) {	// 如果字符数组里面的字符和要搜索的字符一致
					index = i;	// 就将i的值赋值给index
					break;	// 满足条件，退出循环
				}
			}
		}
		return index;	// 打印index的值
	}
}
```

