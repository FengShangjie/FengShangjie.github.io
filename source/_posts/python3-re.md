---
title: python3-re
abbrlink: 63609
date: 2018-07-13 17:55:25
tags:
---

# python3中正表达式中的用法笔记
由于自己对正则表达式不是很熟悉，自己就重新学习了一下这个正则表达式。下面是我学习正则表达式的一些笔记，自己主要是用于备忘与查询
<!-- more -->
### 1、元字符
序号 |字符  |  说明
--|-- |--
1 | \  | 转义符，表示转义
2 | . |表示任意一个字符
3 | + | 重复一次或者多次
4 | * | 重复零次或者多次
5 | ? | 重复零次或者一次
6 | \| | 选择符号，表示“或关系”，例如A\|B 表示匹配A或B
7 | {} | 定义量词
8 | [] | 定义字符类
9 | () | 定义分组
10 | ^ | 可以表示取反， 或者匹配一行的开始
11 | $ | 匹配一行的结束
```python
import re
p1 = r'\w+@zhijieketang\.com'  #没有规定字符位置匹配字符
p2 = r'^\w+@zhijieketang\.com$'  #规定了必须要以.com结尾

text = "Tony's email is tony_guan588@zhijieketang.com."

m =  re.search(p1, text)#p1与text匹配
#输出为<_sre.SRE_Match object; span=(16, 45), match='tony_guan588@zhijieketang.com'>
print(m) 


m =  re.search(p2, text) #p2与text匹配
#输出为None
print(m)

email = 'tony_guan588@zhijieketang.com'
m =  re.search(p2, email)#p2与email匹配
#输出为<_sre.SRE_Match object; span=(0, 29), match='tony_guan588@zhijieketang.com'>
print(m)
```
### 2、预定义字符类
==这里包括一些长用的字符表现形式，我们在c语言中经常使用==
字符 | 说明 
--|--
. | 匹配任意一个字符
\\\\ | 匹配反斜杠\字符
\n | 匹配换行
\r | 匹配回车
\f | 匹配一个换页符
\t | 匹配一个水平制表符
\v | 匹配一个垂直制表符
\s | 匹配一个空格符，等价于[\n\r\f\t\v]
\S | 匹配一个非空格符，等价于[^\s]
\d | 匹配一个数字字符，等价于[0-9]
\D | 匹配一个非数字字符，等价于[^0-9]
\w | 匹配任何语言的单词字符(如：英文字母、亚洲文字)、数字和下划线(_)等字符。如果正则表达式编译标志设置为ASCII，则指匹配[a-z0-9A-Z]
\W | 相当于[6\w]

### 3、字符类
这里主要包含着如何定义一个字符类(与其他的字符类是<br>不同的这里面主要使用 `[]` 来做定义类。)

`r'[0123456789]'` 表示数字集

`r'[^0123456789]'` 表示非数字集

### 4、区间
区间是用 `-` 表示的

数字字符类 `[0123456789]` 表示为 `[0-9]`
<br><br>
区间主要是使用在如果使用字符类， 则串里面的内容比较长，如果使用区间表示比较简单<br>
小写字母字符类 `[a-z]` <br>
大写字母字符类 `[A-z]` <br>
还可以使用间隔 `[0-25-7]`表示0、1、2、5、6、7<br>

### 5、量词
字符 | 说明
--|--
？ | 出现==一==次或==零==次
* | 出现==多==次或==零==次
+ | 出现==一==次或==多==次
{n} | 出现==零==或==n==次
{n,m} | 至少出现==n==次，但不超过==m==次
{n,} | 至少出现n次
{n, m}? | 只匹配5个，惰性量词

### 6、分组
自此之前学习量词只能重复显示一个字符， 如果想让一个字符串作为整体使用量词，可将这个字符串发放到一对小括号中。这就是分组。<br>

```python
import re

p = r'(121){2}' #正则表达式，并且创建分组(121)并且重复2次
m = re.search(p, '121121abcabc')

print(m)
print(m.group()) #返回匹配的字符串 打印121121
print(m.group(1)) #返回自一个组的内容 打印121
print(m.groups()) #返回所有组的内容 打印('121',)

p = r'(121){2}(abc){2}'
m = re.search(p, '121121abcabc')
print(m.group()) #打印121121abcabc
print(m.group(1)) #打印121
print(m.groups()) #打印('121', 'abc')
```

分组还可以通过分组名字来访问
<br>格式:p = r'(?P<area_code>\d{3,4})-(?P<num_code>\d{7,8})'
<br> (？P<name>匹配串)
```python
import re

p = r'(\d{3,4})-(\d{7,8})' #正则表达式，建立区号和电话号码
m = re.search(p, '0792-87654321')

print(m)
print(m.group(1)) 
print(m.group(2)) 
print(m.groups())
'''
<_sre.SRE_Match object; span=(0, 13), match='0792-87654321'>
0792
87654321
('0792', '87654321')
'''

p = r'(?P<area_code>\d{3,4})-(?P<num_code>\d{7,8})' #区号命名为area_code,电话号码命名为num_code
m = re.search(p, '0792-87654321')

print(m.group(1)) #通过分组号访问
print(m.group(2)) 
print(m.group("area_code"))  #通过定义的名字来访问 
print(m.group("num_code")) 
'''
0792
87654321
0792
87654321
'''
#通过名字与编号访问结果式一样的
```
通过反向引用分组能获取特定的标签
```python
import re
p = r'<([\w]+)>.*</([\w]+)>'  #这是正常分组
m = re.search(p, '<a>aaa</a>')

print(m) #能但会匹配结果
m = re.search(p, '<a>aaa</b>')

print(m) #能返回匹配结果
p = r'<([\w]+)>.*</\1>'  #这是反向引用分组
m = re.search(p, '<a>aaa</a>')

print(m) #能返回匹配结果
m = re.search(p, '<a>aaa</b>')

print(m) #不能返回，直接返回None
```
在日常的时候我们，有时候想要返回某个文件的内容，返货全部的名称。但是使用普通的分组是不能使用的，这个时候我们需要使用`非捕获分组`
```python
import re 
s = 'img1.jpg, img2.jpg, img3.bmp'
p = r'\w+(\.jpg)'  #正常分组
m = re.findall(p, s) 
print(m)  #输出['.jpg', '.jpg']
p = r'\w+(?:\.jpg)'  #采用非捕获分组
m = re.findall(p, s) 
print(m) #输出['img1.jpg', 'img2.jpg']
```


