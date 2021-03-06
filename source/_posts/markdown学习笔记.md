---
title: markdown学习笔记
abbrlink: 24465
date: 2018-04-15 21:18:13
tags:
---
这里是我学习markdown的一些笔记用于自己忘记的时候复习，当然你也欢迎您对我意见。
<!-- more -->
~~~markdown
# 一级标题
~~~
# 一级标题



~~~markdown
## 二级标题
~~~
## 二级标题

~~~markdown
### 三级标题
~~~
### 三级标题

~~~markdown
#### 四级标题
~~~
#### 四级标题

~~~markdown
##### 五级标题
~~~
##### 五级标题

~~~markdown
###### 六级标题
~~~
###### 六级标题

~~~markdown
这是一个段落，根据人脑的思维我们可以根据句号来判断是一句话。
在markdown里面我们可以根据换行来判断他是一句话。但是markdown显示的时候把他显示成一段话。如果我们要表示两段话我们可以用两个换行。比如这样。
 
我不是孤单一个人。
~~~

<font size="2">这是一个段落，根据人脑的思维我们可以根据句号来判断是一句话。
在markdown里面我们可以根据换行来判断他是一句话。但是markdown显示的时候把他显示成一段话。如果我们要表示两段话我们可以用两个换行。比如这样。</font>
<font size="2">我不是孤单一个人。</font>

~~~markdown
**这里是加粗的文字。**
~~~

**这里是加粗的文字。**

~~~markdown
*这里表示斜体*
~~~

*这里表示斜体*

~~~markdown
~~这里是删除线~~
~~~

~~这里是删除线~~

~~~markdown
==这里是加重==
~~~

==这里是加重==

~~~markdown
++这里是下划线++
~~~

<font size="2">++这里是下划线++</font>

~~~markdown
`这里是底纹`
~~~

`这里是底纹`

~~~markdown
\+++里是转移符++(本来这里表示的是带有下划线的文字)
~~~

\+++里是转移符++(本来这里表示的是带有下划线的文字

~~~VV
```markdown
这里是区块 
```  
~~~

```markdown
~~~markdown
这里是区块 
~~~
```

~~~markdown
这里是区块 
~~~ 

~~~markdown
> 这里表示引用
>> 这里是子引用
~~~

> 这里表示引用
>> 这里是子引用

~~~markdown
****
这里是分隔线,用三个或以上 * 符号
****
~~~

****
这里是分隔线,用三个或以上 * 符号
****

~~~markdown
___
这里也是分隔线，用三个或以上的 _ 符号
___
~~~

---
这里也是分隔线，用三个或以上的 _ 符号
---

~~~markdown
---
这里也是分隔线，用三个或以上的 - 符号
---
~~~

---
这里也是分隔线，用三个或以上的 - 符号
---

~~~markdown
1. 这里是有序列表的第一个元素
2. 这里是有序列表的第二个元素，他的子列表是无序列表：
    - 这里是无序列表的第一个子元素
    - 这里是无序列表的第二哥元素
    - 这里是无序列表的第三个元素
- 当然了，无序列表可以单独使用了
~~~

1. 这里是有序列表的第一个元素
2. 这里是有序列表的第二个元素，他的子列表是无序列表：
    - 这里是无序列表的第一个子元素
    - 这里是无序列表的第二哥个元素
    - 这里是无序列表的第三个元素
- 当然了，无序列表可以单独使用了

~~~markdown
你想选哪个：
- [x] 选这个，因为里面有x。
- [ ] 不选这个，因为这个中间是空的。
- [ ] 我还能扩展

~~~

你想选哪个：
- [x] 选这个，因为里面有x。
- [ ] 不选这个，疑问这个中间是空的。
- [ ] 我还能扩展

~~~ markdown
[百度的超链接](https://www.baidu.com)

[这篇博客的超链接](http://www.yydwb.club)

![带有百度logo](https://www.baidu.com/img/bd_logo1.png)

![再来一个有道云笔记的logo](http://note.youdao.com/images/index/dd55e32b.logo.png)
~~~

[百度的超链接](https://www.baidu.com)

[这篇博客的超链接](http://www.yydwb.club)

![带有百度logo](https://www.baidu.com/img/bd_logo1.png)

![再来一个有道云笔记的logo](http://note.youdao.com/images/index/dd55e32b.logo.png)

~~~markdown
这里是用脚注的方式来表示url,[百度][1], [腾讯][2], [我的博客][3]

[1]:htts://www.baidu.com
[2]:http://www.qq.com
[3]:http://www.yydwb.com
~~~

这里是用脚注的方式来表示url,[百度][1], [腾讯][2], [我的博客][3]

[1]:htts://www.baidu.com
[2]:http://www.qq.com
[3]:http://www.yydwb.com

```markdown
表格的第一列  | 表格的第二列  | 空列 
--- | ------------- | ---- 
中间有三个 -  | 也可以是三个以上的 - |
这里还可以少一个  | 少了之后在后面自动补全
  |  要空第一个必须多一根 | 
  | | 空前面两列是一样的 
```


表格的第一列  | 表格的第二列  | 空列 
--- | ------------- | ---- 
中间有三个 -  | 也可以是三个以上的 - |
这里还可以少一个  | 少了之后在后面自动补全
  |  要空第一个必须多一根 | 
  | | 空前面两列是一样的 
