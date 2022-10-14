## 简介

------

### 语言特性

- 解释型语言：没有编译环节
- 交互式语言：在>>>提示符后直接执行代码
- 面向对象语言：封装、继承、多态

### 发展史

Python2.0于2000年发布，2020年停止维护，最后一个 Python 2.x 版本为2.7，它除了支持 Python 2.x 语法外，还支持部分 Python 3.1 语法。

Python3.0，常被称为Python 3000，于2008年发布，不向下兼容，不过很多新特性也被移植到了2.6/2.7版本



## 环境搭建

------

### Python下载

- Python 官网：https://www.python.org/
- Python文档下载地址：https://www.python.org/doc/

### Python安装

#### Windows平台

在安装最后阶段勾选上 Add Python 3.x to PATH，就不需要手动设置PATH

#### Mac平台

MAC 系统都自带有 Python2.7 环境，你可以在链接 https://www.python.org/downloads/上下载最新版安装 Python 3.x

### 解释器

当我们从Python官方网站下载并安装好Python 3.x后，我们就直接获得了一个官方版本的解释器：CPython。这个解释器是用C语言开发的，所以叫CPython。在命令行下运行`python`就是启动CPython解释器。

CPython是使用最广的Python解释器。

### 环境变量配置

自己在网上找找吧，若Windows最后没勾选上，就需要单独配置

### 运行Python

#### 交互模式

1. 在命令行中输入python3，然后在>>>后直接输入代码，最后使用exit()来退出交互模式，会大哦命令行模式
2. 在IDLE中开发，然后在>>>后直接输入代码，最后使用exit()来退出IDLE，此时窗口直接关闭，不会回到命令行模式

**缺点：**代码没有被保存，下次还需要手动输入

#### 命令行模式

在命令行模式下，可以执行`python3`进入Python交互式环境，也可以执行`python3 hello.py`运行一个`.py`文件。

执行一个`.py`文件*只能*在命令行模式执行。

Python交互模式的代码是输入一行，执行一行，而命令行模式下直接运行`.py`文件是一次性执行该文件内的所有代码。可见，Python交互模式主要是为了调试Python代码用的，也便于初学者学习，它*不是*正式运行Python代码的环境！

#### 集成开发环境

使用PyCharm，这是JetBrains打造的Python IDE，下载地址 : https://www.jetbrains.com/pycharm/download/



## 基本语法

------

### 编码格式

- 默认情况下，Python 3 源码文件以 **UTF-8** 编码，所有字符串都是 unicode 字符串。
- 当然你也可以为源码文件指定不同的编码

### 标识符

- 标识符由字母、数字和下划线组成。
- 第一个字符必须是字母表中字母或下划线 **_** 。
- 标识符对大小写敏感。

### 保留字

- 关键字都是保留字，关键字为数据类型、控制逻辑顺序的字符

- 保留字还包括语言已经定义过的其他字

- ```python
  >>> import keyword
  >>> keyword.kwlist   #输出所有保留字
  ```

### 注释

- 单行注释以 **#** 开头

- 多行注释可以用多个 **#** 号，还有 **'''** 和 **"""**

  ```python
  #!/usr/bin/python3
   
  # 第一个注释
  # 第二个注释
   
  '''
  第三注释
  第四注释
  '''
   
  """
  第五注释
  第六注释
  """
  print ("Hello, Python!")
  ```

### 缩进

Python用缩进来表示包含和层次关系。

`if/while/for/def/class`等关键字所在的整语句后通过冒号(:)结尾并在之后进行缩进，表明后续代码与紧邻无缩进语句的所属关系。

### 续行符

使用反斜杠(\)

### 变量

- 在Python里，一切皆对象，无论什么类型，都是变量存储对象的内存地址，即变量指向对象

- 变量没有类型，对象有类型，变量可以在使用过程中，指向任意类型的对象（如：a = 1; a = "xxx"）

- Python 中的变量不需要声明。每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。

- 在 Python 中，变量就是变量，它没有类型，我们所说的"类型"是变量所指的内存中对象的类型。

  ```python
  #!/usr/bin/python3
  
  counter = 100          # 整型变量
  miles   = 1000.0       # 浮点型变量
  name    = "runoob"     # 字符串
  
  print (counter)
  print (miles)
  print (name)
  ```

- Python允许你同时为多个变量赋值。例如：

  ```python
  # 为多个相同值的变量赋值
  a = b = c = 1
  # 为多个不同值的变量赋值
  a, b, c = 1, 2, "runoob"
  ```

### 行与缩进

- 单行语句结尾不用加分号（;）

- python最具特色的就是使用缩进来表示代码块，不需要使用大括号 **{}** 。

- 缩进的空格数是可变的，但是同一个代码块的语句必须包含相同的缩进空格数。示例如下：

  ```python
  if True:
      print ("True")
  else:
      print ("False")
  ```

- 以下代码最后一行语句缩进数的空格数不一致，会导致运行错误：

  ```python
  if True:
      print ("Answer")
      print ("True")
  else:
      print ("Answer")
    print ("False")    # 缩进不一致，会导致运行错误
  ```

### 多行语句

- Python 通常是一行写完一条语句，但如果语句很长，我们可以使用反斜杠 **\** 来实现多行语句，例如：

  ```python
  total = item_one + \
          item_two + \
          item_three
  ```

- 在 [], {}, 或 () 中的多行语句，不需要使用反斜杠 **\**，例如：

  ```python
  total = ['item_one', 'item_two', 'item_three',
          'item_four', 'item_five']
  ```

### 同一行显示多条语句

- Python 可以在同一行中使用多条语句，语句之间使用分号 **;** 分割，以下是一个简单的实例：

  ```python
  #!/usr/bin/python3
   
  import sys; x = 'runoob'; sys.stdout.write(x + '\n')
  ```

### 代码块与代码组

- **代码组**：if、while、def和class这样的复合语句，首行**以关键字开始**，**以冒号( : )结束**，该行之后的一行或多行代码构成代码组。

- **代码块**：多个代码组构成代码块。

  ```
  if expression : 
     suite
  elif expression : 
     suite 
  else : 
     suite
  ```

### print 输出

- **print** 默认输出是换行的

- 如果要实现不换行需要在变量末尾加上 **end=""**

  ```python
  #!/usr/bin/python3
   
  x="a"
  y="b"
  # 换行输出
  print( x )
  print( y )
  # 不换行输出
  print( x, end=" " )
  print( y, end=" " )
  ```

### import 与 from...import

- 在 python 用 **import** 或者 **from...import**或者**import...as...**来导入相应的模块。
- 将整个模块(somemodule)导入，格式为： **import somemodule**
- 从某个模块中导入某个函数,格式为： **from somemodule import somefunction**
- 从某个模块中导入多个函数,格式为： **from somemodule import firstfunc, secondfunc, thirdfunc**
- 将某个模块中的全部函数导入，格式为： **from somemodule import \***





## 基本语句

### input()

**使用方式：**<变量> = input(<提示性文字>)

无论用户输入的是字符还是数字，input()函数统一按照字符串类型（str）输出。

### eval()

**使用方式：**<变量> = eval(<字符串>)
去掉字符串最外侧的引号，并按照Python 语句方式执行去掉引号后的字符内容，通常会和
input 函数一起使用。

### print()：输出函数

使用方式：

1. 仅输出字符串：print(<待输出字符串>)

2. 仅用于输出一个或多个变量：print(<变量1>,<变量2>......<变量n>)

3. 用于混合输出字符串与变量值：
   print(<输出字符串模板，用{}占据要填充的位置>.format(<变量1>,<变量2>......<变量n>))

4. print()函数输出文本时默认在最后增加一个换行，如若不希望在最后增加换行，或者是想要输出其他内容，可以对print()函数的end 参数值进行赋值。

   `print("",end = "xxx")`



### 条件控制

```python
if condition_1:
    statement_block_1
elif condition_2:
    statement_block_2
else:
    statement_block_3
```

### 循环语句

 Python 中没有 do..while 循环，只有for和while循环

#### while循环

**一般形式为**

```
while 判断条件(condition)：
    执行语句(statements)
```

例如：

```python
sum = 0
counter = 1
while counter <= n:
    sum = sum + counter
    counter += 1
```

**无限循环**

```python
var = 1
while var == 1 :  # 表达式永远为 true
   num = int(input("输入一个数字  :"))
   print ("你输入的数字是: ", num)
```

**while 循环使用 else 语句** 如果 while 后面的条件语句为 false 时，则执行 else 的语句块。

```python
while <expr>:
    <statement(s)>
else:
    <additional_statement(s)>
```

```python
#!/usr/bin/python3
 
count = 0
while count < 5:
   print (count, " 小于 5")
   count = count + 1
else:
   print (count, " 大于或等于 5")
```

执行以上脚本，输出结果如下：

```
0  小于 5
1  小于 5
2  小于 5
3  小于 5
4  小于 5
5  大于或等于 5
```



#### for循环

**for循环的一般格式**

```python
for <variable> in <sequence>:
    <statements>
else:
    <statements>
```

```python
>>>languages = ["C", "C++", "Perl", "Python"] 
>>> for x in languages:
...     print (x)
... 
C
C++
Perl
Python
>>>
```

**range函数**

```python
>>>for i in range(5):
...     print(i)
...
0
1
2
3
4
```

```python
>>>for i in range(5,9) :
    print(i)
 
    
5
6
7
8
>>>
```

#### continue语句

#### break语句

#### pass语句

Python pass是空语句，是为了保持程序结构的完整性。

pass 不做任何事情，一般用做占位语句，如下实例

### 实例

```python
>>>while True: 
...     pass  # 等待键盘中断 (Ctrl+C)
```





## 基本数据类型

------

Python3 中有六个标准的数据类型：

- Number（数字）
- String（字符串）
- List（列表）
- Tuple（元组）
- Set（集合）
- Dictionary（字典）

Python3 的六个标准数据类型中：

- **不可变数据（3 个）：**Number（数字）、String（字符串）、Tuple（元组）；
- **可变数据（3 个）：**List（列表）、Dictionary（字典）、Set（集合）。



### Number（数字）

- Python3 支持 **int（整型）、float（浮点型）、bool（布尔）、complex（复数）**。
- Python3中，整形只有int，表示长整形。（Python2中long表示长整形）

#### isinstance与type

- type()不会认为子类是一种父类类型。

- isinstance()会认为子类是一种父类类型。

  ```python
  >>> class A:
  ...     pass
  ... 
  >>> class B(A):
  ...     pass
  ... 
  >>> isinstance(A(), A)
  True
  >>> type(A()) == A 
  True
  >>> isinstance(B(), A)
  True
  >>> type(B()) == A
  False
  ```

#### del

用于删除对象引用

```python
var1, var2 = 1, 10
del var1, var2
```

#### 数据运算

重点是**/**、**//**、******

```python
>>> 5 + 4  # 加法
9
>>> 4.3 - 2 # 减法
2.3
>>> 3 * 7  # 乘法
21
>>> 2 / 4  # 除法，得到一个浮点数
0.5
>>> 2 // 4 # 除法，得到一个整数
0
>>> 17 % 3 # 取余 
2
>>> 2 ** 5 # 乘方
32
```

#### 数学函数

| 函数                                                         | 返回值 ( 描述 )                                              |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [abs(x)](https://www.runoob.com/python3/python3-func-number-abs.html) | 返回数字的绝对值，如abs(-10) 返回 10                         |
| [ceil(x) ](https://www.runoob.com/python3/python3-func-number-ceil.html) | 返回数字的上入整数，如math.ceil(4.1) 返回 5                  |
| cmp(x, y)                                                    | 如果 x < y 返回 -1, 如果 x == y 返回 0, 如果 x > y 返回 1。 **Python 3 已废弃，使用 (x>y)-(x<y) 替换**。 |
| [exp(x) ](https://www.runoob.com/python3/python3-func-number-exp.html) | 返回e的x次幂(ex),如math.exp(1) 返回2.718281828459045         |
| [fabs(x)](https://www.runoob.com/python3/python3-func-number-fabs.html) | 返回数字的绝对值，如math.fabs(-10) 返回10.0                  |
| [floor(x) ](https://www.runoob.com/python3/python3-func-number-floor.html) | 返回数字的下舍整数，如math.floor(4.9)返回 4                  |
| [log(x) ](https://www.runoob.com/python3/python3-func-number-log.html) | 如math.log(math.e)返回1.0,math.log(100,10)返回2.0            |
| [log10(x) ](https://www.runoob.com/python3/python3-func-number-log10.html) | 返回以10为基数的x的对数，如math.log10(100)返回 2.0           |
| [max(x1, x2,...) ](https://www.runoob.com/python3/python3-func-number-max.html) | 返回给定参数的最大值，参数可以为序列。                       |
| [min(x1, x2,...) ](https://www.runoob.com/python3/python3-func-number-min.html) | 返回给定参数的最小值，参数可以为序列。                       |
| [modf(x) ](https://www.runoob.com/python3/python3-func-number-modf.html) | 返回x的整数部分与小数部分，两部分的数值符号与x相同，整数部分以浮点型表示。 |
| [pow(x, y)](https://www.runoob.com/python3/python3-func-number-pow.html) | x**y 运算后的值。                                            |
| [round(x [,n\])](https://www.runoob.com/python3/python3-func-number-round.html) | 返回浮点数 x 的四舍五入值，如给出 n 值，则代表舍入到小数点后的位数。**其实准确的说是保留值将保留到离上一位更近的一端。** |
| [sqrt(x) ](https://www.runoob.com/python3/python3-func-number-sqrt.html) | 返回数字x的平方根。                                          |

#### 随机数函数

Python包含以下常用随机数函数：

| 函数                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [choice(seq)](https://www.runoob.com/python3/python3-func-number-choice.html) | 从序列的元素中随机挑选一个元素，比如random.choice(range(10))，从0到9中随机挑选一个整数。 |
| [randrange ([start,\] stop [,step]) ](https://www.runoob.com/python3/python3-func-number-randrange.html) | 从指定范围内，按指定基数递增的集合中获取一个随机数，基数默认值为 1 |
| [random() ](https://www.runoob.com/python3/python3-func-number-random.html) | 随机生成下一个实数，它在[0,1)范围内。                        |
| [seed([x\]) ](https://www.runoob.com/python3/python3-func-number-seed.html) | 改变随机数生成器的种子seed。如果你不了解其原理，你不必特别去设定seed，Python会帮你选择seed。 |
| [shuffle(lst) ](https://www.runoob.com/python3/python3-func-number-shuffle.html) | 将序列的所有元素随机排序                                     |
| [uniform(x, y)](https://www.runoob.com/python3/python3-func-number-uniform.html) | 随机生成下一个实数，它在[x,y]范围内。                        |



### String（字符串）

- Python 不支持单字符类型，单字符在 Python 中也是作为一个字符串使用。
- 字符串是 Python 中最常用的数据类型。我们可以使用引号( **'** 或 **"** )来创建字符串。
- 创建字符串很简单，只要为变量分配一个值即可。例如：

```python
var1 = 'Hello World!'
var2 = "Runoob"
```

#### 访问字符串中单个字符

直接用方括号[]来获取，如：

```python
str = "RUNOOB"
print(str[1])
```

#### 字符串的截取

- 使用[_ : _]方式来截取， _中不放值，代表开头/结尾；取值结果包括起始位置，不包括截止位置

- 索引值以 **0** 为开始值，**-1** 为从末尾的开始位置。

```
str = "RUNOOB"
---------------结果------
str[:] = "RUNOOB"
str[0:] = "RUNOOB"
str[:5] = "RUNOO"
str[0:2] = "RU"
str[1:4] = "UNO"
```

#### 字符串拼接

使用“+”拼接

```python
print("xxx" + "aaa")
```

#### 转义字符

- 字符串中有特殊字符的，用\来转义（即将\加到特殊字符前）
- \n  \b  \t...在字符串中有特殊左右

#### Python字符串运算符

下表实例变量 a 值为字符串 "Hello"，b 变量值为 "Python"：

| 操作符 | 描述                                                         | 实例                            |
| :----- | :----------------------------------------------------------- | :------------------------------ |
| +      | 字符串连接                                                   | a + b 输出结果： HelloPython    |
| *      | 重复输出字符串                                               | a*2 输出结果：HelloHello        |
| []     | 通过索引获取字符串中字符                                     | a[1] 输出结果 **e**             |
| [ : ]  | 截取字符串中的一部分，遵循**左闭右开**原则，str[0:2] 是不包含第 3 个字符的。 | a[1:4] 输出结果 **ell**         |
| in     | 成员运算符 - 如果字符串中包含给定的字符返回 True             | **'H' in a** 输出结果 True      |
| not in | 成员运算符 - 如果字符串中不包含给定的字符返回 True           | **'M' not in a** 输出结果 True  |
| r/R    | 原始字符串 - 原始字符串：所有的字符串都是直接按照字面的意思来使用，没有转义特殊或不能打印的字符。 原始字符串除在字符串的第一个引号前加上字母 **r**（可以大小写）以外，与普通字符串有着几乎完全相同的语法。 | `print( r'\n' ) print( R'\n' )` |
| %      | 格式字符串                                                   | 请看下一节内容。                |

#### Python 字符串格式化

```python
#!/usr/bin/python3
 
print ("我叫 %s 今年 %d 岁!" % ('小明', 10))
```

python字符串格式化符号:

| 符  号 | 描述                                 |
| :----- | :----------------------------------- |
| %c     | 格式化字符及其ASCII码                |
| %s     | 格式化字符串                         |
| %d     | 格式化整数                           |
| %u     | 格式化无符号整型                     |
| %o     | 格式化无符号八进制数                 |
| %x     | 格式化无符号十六进制数               |
| %X     | 格式化无符号十六进制数（大写）       |
| %f     | 格式化浮点数字，可指定小数点后的精度 |
| %e     | 用科学计数法格式化浮点数             |
| %E     | 作用同%e，用科学计数法格式化浮点数   |
| %g     | %f和%e的简写                         |
| %G     | %f 和 %E 的简写                      |
| %p     | 用十六进制数格式化变量的地址         |

#### Python三引号

python三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符。实例如下

```python
#!/usr/bin/python3
 
para_str = """这是一个多行字符串的实例
多行字符串可以使用制表符
TAB ( \t )。
也可以使用换行符 [ \n ]。
"""
print (para_str)
```

以上实例执行结果为：

```
这是一个多行字符串的实例
多行字符串可以使用制表符
TAB (    )。
也可以使用换行符 [ 
 ]。
```

#### f-string

f-string 是 python3.6 之后版本添加的，称之为字面量格式化字符串，是新的格式化字符串的语法。

**f-string** 格式化字符串以 **f** 开头，后面跟着字符串，字符串中的表达式用大括号 {} 包起来，它会将变量或表达式计算后的值替换进去，实例如下：

```python
>>> name = 'Runoob'
>>> f'Hello {name}'  # 替换变量
'Hello Runoob'
>>> f'{1+2}'         # 使用表达式
'3'

>>> w = {'name': 'Runoob', 'url': 'www.runoob.com'}
>>> f'{w["name"]}: {w["url"]}'
'Runoob: www.runoob.com'
```



### List（列表）

- 序列中的每个值都有对应的位置值，称之为索引，第一个索引是 0，第二个索引是 1，依此类推。

- 列表的数据项不需要具有相同的类型

- Python 已经内置确定序列的长度以及确定最大和最小的元素的方法。

- 创建一个列表，只要把逗号分隔的不同的数据项使用方括号括起来即可。如下所示：

  ```python
  list1 = ['Google', 'Runoob', 1997, 2000]
  list2 = [1, 2, 3, 4, 5 ]
  list3 = ["a", "b", "c", "d"]
  ```

#### 单个元素操作

##### 增

list.append(obj)

list.insert(index, obj)

##### 删

1. list.pop([index=-1])
   - index -- 可选参数，要移除列表元素的索引值，不能超过列表总长度，默认为 index=-1，删除最后一个列表值。

2. list.remove(obj)

3. delete list[index]
   - 移除列表中某个值的第一个匹配项

```python
#!/usr/bin/python3

list1 = ['Google', 'Runoob', 'Taobao']
list1.pop()
print ("列表现在为 : ", list1)
list1.pop(1)
print ("列表现在为 : ", list1)
```

以上实例输出结果如下：

```python
列表现在为 :  ['Google', 'Runoob']
列表现在为 :  ['Google']
```

##### 改

list[index] = xxx

##### 查

list.index(obj)

- 从列表中找出某个值第一个匹配项的索引位置

#### 列表之间操作

##### 增

1. list + list

   ```python
   [1, 2, 3] + [4, 5, 6]
   ```

2. list.extend(seq)

   - 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）

#### 其他

| 序号 | 函数                                                         |
| :--- | :----------------------------------------------------------- |
| 1    | [len(list)](https://www.runoob.com/python3/python3-att-list-len.html) 列表元素个数 |
| 2    | [max(list)](https://www.runoob.com/python3/python3-att-list-max.html) 返回列表元素最大值 |
| 3    | [min(list)](https://www.runoob.com/python3/python3-att-list-min.html) 返回列表元素最小值 |
| 4    | [list(seq)](https://www.runoob.com/python3/python3-att-list-list.html) 将元组转换为列表 |
| 5    | [list.clear()](https://www.runoob.com/python3/python3-att-list-clear.html) 清空列表 |
| 6    | [list.copy()](https://www.runoob.com/python3/python3-att-list-copy.html) 复制列表 |
| 7    | [list.count(obj)](https://www.runoob.com/python3/python3-att-list-count.html) 统计某个元素在列表中出现的次数 |

### Tuple（元组）

- Python 的元组与列表类似，不同之处在于元组的元素不能修改。
- 元组使用小括号 **( )**，列表使用方括号 **[ ]**。

#### 创建

元组中只包含一个元素时，需要在元素后面添加逗号 **,** ，否则括号会被当作运算符使用

```python
tup1 = () #创建空元组
tup2 = (50,) #创建单元素元组
tup1 = ('Google', 'Runoob', 1997, 2000)
```

#### 查找

元组可以使用下标索引来访问元组中的值，如下实例:

```python
#!/usr/bin/python3
 
tup1 = ('Google', 'Runoob', 1997, 2000)
tup2 = (1, 2, 3, 4, 5, 6, 7 )
 
print ("tup1[0]: ", tup1[0])
print ("tup2[1:5]: ", tup2[1:5])
```

#### 修改

元组中的元素值是不允许修改的，但我们可以对元组进行连接组合，如下实例:

```python
#!/usr/bin/python3
 
tup1 = (12, 34.56)
tup2 = ('abc', 'xyz')
 
# 以下修改元组元素操作是非法的。
# tup1[0] = 100
 
# 创建一个新的元组
tup3 = tup1 + tup2
print (tup3)
```

#### 删除

元组中的元素值是不允许删除的，但我们可以使用del语句来删除整个元组，如下实例:

```python
#!/usr/bin/python3
 
tup = ('Google', 'Runoob', 1997, 2000)
 
print (tup)
del tup
```

#### 元组运算符

| Python 表达式                  | 结果                         | 描述         |
| :----------------------------- | :--------------------------- | :----------- |
| len((1, 2, 3))                 | 3                            | 计算元素个数 |
| (1, 2, 3) + (4, 5, 6)          | (1, 2, 3, 4, 5, 6)           | 连接         |
| ('Hi!',) * 4                   | ('Hi!', 'Hi!', 'Hi!', 'Hi!') | 复制         |
| 3 in (1, 2, 3)                 | True                         | 元素是否存在 |
| for x in (1, 2, 3): print (x,) | 1 2 3                        | 迭代         |

#### 元组索引，截取

因为元组也是一个序列，所以我们可以访问元组中的指定位置的元素，也可以截取索引中的一段元素，如下所示：

`tup = ('Google', 'Runoob', 'Taobao', 'Wiki', 'Weibo','Weixin')`

| Python 表达式 | 结果                                            | 描述                                             |
| :------------ | :---------------------------------------------- | :----------------------------------------------- |
| tup[1]        | 'Runoob'                                        | 读取第二个元素                                   |
| tup[-2]       | 'Weibo'                                         | 反向读取，读取倒数第二个元素                     |
| tup[1:]       | ('Runoob', 'Taobao', 'Wiki', 'Weibo', 'Weixin') | 截取元素，从第二个开始后的所有元素。             |
| tup[1:4]      | ('Runoob', 'Taobao', 'Wiki')                    | 截取元素，从第二个开始到第四个元素（索引为 3）。 |



### Dictionary（字典）

字典是另一种可变容器模型，且可存储任意类型对象。

字典的每个键值 **key=>value** 对用冒号 **:** 分割，每个对之间用逗号(**,**)分割，整个字典包括在花括号 **{}** 中

#### 查找

把相应的键放入到方括号中，如下实例:

```python
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
print ("dict['Name']: ", dict['Name'])
print ("dict['Age']: ", dict['Age'])
```

#### 增加与修改

新添加的键值对在原字典中不存在，即为添加；新添加的键值对在原字典存在，即为修改

```python
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
dict['Age'] = 8               # 更新 Age
dict['School'] = "菜鸟教程"  # 添加信息
 
 
print ("dict['Age']: ", dict['Age'])
print ("dict['School']: ", dict['School'])
```

#### 删除字典元素

能删单一的元素也能清空字典，清空只需一项操作。

显示删除一个字典用del命令，如下实例：

```python
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
del dict['Name'] # 删除键 'Name'
dict.clear()     # 清空字典
del dict         # 删除字典
```

#### 字典内置函数&方法

Python字典包含了以下内置函数：

| 序号 | 函数及描述                                                   | 实例                                                         |
| :--- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| 1    | len(dict) 计算字典元素个数，即键的总数。                     | `>>> dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'} >>> len(dict) 3` |
| 2    | str(dict) 输出字典，以可打印的字符串表示。                   | `>>> dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'} >>> str(dict) "{'Name': 'Runoob', 'Class': 'First', 'Age': 7}"` |
| 3    | type(variable) 返回输入的变量类型，如果变量是字典就返回字典类型。 | `>>> dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'} >>> type(dict) <class 'dict'>` |

Python字典包含了以下内置方法：

| 序号 | 函数及描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | [radiansdict.clear()](https://www.runoob.com/python3/python3-att-dictionary-clear.html) 删除字典内所有元素 |
| 2    | [radiansdict.copy()](https://www.runoob.com/python3/python3-att-dictionary-copy.html) 返回一个字典的浅复制 |
| 3    | [radiansdict.fromkeys()](https://www.runoob.com/python3/python3-att-dictionary-fromkeys.html) 创建一个新字典，以序列seq中元素做字典的键，val为字典所有键对应的初始值 |
| 4    | [radiansdict.get(key, default=None)](https://www.runoob.com/python3/python3-att-dictionary-get.html) 返回指定键的值，如果键不在字典中返回 default 设置的默认值 |
| 5    | [key in dict](https://www.runoob.com/python3/python3-att-dictionary-in.html) 如果键在字典dict里返回true，否则返回false |
| 6    | [radiansdict.items()](https://www.runoob.com/python3/python3-att-dictionary-items.html) 以列表返回一个视图对象 |
| 7    | [radiansdict.keys()](https://www.runoob.com/python3/python3-att-dictionary-keys.html) 返回一个视图对象 |
| 8    | [radiansdict.setdefault(key, default=None)](https://www.runoob.com/python3/python3-att-dictionary-setdefault.html) 和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default |
| 9    | [radiansdict.update(dict2)](https://www.runoob.com/python3/python3-att-dictionary-update.html) 把字典dict2的键/值对更新到dict里 |
| 10   | [radiansdict.values()](https://www.runoob.com/python3/python3-att-dictionary-values.html) 返回一个视图对象 |
| 11   | [pop(key[,default\])](https://www.runoob.com/python3/python3-att-dictionary-pop.html) 删除字典给定键 key 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回default值。 |
| 12   | [popitem()](https://www.runoob.com/python3/python3-att-dictionary-popitem.html) 随机返回并删除字典中的最后一对键和值。 |



### Set（集合）

集合（set）是一个无序的不重复元素序列。

#### 创建

可以使用大括号 **{ }** 或者 **set()** 函数创建集合，注意：创建一个空集合必须用 **set()** 而不是 **{ }**，因为 **{ }** 是用来创建一个空字典。

```python
parame = {value01,value02,...}
pax = set(value)
```

#### 增加

1. add()  添加单个元素

   ```python
   >>> thisset = set(("Google", "Runoob", "Taobao"))
   >>> thisset.add("Facebook")
   ```

2. update()  参数可以是列表，元组，字典等

   ```python
   >>> thisset = set(("Google", "Runoob", "Taobao"))
   >>> thisset.update({1,3})
   ```

#### 删除

1. remove()  将元素 x 从集合 s 中移除，如果元素不存在，则会发生错误。

   ```python
   >>> thisset = set(("Google", "Runoob", "Taobao"))
   >>> thisset.remove("Taobao")
   ```

2. discard()  移除集合中的元素，且如果元素不存在，不会发生错误。

   ```python
   >>> thisset = set(("Google", "Runoob", "Taobao"))
   >>> thisset.discard("Facebook")  # 不存在不会发生错误
   ```

#### 集合内置方法完整列表

| 方法                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [add()](https://www.runoob.com/python3/ref-set-add.html)     | 为集合添加元素                                               |
| [clear()](https://www.runoob.com/python3/ref-set-clear.html) | 移除集合中的所有元素                                         |
| [copy()](https://www.runoob.com/python3/ref-set-copy.html)   | 拷贝一个集合                                                 |
| [difference()](https://www.runoob.com/python3/ref-set-difference.html) | 返回多个集合的差集                                           |
| [difference_update()](https://www.runoob.com/python3/ref-set-difference_update.html) | 移除集合中的元素，该元素在指定的集合也存在。                 |
| [discard()](https://www.runoob.com/python3/ref-set-discard.html) | 删除集合中指定的元素                                         |
| [intersection()](https://www.runoob.com/python3/ref-set-intersection.html) | 返回集合的交集                                               |
| [intersection_update()](https://www.runoob.com/python3/ref-set-intersection_update.html) | 返回集合的交集。                                             |
| [isdisjoint()](https://www.runoob.com/python3/ref-set-isdisjoint.html) | 判断两个集合是否包含相同的元素，如果没有返回 True，否则返回 False。 |
| [issubset()](https://www.runoob.com/python3/ref-set-issubset.html) | 判断指定集合是否为该方法参数集合的子集。                     |
| [issuperset()](https://www.runoob.com/python3/ref-set-issuperset.html) | 判断该方法的参数集合是否为指定集合的子集                     |
| [pop()](https://www.runoob.com/python3/ref-set-pop.html)     | 随机移除元素                                                 |
| [remove()](https://www.runoob.com/python3/ref-set-remove.html) | 移除指定元素                                                 |
| [symmetric_difference()](https://www.runoob.com/python3/ref-set-symmetric_difference.html) | 返回两个集合中不重复的元素集合。                             |
| [symmetric_difference_update()](https://www.runoob.com/python3/ref-set-symmetric_difference_update.html) | 移除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合中不同的元素插入到当前集合中。 |
| [union()](https://www.runoob.com/python3/ref-set-union.html) | 返回两个集合的并集                                           |
| [update()](https://www.runoob.com/python3/ref-set-update.html) | 给集合添加元素                                               |

## 运算符

------

### 算数运算符

重点是**/**、**//**、******

以a=10，b=21为例

| +      | 加 - 两个对象相加                               | a + b 输出结果 31  |
| ------ | ----------------------------------------------- | ------------------ |
| -      | 减 - 得到负数或是一个数减去另一个数             | a - b 输出结果 -11 |
| *      | 乘 - 两个数相乘或是返回一个被重复若干次的字符串 | a * b 输出结果 210 |
| **/**  | 除 - x 除以 y                                   | b / a 输出结果 2.1 |
| %      | 取模 - 返回除法的余数                           | b % a 输出结果 1   |
| ****** | 幂 - 返回x的y次幂                               | a**b 为10的21次方  |
| **//** | 取整除 - 向下取接近商的整数                     | b // a 输出结果 2  |

### 赋值运算符

重点为**海象运算符**，不过一般应该不能用，毕竟3.8之后版本才能用

以下假设变量a为10，变量b为20：

| =    | 简单的赋值运算符                                             | c = a + b 将 a + b 的运算结果赋值为 c |
| ---- | ------------------------------------------------------------ | ------------------------------------- |
| +=   | 加法赋值运算符                                               | c += a 等效于 c = c + a               |
| -=   | 减法赋值运算符                                               | c -= a 等效于 c = c - a               |
| *=   | 乘法赋值运算符                                               | c *= a 等效于 c = c * a               |
| /=   | 除法赋值运算符                                               | c /= a 等效于 c = c / a               |
| %=   | 取模赋值运算符                                               | c %= a 等效于 c = c % a               |
| **=  | 幂赋值运算符                                                 | c **= a 等效于 c = c ** a             |
| //=  | 取整除赋值运算符                                             | c //= a 等效于 c = c // a             |
| :=   | 海象运算符，可在表达式内部为变量赋值。**Python3.8 版本新增运算符**。 | num=34; if num>30: => if(num:=34)>30: |

### 比较运算符

返回结果为bool类型

1. **==**  
2. **!=**  
3. **>**  
4. **>=**  
5. **<**  
6. **<=**

### 位运算符

按位运算符是把数字看作二进制来进行计算的

下表中变量 a 为 60，b 为 13二进制格式如下：

```python
a = 0011 1100

b = 0000 1101

-----------------

a&b = 0000 1100

a|b = 0011 1101

a^b = 0011 0001

~a  = 1100 0011
```

| 运算符 | 描述                                                         | 示例                                                         |
| ------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| &      | 按位与运算符：参与运算的两个值,如果两个相应位都为1,则该位的结果为1,否则为0 | (a & b) 输出结果 12 ，二进制解释： 0000 1100                 |
| \|     | 按位或运算符：只要对应的二个二进位有一个为1时，结果位就为1。 | (a \| b) 输出结果 61 ，二进制解释： 0011 1101                |
| ^      | 按位异或运算符：当两对应的二进位相异时，结果为1              | (a ^ b) 输出结果 49 ，二进制解释： 0011 0001                 |
| ~      | 按位取反运算符：对数据的每个二进制位取反,即把1变为0,把0变为1。**~x**类似于 **-x-1** | (~a ) 输出结果 -61 ，二进制解释： 1100 0011， 在一个有符号二进制数的补码形式。 |
| <<     | 左移动运算符：运算数的各二进位全部左移若干位，由"<<"右边的数指定移动的位数，高位丢弃，低位补0。 | a << 2 输出结果 240 ，二进制解释： 1111 0000                 |
| >>     | 右移动运算符：把">>"左边的运算数的各二进位全部右移若干位，">>"右边的数指定移动的位数 | a >> 2 输出结果 15 ，二进制解释： 0000 1111                  |

### 逻辑运算符

- and
- or
- not

### 成员运算符

- in
- not in

### 身份运算符

- is
- is not

### 运算符优先级





## 函数



### 定义函数

在Python中，定义一个函数要使用`def`语句，依次写出函数名、括号、括号中的参数和冒号`:`，然后，在缩进块中编写函数体，函数的返回值用`return`语句返回。

如果想定义一个什么事也不做的空函数，可以用`pass`语句，空函数缺少了`pass`，代码运行就会有语法错误。

如果函数实现中没有return，函数执行完毕后也会返回结果，只是结果为`None`。`return None`可以简写为`return`。

```python
def my_abs(x):
    if x >= 0:
        return x
    else:
        return -x
```

```python
def nop():
    pass
```

```python
if age >= 18:
    pass
```

### 函数的参数

#### 1.必选参数

```python
def power(x):
    return x * x
```

#### 2.默认参数

```python
def power(x, n=2):
    s = 1
    while n > 0:
        n = n - 1
        s = s * x
    return s
```

#### 3.可变参数

可变参数就是传入的参数个数是可变的，可以是1个、2个到任意个，还可以是0个。

```python
def calc(*numbers):
    sum = 0
    for n in numbers:
        sum = sum + n * n
    return sum
```

在函数内部，参数`numbers`接收到的是一个tuple，调用该函数时，可以传入任意个参数，包括0个参数：

```python
>>> calc(1, 2)
5
>>> calc()
0
```

如果已经有一个list或者tuple，要调用一个可变参数怎么办？可以这样做：

```python
>>> nums = [1, 2, 3]
>>> calc(nums[0], nums[1], nums[2])
14
```

这种写法当然是可行的，问题是太繁琐，所以Python允许你在list或tuple前面加一个`*`号，把list或tuple的元素变成可变参数传进去：

```python
>>> nums = [1, 2, 3]
>>> calc(*nums)
14
```

#### 4.关键字参数

可变参数允许你传入0个或任意个参数，这些可变参数在函数调用时自动组装为一个tuple。而关键字参数允许你传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装为一个dict

可变参数在参数中加一个*，关键字参数在参数中加两个*

```python
def person(name, age, **kw):
    print('name:', name, 'age:', age, 'other:', kw)
```

```python
>>> person('Bob', 35, city='Beijing')
name: Bob age: 35 other: {'city': 'Beijing'}
>>> person('Adam', 45, gender='M', job='Engineer')
name: Adam age: 45 other: {'gender': 'M', 'job': 'Engineer'}
```

当然，上面复杂的调用可以用简化的写法：

```python
>>> extra = {'city': 'Beijing', 'job': 'Engineer'}
>>> person('Jack', 24, **extra)
name: Jack age: 24 other: {'city': 'Beijing', 'job': 'Engineer'}
```

#### 5.命名关键字参数

如果要限制关键字参数的名字，就可以用命名关键字参数，例如，只接收`city`和`job`作为关键字参数。这种方式定义的函数如下：

```python
def person(name, age, *, city, job):
    print(name, age, city, job)
```

和关键字参数`**kw`不同，命名关键字参数需要一个特殊分隔符`*`，`*`后面的参数被视为命名关键字参数。

如果函数定义中已经有了一个可变参数，后面跟着的命名关键字参数就不再需要一个特殊分隔符`*`了：

```python
def person(name, age, *args, city, job):
    print(name, age, args, city, job)
```

### 返回值

#### 返回多个值

返回值是一个tuple，无论是单返回值还是多返回值，返回一个tuple可以省略括号，而多个变量可以同时接收一个tuple，所以，Python的函数返回多值其实就是返回一个tuple，但写起来更方便。

按位置赋给对应的值：

```python
import math

def move(x, y, step, angle=0):
    nx = x + step * math.cos(angle)
    ny = y - step * math.sin(angle)
    return nx, ny
```

```python
>>> x, y = move(100, 100, 60, math.pi / 6)
>>> print(x, y)
151.96152422706632 70.0
```

或

```python
>>> r = move(100, 100, 60, math.pi / 6)
>>> print(r)
(151.96152422706632, 70.0)
```



## 面向对象

------





