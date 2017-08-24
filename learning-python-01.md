

# <center>_Learning Python - 1_
<br>

[_<center>https://github.com/yytdfc/learning-python_](https://github.com/yytdfc/learning-python)

---
<!-- footer: https://github.com/yytdfc/learning-python -->
<!-- page_number: true -->
<!-- *page_number: false -->
## Content
1. 简介
2. 基本语法
3. 数据结构
4. 条件控制
5. 循环语句
6. 函数
6. 面向对象编程
7. 错误和异常
9. Python Standard Library 简介
---
<!-- *page_number: false -->
## <center>1. 简介
---
### 简介 
<img align="right" src="https://www.python.org/static/img/python-logo.png">

- Python由Guido van Rossum于1989年底发明, 第一个公开发行版发行于1991年.
- Python是一种解释型、面向对象、动态数据类型的高级程序设计语言.
- Python语法简洁, 开发高效, 适合作为胶水语言.
- Python拥有大量高质量第三方库, 方便易用.

---
### Python环境配置
- pip: [PyPI - the Python Package Index](https://pypi.python.org/pypi)的包管理工具:
推荐使用[阿里云源镜像](http://mirrors.aliyun.com/)
```sh
sudo apt install python3 python3-pip
pip install xxx
```
- [conda](https://www.continuum.io/downloads): 一个开源包管理系统和环境管理系统:
推荐使用[清华源镜像](https://mirror.tuna.tsinghua.edu.cn/help/anaconda/)
```sh
wget https://mirrors.tuna.tsinghua.edu.cn/anaconda/\
    archive/Anaconda3-4.4.0-Linux-x86_64.sh
sh ./Anaconda3-4.4.0-Linux-x86_64.sh
conda install xxx
```
---
### Python IDE

- 文本编辑器
如 [Vim](www.vim.org/), [Emacs](https://www.gnu.org/s/emacs), [Sublime](https://www.sublimetext.com) 等
- [Spyder](https://github.com/spyder-ide/spyder) <img src="https://avatars0.githubusercontent.com/u/1284937?v=4&s=200" align=right width=80>
集成IPython, 主要用于科学计算, 最接近于于matlab 
- [Jupyter Notebook](http://jupyter.org/)
- <img src="http://www.python3statement.org/assets/jupyter.png" align=right width=90>在网页使用, 按块编写内容, 支持Python代码, 文本, markdown等形式, 可以形成报告.
- [PyCharm](https://www.jetbrains.com/pycharm/) <img src="https://d3nmt5vlzunoa1.cloudfront.net/pycharm/files/2015/12/PyCharm_400x400_Twitter_logo_white.png" align=right width=90>
JetBrains出品

---
### Python2 or Python3 ?
- 可参考官方选择建议: [Should I use Python 2 or Python 3 for my development activity?](https://wiki.python.org/moin/Python2orPython3)
- [_Python3 宣言 - Moving to require Python 3_](http://www.python3statement.org/):
>2015年~2020年为过渡期, 保持Python2的支持更新, 2020年后全面支持Python3, 放弃Python2的维护更新.

![70%](https://upload.wikimedia.org/wikipedia/en/thumb/c/ce/Cython-logo.svg/220px-Cython-logo.svg.png) ![35%](http://www.python3statement.org/assets/ipython.png) ![25%](http://www.python3statement.org/assets/jupyter.png) ![100%](http://www.python3statement.org/assets/pandas.png) ![35%](http://www.python3statement.org/assets/matplotlib.png) ![55%](http://www.python3statement.org/assets/sympy.png) ![30%](http://www.python3statement.org/assets/biopython.png) ![30%](http://www.python3statement.org/assets/pymc3.png) ![50%](http://www.python3statement.org/assets/osbrain.png) ...

---
### Hello World
Python支持交互式和脚本式两种编程方式:
- 交互式:
```sh
$ python3  # 启动 python3
```
```py
>>> print('hello world')
hello world
```
- 脚本式:
编写 `hello_world.py` 文件:
```py
print('hello world')
```
```sh
$ python3 hello_world.py  # 运行 hello_world.py
```
---
### Zen of Python
``` py
>>> import this
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
...
...
```
---
### 如何学习Python
- 官方文档 (推荐使用[Zeal](https://zealdocs.org/)下载文档到本地方便随时查阅):
	- [**The Python Tutorial**](https://docs.python.org/3/tutorial/) _**([中文翻译](http://www.pythondoc.com/pythontutorial3/))**_
	- [The Python Language Reference](https://docs.python.org/3.6/reference/index.html)
	- [The Python Standard Library](https://docs.python.org/3/library/index.html)
- `help` 命令: 查看某个函数的帮助说明, 如 `help(print)`
- `dir` 命令: 查看某个包或者对象的所有方法, 如 `dir(str)`
- 其他推荐的教程:
_[A Byte of Python(简明Python教程)](https://www.gitbook.com/book/lenkimo/byte-of-python-chinese-edition/details), [Effective Python(翻译)](https://github.com/guoruibiao/Effective-Python),
[菜鸟教程](http://www.runoob.com/python3/python3-tutorial.html),  [CS 116 Introduction to Computer Science](https://uwflow.com/course/cs116)_
---
### 关于本课程
- _[https://github.com/yytdfc/learning-python](https://github.com/yytdfc/learning-python)_
- _一些参考资料: [在这里](https://github.com/yytdfc/learning-python/tree/master/resources)_
- _Presentation powered by [Marp](https://yhatt.github.io/marp/)_
---
<!-- *page_number: false -->
## <center>2. 基本语法
---
### 命名和注释
- 变量命名采用`A~Z`, `a~z`, `_`
- 一般在源文件头注释该源文件编码: 
`# -*- coding: <utf-8> -*-`
- 注释用 `#` 或者 `''' '''`:
``` py
# inline comments

"""
block comments
"""
```
---
### 缩进和换行
- 采用缩进(一般4空格)表示语法层次结构, 如:
```py
def perm(l):
    if len(l) <= 1:
        return [l]
    r = []
    for i in range(len(l)):
        s = l[:i] + l[i+1:]
        p = perm(s)
        for x in p:
        r.append(l[i:i+1] + x)
    return r
```

- 使用 `\` 作为显示续行符
- 两个括号中内容自动隐式换行, 如:
```py
week = ['Monday', 'Tuesday', 'Wednesday', 'Thursday',
        'Friday', 'Saturday', 'Sunday']  # 缩进不影响
```

---
### 保留关键字
- Python有以下保留关键字, 变量命名时**不建议**使用:
```py
False      class      finally    is         return
None       continue   for        lambda     try
True       def        from       nonlocal   while
and        del        global     not        with
as         elif       if         or         yield
assert     else       import     pass
break      except     in         raise
```
---
### 运算符和分隔符
- 运算符:
```py
+       -       *       **      /       //      %      @
<<      >>      &       |       ^       ~
<       >       <=      >=      ==      !=
```
- 分隔符:
```py
(       )       [       ]       {       }
,       :       .       ;       @       =       ->
+=      -=      *=      /=      //=     %=      @=
&=      |=      ^=      >>=     <<=     **=
```
---
### gobal

### nonlocal
---
### 运行模式
``` py
i = 10
def f():
    print(i)
i = 42
f()
```
---
<!-- *page_number: false -->
## <center>3. 数据类型
--- 
### 数字类型 `numbers.Number`
- 整型: `numbers.Integral`
	- 整数: `int`
	- 布尔型: `bool`
- 浮点数: `numbers.Real` 即 `float`
- 复数: `numbers.Complex` 即 `complex`

> *注意:*
Python2中认为`1`, `2`等数字为整数, 使用`1.0`, `2.0`表示浮点数
Python3中默认所有的数字均为浮点数类型
---
### 数学运算符
``` py
>>> 17 / 3  # python3中为浮点数除法运算
5.666666666666667
>>> 17 / 3  # python2中为整数除法运算
5
>>> 17 // 3  # 整数除法运算, 2 3兼容
5
>>> 17 % 3  # 取余运算
2
>>> 5 ** 2  # 指数运算
25
>>> int(3.14)  # 类型转换
3
>>> (1+1j) * 2  # 复数: (实部+虚部j)
(2+2j)
```
---
### 位运算符
- `0b01` 表示二进制数
- `0o01` 表示八进制数
- `0x01` 表示十六进制数
```py
>>> bin(0b100101 & 0b100010)  # 按位与
'0b100000'
>>> bin(0b100101 | 0b100010)  # 按位或
'0b100111'
>>> bin(0b100101 ^ 0b100010)  # 按位异或
'0b111'
```
---
### 有序序列
- 不可变:
	- 字符串: `str`
	- 元组: `tuple`
	- 字节串: `bytes`
- 可变:
	- 列表: `list`
	- 字节数组: `bytearray`
### 无序容器
- 字典: `dict`
- 集合: `set`
---
### 字符串 `str`
```py
>>> s = 'abcde'
>>> s == "abcde"  # '' 字符串与 "" 字符串是等价的
True
>>> s[0] = '1'  # 字符串是不可变
TypeError: 'str' object does not support item assignment
>>> s[0:2]  # 使用切片获取, s[x,y]为返回 x <= i < y 的字符
'ab'
>>> s[:2] + 'o' + s[-1]  # 使用 + 拼接字符串
'aboe'
>>> len(s)  # 获取字符串长度
5
>>> 'abc' in s  # 判断字符串中是否包含某字符串
True
```
---
### 字符串 `str`
```py
>>> s = 'abcde 1 2 3 ab '
>>> s.find('a')  # 查找某字符串
0
>>> s.find('a',1)  # 查找某字符串
12
>>> s.split()  # 分割字符串
['abcde', '1', '2', '3', 'ab']
>>> s.split('a')  # 分割字符串
['', 'bcde 1 2 3 ', 'b ']
>>> s.startswith('abc')  # 是否以某字符串开始
True
>>> s.endswith('b')  # 是否以某字符串结尾
False
>>> s.isalpha()  # 是否全部为字母
False
```
---
### 列表 `list`
```py
>>> num_list = [4, 5, 0]
>>> str_list = ['a', 'b', 'c']
>>> mixed_list = ['abc', 12.4, True, num_list, {2: 'b'}]
>>> num_list[1] # 元素访问
5
>>> len(num_list) # 获取长度
3
>>> num_list.append(10) # 列表中添加元素
>>> num_list
[4, 5, 0, 10]
>>> num_list.extend([2, 6, 5]) # 列表扩展
>>> num_list
[4, 5, 0, 10, 2, 6, 5]
>>> str_list.index('b') # 查找元素
1
>>> str_list.insert(2, 'a') # 插入元素
>>> str_list
['a', 'b', 'a', 'c', 'd', 'e']
>>> str_list.pop(4) # 弹出一个元素
'd'
```
---
### 列表 `list`
```py
>>> num_list = [4, 5, 0, 10, 2, 6, 5]
>>> max(num_list)
10
>>> sum(num_list)
32
>>> sorted(num_list)  # 返回排序好的列表, 不更改列表
[0, 2, 4, 5, 5, 6, 10]
>>> num_list
[4, 5, 0, 10, 2, 6, 5]
>>> num_list.sort()  # 对列表进行排序, 没有返回值
>>> num_list
[0, 2, 4, 5, 5, 6, 10]
```
---
### Python中切片访问
```py
L[i:j] => [L[i],L[i+1],…,L[j-1]]
L[i:j:k] => [L[i],L[i+k],…,L[i+m*k]] # i+m*k 不超过 j
```
```py
>>> num = list(range(10))
>>> num
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> num[-1] # 最后一个元素
9
>>> num[3:-3]
[3, 4, 5, 6]
>>> num[1::2] # 取所有偶数个元素
[1, 3, 5, 7, 9]
>>> num[1:-1:2]
[1, 3, 5, 7]
>>> num[-1::-1] # 逆序
[9, 8, 7, 6, 5, 4, 3, 2, 1, 0]
>>> 
```
---
### 字典 `dict`
- 是一种key-value的数据结构, 访问时间复杂度O(1)
- key支持不可变的数据类型: `numbers.Number`, `srt`, `tuple`
```py
>>> dic = {'blue': 400, 'green': 500, 'yellow':600}
>>> dic['green']  # 获取key对应的value
500
>>> len(dic)  # 获取元素数量
3
>>> dic['red'] = 200  # 添加一个key
>>> dic
{'blue': 400, 'yellow': 600, 'red': 200, 'green': 500}
>>> dic.keys()  # 返回keys
dict_keys(['blue', 'yellow', 'red', 'green'])
>>> dic.values()  # 返回values
dict_values([400, 600, 200, 500])
>>> 'blue' in dic  # 判断dic中是否有某一个key
True
>>> dic.pop('yellow') # 弹出一个key-value
600
```
---
### 元组 `tuple`
- 与`list`类似，不同之处在于`tuple`的元素不能修改
```py
>>> tup = (1, 2, 3, 4, 5)  # ()初始化
>>> tup = 'a', 'b', 'c', 'd'  #  , 间隔初始化
>>> tup[1:3]  # 切片访问
('b', 'c')
>>> len(tup)  # 元素数量
4
>>> del tup  # 删除tuple
>>> (1, 2) + (3, 4)  # tuple加法运算
(1, 2, 3, 4)
>>> list(zip([1, 2],['a', 'b']))  # zip函数将两个list组合
[(1, 'a'), (2, 'b')]
>>> dic = {(0,1): 100, (1,0): 200} # tuple 常用作key
```
---
### 集合 `set`
- 相当于数学中的集合, 不允许有重复的元素
```py
>>> s = {0, 0, 1, 2, 2, 5}
>>> s
{0, 1, 2, 5}
>>> s.add(8)  # 增加元素
>>> s
{0, 1, 2, 8, 5}
>>> s.update({2, 4, 5})  # 并入set
>>> s
{0, 1, 2, 4, 5, 8}
>>> {1, 2, 3} & {2, 3, 4}  # 交集运算
{2, 3}
>>> {1, 2, 3} | {2, 3, 4}  # 并集运算
{1, 2, 3, 4}
>>> {1, 2, 3} - {2, 3, 4}  # 去除后者中的元素
{1}
```
---
### 模块: `module`
- 由 `import` 导入, 类似于C++中的 `namespace`
- 使用单独行`import x`或`import y as z`者来导入包和模块
- 不要使用`import x, y`导入两包
- 使用`from x import y`, 其中x是包前缀, y是不带前缀的模块名.
- 除非你完全了解包中所有的成员, 禁止使用`from x import *`的通配符导入方式
---
<!-- *page_number: false -->
## <center>4. 条件控制
---
### 逻辑运算
`==`, `<`, `>`, `<=`, `>=`, `!=`, `<>`, `and`, `or`, `not`, `is`, `in`
`==` 等价于 `is`
`!=` 等价于 `<>` 等价于 `is not`
``` py
>>> -3 < -2 < -1  # 与 C 语法不同, 这里用作联系逻辑判断
True
>>> (-3 < -2) < -1
False
>>> -4 < -3 < -2 <-1
True
>>> 1 <> 2
True
>>> True = False
>>> True
False
>>> 1 in [1, 2, 3]
True
>>> 'b' not in 'apple'
False
```
---
### `if`控制语句
```py
if x < y < z:  # 多行模式
    print(x)
    
if x < y: print(x)  # 单行模式

y = x**2 if x > 0 else -x

if condition_1:
    statement_block_1
elif condition_2:
    statement_block_2
else:
    statement_block_3
```
---
<!-- *page_number: false -->
## <center>4. 循环语句
---
### 循环控制语句
- 循环控制语句:
`continue`(直接执行下一步), `break`(跳出循环)
### `while`循环
```py
while condition:
    loop_block
```
### `for`循环
```py
for i in iter:
    loop_block
```
---
### `range`对象
`range()`函数返回有序列表的`range`对象, 可作为迭代器
```py

```
---
### 迭代器
- `next()`函数获取下一个迭代元素
```py
>>> x = [1, 2, 3]
>>> it = iter(x)  # 创建迭代器对象
>>> print (next(it))  # 输出迭代器的下一个元素
1
>>> print (next(it))
2
>>> next(it)
3
>>> next(it)  # 结束会抛出异常
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
StopIteration
```
---
### 生成器
```py
>>> def fib(n):
...     a, b, counter = 1, 2, 1
...     while 1:
...         if counter > n: return
...         yield a  # 由yield构造生成器的每一个元素
...         a, b, counter = b, a + b, counter+1
...
>>> list(fib(3))
[1, 2, 3]
>>> gen = fib(3)
>>> next(gen)
1
>>> next(gen)
2
>>> next(gen)
3
>>> next(gen)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
StopIteration
```
---
<!-- *page_number: false -->
## <center>6. 函数
---
### 函数定义 `def`
```
def f1(x):
    return x + 1  # return 返回值

def liner_fun(k, b):
    def f(x):  # 内部可以声明函数
    	return k * x + b
    return f  
    
def compare(x, y, reverse=False): # 函数参数默认值
    if reverse:
        return x > y
    else
        return x < y
```
- 不可变类型：类似 C++ 的值传递，如 整数、字符串、元组。
- 可变类型： 类似 C++ 的引用传递，如 列表，字典。
---
### `lambda`
```py
>>> fx = lambda x: x**2
>>> fx(3)
9
>>> z_xy = lambda x, y : x**2 + y
>>> z_xy(2, 3)
7
>>> liner = lambda k, b: lambda x: k * x + b
>>> f1 = liner(2, 1)
>>> f1(4)
9
>>> liner(2, 1)(3)
7
```
---
### `map`, `filter` 和 `reduce`
```py
>>> x = list(range(5))
>>> list(map(lambda x: x**2, x))
[1, 4, 9, 16, 25]
>>> list(filter(lambda x: x%2==1, x))
[1, 3, 5]
>>> from functools import reduce # Python3中需要导入
>>> reduce(lambda a,b: a*b, x)
120
```
---
### 列表推导
```py
>>> x = list(range(5))
>>> [i**2 for i in x]
[0, 1, 4, 9, 16]
>>> [i for i in x if i%2==1]
[1, 3]
>>> y = [i**2 for i in x]
>>> [j-i for i,j in zip(x,y) if i!=j]
[2, 6, 12]
>>> [[i*j for j in range(4)] for i in range(3)]
[[0, 0, 0, 0], [0, 1, 2, 3], [0, 2, 4, 6]]
>>> [i*j for i in range(3) for j in range(4)]
[0, 0, 0, 0, 0, 1, 2, 3, 0, 2, 4, 6]
>>> {i: j for i,j in zip(x,y) if i!=j}
{2: 4, 3: 9, 4: 16}
```
---
### 一行代码实现快速排序
```py
>>> sort=lambda x:[]if not x else sort([i for i in x[1:]
if i<=x[0]])+[x[0]]+sort([i for i in x[1:] if i>x[0]])
>>> sort([1, 5, 4, 2, 3, 2])
[1, 2, 2, 3, 4, 5]
```
---
<!-- *page_number: false -->
## <center>7. 面向对象编程
---
### 类定义 `class`
```py
class A:
    pass
# is equivalent to
class A(object):
    pass
    
class B(A):
    pass
class Country:
    '''Fields: continent (Str), leader (Str),
    population (Nat)'''
    def __ init __(self, cont, lead, pop):
    self.continent = cont
    self.leader = lead
    self.population = pop

canada = Country("North America", "Trudeau", 35344962)
```
---
built-in的方法:
---
<!-- *page_number: false -->
## <center>8. 错误和异常
---
### 异常 `try`:
```py
>>> def foo():
...     try:
...         return 'return from try'
...     finally:
...         return 'return from finally'
...
>>> foo()
'return from finally'
```
---
- 永远不要使用 except: 语句来捕获所有异常, 也不要捕获 Exception 或者 StandardError，捕获异常时尽量指明具体异常。
- except: 永远不用
- except FileException: 在有针对行的代码中，扑捉特定异常。但是，需要考虑全面性，如果有为捕捉的异常，会导致程序退出，需要考虑所带来的后果；
- except Exception: 捕获所有的非退出异常，缺点是没有很好的区分异常类型

---
<!-- *page_number: false -->
## <center>9. Python Standard Library 简介
---
## 输入输出
```py
```
---
## 文件
```py
```
---
## 系统
```py
```
---
<!-- *page_number: false -->
## <center>10. PEP8简介
---
### 命名规范

---
<!-- *page_number: false -->
## <center>_**Thanks**_


---
### `with`
```py
with A() as a, B() as b:
    suite
    
with A() as a:
    with B() as b:
        suite
        
with open('text.txt','r') as f:
	f.readlines()
```

