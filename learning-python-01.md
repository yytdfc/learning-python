

# <center>Learning Python<br>Lecture - 1</center>

---
<!-- footer: Learning Python -->
<!-- page_number: true -->
<!-- *page_number: false -->
## 1. 简介
---
## 简介 
<img align="right" src="https://www.python.org/static/img/python-logo.png">

- Python由Guido van Rossum于1989年底发明，第一个公开发行版发行于1991年。
- Python是一种解释型、面向对象、动态<br>数据类型的高级程序设计语言。

---
## Python环境配置
- pip: [PyPI - the Python Package Index](https://pypi.python.org/pypi)的包管理工具:
推荐使用[阿里云源镜像](http://mirrors.aliyun.com/)
```sh
sudo apt install python3 python3-pip
pip install xxx
```
- [conda](https://www.continuum.io/downloads): 一个开源包管理系统和环境管理系统:
推荐使用[清华源镜像](https://mirror.tuna.tsinghua.edu.cn/help/anaconda/)
```sh
wget https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/\
    Anaconda3-4.4.0-Linux-x86_64.sh
sh ./Anaconda3-4.4.0-Linux-x86_64.sh
conda install xxx
```

---
## Hello World
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
## 如何学习Python
- 官方文档 (推荐使用[Zeal](https://zealdocs.org/)下载文档到本地方便随时查阅):
	- [**The Python Tutorial**](https://docs.python.org/3/tutorial/) _**([中文翻译](http://www.pythondoc.com/pythontutorial3/))**_
	- [The Python Language Reference](https://docs.python.org/3.6/reference/index.html)
	- [The Python Standard Library](https://docs.python.org/3/library/index.html)
- `help` 命令: 查看某个函数的帮助说明, 如 `help(print)`
- `dir` 命令: 查看某个包或者对象的所有方法, 如 `dir(str)`
- 其他推荐的教程: _[A Byte of Python(简明Python教程)](https://www.gitbook.com/book/lenkimo/byte-of-python-chinese-edition/details), [菜鸟教程](http://www.runoob.com/python3/python3-tutorial.html), [Effective Python(中文翻译)](https://github.com/guoruibiao/Effective-Python),_

---
<!-- *page_number: false -->
## 2. 基本语法
---
## 命名和注释
- 变量命名采用`A~Z`, `a~z`, `_`
- 一般在源文件头注释该源文件编码: `# -*- coding: <utf-8> -*-`
- 注释用 `#` 或者 `''' '''`:
``` py
# inline comments

"""
paragraph comments
"""
```

---
## 换行和缩进
- 采用缩进表示语法层次结构, 如:
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
week = ['Monday', 'Tuesday', 'Wednesday', 'Thursday',  # 这里隐式换行
        'Friday', 'Saturday', 'Sunday']                # 这里缩进不影响
```

---
## 保留关键字
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
## 运算符和分隔符
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
## 3. 数据类型
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
### 有序序列
- 不可变:
	- 字符串: `str`
	- 元组: `tuple`
	- 字节串: `bytes`
- 可变:
	- 列表: `list`
	- 字节数组: `bytearray`
---
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
>>> s[0:2]  # 使用切片获取, 类似于substr
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

```

---
### 元祖 `tuple`
```py

```

---
### 字典 `dict`
```py

```

---
### 集合 `set`
```py

```


---
### 模块: `module`
- 由 `import` 导入, 类似于C++中的 `namespace`

---
<!-- *page_number: false -->
## 4. 运算符
---
### 数学运算符
``` py
>>> 17 / 3  # python3中为浮点数除法运算
5.666666666666667
>>> 17 / 3  # python2中为整数除法运算
5
>>> 17 // 3  # 整数除法运算
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
### 逻辑运算符
``` py

```



---
<!-- *page_number: false -->
## 5. 基本语句
---
### pass

### return

---
### break

### continue

### yield

### raise

---
### del

### assert

---
### gobal

### nonlocal

---
### lambda
`lambda`表达式
---
## 6. 复合语句
<!-- *page_number: false -->

---
### 条件控制 `if`
```py
if x < y < z:
    print(x)
    
if x < y: print(x)

y = x**2 if x > 0 else -x

if test1:
    action1_block
elif test2:
    action2_block
else:
    else_action_block
```

---
### 循环 `while`
```py

```

---
### 循环 `for`
```py
for i in range(10):
    print(i)
```
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
---
### 函数定义 `def`
```
def f1(x):
    return x + 1

def liner_fun(k, b):
    def f(x):
    	return k * x + b
    return f
    
def compare(x, y, reverse=False):
    if reverse:
        return x > y
    else
        return x < y
```
- 不可变类型：类似 C++ 的值传递，如 整数、字符串、元组。
- 可变类型： 类似 C++ 的引用传递，如 列表，字典。
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
```

---
<!-- *page_number: false -->
## 7. 面向对象
---
<!-- *page_number: false -->
## 8. 输入输出
---
<!-- *page_number: false -->
## 9. 文件
---
<!-- *page_number: false -->
## 10. 错误和异常
---
<!-- *page_number: false -->
## <center>_**Thanks**_


