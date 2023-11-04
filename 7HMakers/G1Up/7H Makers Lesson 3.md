# 基础的TensorFlow 使用

## Python 基础语句

#### 变量部分

``` python
# 创建变量
a = None
b = 1
c = 1.5
b = 'Hello world!'
e = [a, b, c, d]

# 变量赋值
a = 1
b = 2
a = b        # after run this code, the value of a changes into 2(the value of b)
```

#### 分支结构

##### 逻辑值

True ， False

##### 逻辑运算

与 and 同时为 True
或 or 有一个为  True
非 not 
~~短路运算符~~

##### 运算符

```python
a > b
a < b

a >= b
a <= b

a == b         # if a is equal to b, return true
a != b         # if a isn't equal to b, return true
```

##### 基础语法
```python
# if -> 如果为真，则执行

if True:
	print("This is True!")
else:
	print("This is not True")

if a > 0:
	print("a > 0")
elif a < 0:
	print("a < 0")
else:
	print("a = 0")

```

#### 循环结构

重复执行同一个代码块，直到一定条件

##### for 

For 类似于 " For each ", 遍历一次，并取出元素

```python

for i in range(5):
	print(i)

"""
RunTime:
______________
0
1
2
3
4
______________
range(startNumber, endNumber, Step)

similar to 
for (int i = startNumber; i < endNumber, i += Step)
in C
"""
```

##### While

重复执行，直至while的条件表达式值为False
~~Don't stop untile the conditional expression is false~~
~~Do this while the conditional expression is true~~

```python
i = 0
while i < 5:
	print(i)
	i += 1

"""
RunTime:
________________
0
1
2
3
4
________________

"""
```


#### 调包

因为语言内置的方法之类的十分有限，为了使用其他的功能，我们需要把其他的方法 / 库导入到我们当前的文件之中

```python
import numpy        
# 把 numpy 里的所有内容全部导入，之后需要访问，则使用语句： numpy.Something / numpy.SomeFunction()

import numpy as np
# 导入 numpy 的同时为 numpy 取一个 " 别名 " 叫做 np, 在之后访问的时候使用 np.Something 即可

from numpy import random
# 只把 numpy 里面的 random 调进来，numpy 里的其余东西不调用，可直接访问 random.Something
```

#### List

列表可以简单的看成数据的存储方式。比如有很多个数据，我们给他排上座号存起来，之后访问就比较方便。python 的 list 下表默认从 0 开始

```python
# 初始化列表
a = list()
a = []

a = [1, "Hello world!", 1.14]
a = [i for i in range(5)]        # a = [0, 1, 2, 3, 4]

# 插入数据 ( 尾插法 ) -> 在尾部插入数据
a.append(value)

# 访问数据
print(a[0])            # 输出 a 的第 0 个数据
print(a[-1])           # 输出 a 的倒数第一个数据 -> 最后一个数据

# 切片
print(a[2 : 6])        # 返回一个列表类型， [2, 6)， 等价于 [a[2], a[3], a[4], a[5]]
```

#### 方法 / 函数
把一些需要反复使用的功能抽象出来，写成一个函数，减少代码量

``` python
# 基础语法:
""" parameter 是这个方法需要传入的参数 """
def FunctionName(parameter1, parameter2, …):
	功能实现

# 无返回值函数
def PrintLogs(log):
	print(log)

# 有返回值函数
def Sum(a, b):
	return a + b
```
