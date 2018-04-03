---
layout: post
title:  "markdown"
categories: Markdown
tags:  markdown 笔记
excerpt: 更为全面的markdown使用教程
---

* content
{:toc}

---


### 1.斜体和粗体
    *斜体* 或 _斜体_
    **粗体**
    **_加粗斜体_**
    ~~删除线~~

*斜体* 或 _斜体_

**粗体**

**_加粗斜体_**

~~删除线~~
---

### 2.分级标题

    # 标题
    ## 标题
    ### 标题
    #### 标题
    ##### 标题
    ###### 标题

# 标题
## 标题
### 标题
#### 标题
##### 标题
###### 标题
---
### 3.超链接
- 链接
    
    - 行内式链接：
    
        `[百度](www.baidu.com "可选提示：百度网")`
    
        [百度](www.baidu.com "可选提示：百度网")
    
    - 参考式链接
        
        ```
        我经常去的几个网站[Google][1]、[Leanote][2]以及[百度][3]
        [Leanote 笔记][2]是一个不错的[网站][]。
        
        [1]:http://www.google.com "Google"
        [2]:http://www.leanote.com "Leanote"
        [3]:http://www.baidu.com "百度"
        [网站]:http://www.baidu.com
        ```
    
        我经常去的几个网站[Google][1]、[Leanote][2]以及[百度][3]
        [Leanote 笔记][2]是一个不错的[网站][]。
        
        [1]:http://www.google.com "Google"
        [2]:http://www.leanote.com "Leanote"
        [3]:http://www.baidu.com "百度"
        [网站]:http://www.baidu.com 
    
    - 自动链接
            
        ```
        <http://example.com/>
        <address@example.com>
        ```
        
        <http://example.com/>
        <address@example.com>
    
    - 锚点(页内超链接)
        
        在准备跳到的后面加上 {#标记}，不同编辑器不一定支持
        
        ```
        ## 0. 目录 {#index}
        跳转到[目录](#index)
        ```
        
        ## 0. 目录 {#index}
        跳转到[目录](#index)
---
### 4.列表
#### 4.1 无序列表
使用 *，+，- 表示无序列表。
```
- 无序列表项 一
+ 无序列表项 二
* 无序列表项 三
```
- 无序列表项 一
+ 无序列表项 二
* 无序列表项 三

#### 4.2 有序列表
有序列表则使用数字接着一个英文句点。
```
1. 有序列表项 一
2. 有序列表项 二
3. 有序列表项 三

```
1. 有序列表项 一
2. 有序列表项 二
3. 有序列表项 三

#### 4.3 定义型列表
定义型列表由名词和解释组成。一行写上定义，紧跟一行写上解释。解释的写法:紧跟一个缩进(Tab)

```
Markdown
:    轻量级文本标记语言，可以转换成html，pdf等格式（左侧有一个可见的冒号和四个不可见的空格）

代码块 2
:   这是代码块的定义（左侧有一个可见的冒号和四个不可见的空格）

        代码块（左侧有八个不可见的空格）
```
Markdown
:   轻量级文本标记语言，可以转换成html，pdf等格式（左侧有一个可见的冒号和四个不可见的空格）

代码块 2
:   这是代码块的定义（左侧有一个可见的冒号和四个不可见的空格）

        代码块（左侧有八个不可见的空格）

---

### 5.插入图像
- 5.1. 行内式

    语法说明：![图片Alt](图片地址 “图片Title”)
    ```
    美丽花儿： 
    ![美丽花儿](http://ww2.sinaimg.cn/large/56d258bdjw1eugeubg8ujj21kw16odn6.jpg "美丽花儿")
    ```
    美丽花儿： 
    ![若无图则显示](http://ww2.sinaimg.cn/large/56d258bdjw1eugeubg8ujj21kw16odn6.jpg "鼠标悬停显示")
- 5.2 参考式
    
    在文档要插入图片的地方写![图片Alt][标记]
    在文档的最后写上[标记]:图片地址 “Title”
    ```
    美丽花儿：
    ![美丽花儿][flower]
    
    [flower]:http://ww2.sinaimg.cn/large/56d258bdjw1eugeubg8ujj21kw16odn6.jpg  "美丽花儿"
    ```
    
    美丽花儿：
    ![美丽花儿][flower]
    
    [flower]:http://ww2.sinaimg.cn/large/56d258bdjw1eugeubg8ujj21kw16odn6.jpg  "美丽花儿"   
    
---
### 7.内容目录

在段落中填写 [TOC] 以显示全文内容的目录结构。

[TOC] 

---
### 8.脚注
要到文章末尾查看

```    
使用 Markdown[^1]可以效率的书写文档, 直接转换成 HTML[^2], 你可以使用 Leanote[^Le] 编辑器进行书写。
[^1]:Markdown是一种纯文本标记语言
[^2]:HyperText Markup Language 超文本标记语言
[^Le]:开源笔记平台，支持Markdown和笔记直接发为博文
```

使用 Markdown[^1]可以效率的书写文档, 直接转换成 HTML[^2], 你可以使用 Leanote[^Le] 编辑器进行书写。

[^1]:Markdown是一种纯文本标记语言

[^2]:HyperText Markup Language 超文本标记语言

[^Le]:开源笔记平台，支持Markdown和笔记直接发为博文
---
### 9.LaTeX公式
 - 9.1 $表示行内公式:
 
       质能守恒方程可以用一个很简洁的方程式 $E=mc^2$ 来表达。
    
    
    质能守恒方程可以用一个很简洁的方程式 $E=mc^2$ 来表达。
    
 - 9.2 $$ 表示整行公式:
```
$$\sum_{i=1}^n a_i=0$$

$$f(x_1,x_x,\ldots,x_n) = x_1^2 + x_2^2 + \cdots + x_n^2 $$

$$\sum^{j-1}_{k=0}{\widehat{\gamma}_{kj} z_k}$$
```
$$\sum_{i=1}^n a_i=0$$

$$f(x_1,x_x,\ldots,x_n) = x_1^2 + x_2^2 + \cdots + x_n^2 $$

$$\sum^{j-1}_{k=0}{\widehat{\gamma}_{kj} z_k}$$
---
### 10.流程图
```
flow
st=>start: Start:>https://www.zybuluo.com
io=>inputoutput: verification
op=>operation: Your Operation
cond=>condition: Yes or No?
sub=>subroutine: Your Subroutine
e=>end

st->io->op->cond
cond(yes)->e
cond(no)->sub->io
```
### 11.表格
第一行为表头；第二行为分割(格式设置)；第三行为内容
```
|学号|姓名|分数|
|-|-:|-|
|小明|男|75|
|小红|女|79|
|小陆|男|92|
```
|学号|姓名|分数|
|-|-:|-|
|小明|男|75|
|小红|女|79|
|小陆|男|92|


--- 
### 12.分割线
效果一样
```
* * *
***
*****
- - -
---------------------------------------
```
* * *
***
*****
- - -

-------

---
### 13.代码
插入行内代码，即插入一个单词或者一句代码的情况，使用\`code\`这样的形式插入。
插入多行代码，可以使用缩进或者“` code “`,具体看示例。