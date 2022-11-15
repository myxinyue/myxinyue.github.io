---
layout: post
title: 用两个栈实现一个队列
categories: ListNode
description: 用两个栈实现一个队列。队列的声明如下，请实现它的两个函数 appendTail 和 deleteHead ，分别完成在队列尾部插入整数和在队列头部删除整数的功能。(若队列中没有元素，deleteHead 操作返回 -1 )
keywords: 队列
---

##  一、题目描述

**用两个栈实现一个队列**。队列的声明如下，请实现它的两个函数 `appendTail` 和 `deleteHead` ，分别完成在队列尾部插入整数和在队列头部删除整数的功能。(若队列中没有元素，`deleteHead` 操作返回 `-1` )

**示例 1：**

```text
输入：
["CQueue","appendTail","deleteHead","deleteHead"]
[[],[3],[],[]]
输出：[null,null,3,-1]
```

**示例 2：**

```text
输入：
["CQueue","deleteHead","appendTail","appendTail","deleteHead","deleteHead"]
[[],[],[5],[2],[],[]]
输出：[null,-1,null,null,5,2]
```

**提示：**

- `1 <= values <= 10000`

- `最多会对 appendTail、deleteHead 进行 10000 次调用`

  

## 二、题目解析

首先，我们来复习一下栈和队列的特点。

**1、栈是一个先进后出的线性表**。

**2、队列是一个先进先出的线性表**。

#### 入队操作

如果是栈的插入操作，那我们可以把元素都先插入到 stack1 中，也就实现了队列的 入队操作 。

#### 出队操作

- 当 stack2 中不为空时，直接操作，此时在 stack2 中的栈顶元素是最先进入队列的元素，返回该元素即可；
- 如果 stack2 为空且 stack1 也为空，返回 -1；
- 如果 stack2 为空且 stack1 不为空，首先需要把 stack1 中的元素逐个弹出并压入到 stack2 中，然后返回 stack2 的栈顶元素即可。

### 三、代码实现

```java
class CQueue {

    // 队列的特点，先进先出
    // 栈的特点是先进后出
    // 创建两个栈
    // 创建栈 stack1 用来充当队列
    Stack<Integer> stack1;
    
    // 创建栈 stack2 用来辅助 stack1 执行队列的一些复杂操作
    Stack<Integer> stack2;
    
    // 这个函数是 creat queue
    // 意思就是初始化队列
    // 由于题目要求我们用两个栈实现队列，所以在这个函数中初始化的是两个栈
    public CQueue() {

        // 初始化 stack1 
        stack1 = new Stack<Integer>();

        // 初始化 stack2 
        stack2 = new Stack<Integer>();

    }
    
    // 这个函数的意思是在队列的尾部添加元素
    // 使用栈来完成这个操作的话就是在 stack1 的后面添加元素就行
    public void appendTail(int value) {

        // 直接将元素存放到 stack1 中
        // 比如原队列为
        //       -------------
        //  队尾  1  2  3  4  5  队头
        //       -------------
        // 当前 value 为 6 
        // 那么由 stack1 和 stack2 组成的队列就是
        //       ----------------
        //  队尾  6  1  2  3  4  5  队头
        //       ----------------
        stack1.push(value);

    }
    
    // 这个函数的意思是在队列的头部删除元素
    // 由于队列的特点是先进先出，所以需要借助 stack1 和 stack2 去定位到之前存储进来的元素
    public int deleteHead() {

        // 1、如果 stack2 栈不为空，说明 stack2 里面已经存储了一些元素，
        // 并且 stack2 的栈顶元素就是两个栈中最早加入的元素
        if(!stack2.isEmpty()){
            // 返回 stack2 的栈顶元素，满足了队列先进先出的特点
            return stack2.pop();
        }

        // 2、如果 stack2 为空，并且发现 stack1 也为空，
        // 说明 stack1 和 stack2 构建的队列中没有元素，
        if(stack1.isEmpty()){
            // 根据题意，直接返回 -1
            return -1;
        }

        // 3、如果 stack2 为空，但 stack1 不为空
        // 那么需要先将 stack1 中的元素依次【倒序】放入 stack2 中
        // 对于 stack1 来说，越早加入的元素在【栈底】，越晚加入的元素在【栈顶】
        // 由于队列是【先进先出】，所以删除的应该是 stack1 的【栈底】元素
        while(!stack1.isEmpty()){
            // 获取 stack1 的栈顶元素并将该元素从 stack1 中弹出
            int topValue = stack1.pop();
            // 把该元素加入到 stack2
            // 这样 stack2 的栈顶元素就是 stack1 的栈底元素
            stack2.push(topValue);
        }

        // 4、返回 stack2 的栈顶元素，满足了队列先进先出的特点
        return stack2.pop();
    }
}
```

