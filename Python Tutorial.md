# Python Learning

> Credit to Original Author: Wei Zhang, Haochen Wang

* 字符串格式化
* 字符串.zfill()
* 字符串.split()
* 字符串.join()
* 列表的深复制和浅复制
* 列表的排序.sort(), .sorted()
* 继承与多态

## 1. 数据类型
Python包含五种主要的数据类型，分别是

-   Numbers(数字)
-   String(字符串)
-   List(列表)
-   Tuple(元组)
-   Dictionary(字典)

### Section 3.1: 数字Numbers
Python包含三种主要的数字类型，分别是：

-   Int (整形)
-   Float (浮点型)
-   Complex（复数型）

赋值的方法如下:

```py
a = 3000           #整形变量
b = 2000.0         #浮点型变量
c = 3e9            #整形变量，即3*10^9
d = 3.14j          #复数性变量
```

当然，也可以使用其它进制数对变量进行赋值，如：

```py
a = 0b11           #整形变量，二进制数
b = 0o76           #整型变量，八进制数
c = 0xef           #整型变量，十六进制数
```

那么，如何进行各进制数之间的转换呢？

-   使用``bin()``方法把任意进制数转化为二进制数;
-   使用``oct()``方法把任意进制数转化为八进制数;
-   使用``int()``方法把任意进制数转化为十进制数;
-   使用``hex()``方法把任意进制数转化为十六进制数;

> 小贴士： 除使用``int()``转换结果为整型以外，其它转换结果全部为字符串；

### Section 3.2: 字符串与列表

#### 3.2.1 字符串String
字符串是以单引号('')，或双引号("")括起来的一段文本，但引号不包含在字符串范围内。如果在字符串内部也有引号的话，需要添加'或''  

如：

```py
print('I\'m \"OK\"!')
I'm "OK"!
```

如果在一个字符串内需要换行，可以用以下形式表示：

```py
print('''line1
... line2
... line3''')
```

则会显示：

```sh
line1
line2
line3
```
#### 字符串格式化
```
print("I'm %s. I'm %d year old" % ('Vamei', 99))
```

#### 3.2.2 列表List

列表是python中最常用的数据类型，在一个列表中，可以存储多种数据格式，如string，int，也可以是list本身；列表的使用非常灵活，列表中的每个元素甚至可以存储不同的数据类型，每个元素的大小也不尽相同。如：

```py
a = []   #初始化空列表
a.append(1)  #为列表添加一个数据元素
a.append('s') #为列表添加一个字符串
a.append([1,'s']) #为列表添加一个列表元素
```

我们可以在spyder中观察该列表的数据类型如下：  

![avatar](2.png)  

在Type一栏中，我们发现该List有三种不同的数据类型；从Size一栏，我们发现该List每个元素的大小也有所不同；

#### 3.2.3 列表的初始化

可以用以下方式初始化一个列表：

```py
classmates = ['Michael', 'Bob', 'Tracy']
```

也可以初始化一个空列表，然后不断添加元素，如：

```py
classmates = []
classmates.append('Michael')
classmates.append('Bob')
classmates.append('Tracy')
```

#### 3.2.4 列表的访问

可以通过列表索引访问列表中的元素，列表索引从0开始。如：

```py
classmates = ['Michael', 'Bob', 'Tracy']
print(classmates[0])

# 输出结果：
Michael
```

如果要访问多个列表元素，可以使用以下方式：

```py
classmates = ['Michael', 'Bob', 'Tracy']
print(classmates[0:2])
```

输出的结果如下，**需要注意的是访问的元素是从索引范围起始到索引范围终止前一位的元素**，这里就是访问的列表内索引为0和1的两个元素。

```py
['Michael', 'Bob']
```

当然，也可以访问多维list。比如在下面的例子中，Michael和Tracy在一起了，于是我们为他们设置了一个单独的list，这时我们可以通过以下方式访问Michael：

```py
classmates = [['Michael','Tracy'], 'Bob']
print(classmates[0][0])

# 输出结果：
Michael
```

除此之外，python还支持从后向前访问元素，如下面的例子，会输出倒数第一个元素

```py
classmates = ['Michael', 'Bob', 'Tracy']
print(classmates[-1])

# 输出结果：
Tracy
```

#### 3.2.5列表的插入、删除  

列表的插入和删除可以参考以下的例子：

```py
# 插入操作
classmates = ['Michael', 'Bob', 'Tracy']
classmates.insert(1, 'Jack') # 这里会把'Jack'添加到索引为1的位置
print(classmates)  

# 输出结果：
['Michael', 'Jack', 'Bob', 'Tracy']

# 删除操作
classmates.pop(1)  # 这里会把索引为1的元素删除
print(classmates)

# 输出结果：
['Michael', 'Bob', 'Tracy']
```

> 小贴士：需要注意的是，在插入和删除元素后，List元素的索引也会随之改变，在写循环时要小心这一点。

### Section 3.3: 元组Tuple

Tuple与List有一定的相似之处，但最大的不同之处在于，Tuple一旦定义，则无法修改。  

Tuple的初始化方法如下：

```py
classmates = ('Michael', 'Bob', 'Tracy')
```

Tuple的访问方法与List相同，只是无法进行修改；因此，相比于List，Tuple对于工程项目而言更加安全。不过，Tuple本身虽然无法修改，但如果在Tuple内嵌套List，则可以修改List内的元素，如下面的例子：

```py
classmates = (['Michael', 'Tracy'],'Bob')
classmates[0][0] = 'Jack'
print(classmates)

# 输出结果：
(['Jack', 'Tracy'], 'Bob')
```

但本质上来说，这个例子并没有修改Tuple本身，Tuple依旧没有改变。

### Section 3.4: 字典Dict

Dict变量包含key和value两部分，其基本格式为：

```py
d = {key1 : value1, key2 : value2 }
```

Key一般是唯一的，value可以不唯一，以下是dict的一个常见示例：

```py
dict = {'a': 1, 'b': 2, 'b': '3'} #key唯一，故若多次赋值，则以后赋值为准；
print(dict['b'])

# 输出结果：
3
```

```py
print(dict)
# 输出结果:
{'a': 1, 'b': '3'}
```

这里是一个dict的插入和删除示例，dict可以直接添加未出现的key，删除需要用到del命令。

```py
dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
dict['School'] = "RUNOOB" # 插入
print(dict)

# 输出结果：
{'Name': 'Zara', 'Age': 7, 'Class': 'First', 'School': 'RUNOOB'}

del dict['Name']
print(dict)

# 输出结果：
{'Age': 7, 'Class': 'First', 'School': 'RUNOOB'}
```

## Section 4: 条件、循环

### Section 4.1: 条件语句

Python中的条件语句按照以下的语法规则书写：
```py
if <条件判断1>:
    <执行1>
elif <条件判断2>:
    <执行2>
elif <条件判断3>:
    <执行3>
else:
    <执行4>
```
这里是一个具体的例子：
```py
age = 3
if age >= 18:
    print('adult')
elif age >= 6:
    print('teenager')
else:
    print('kid')

\# 输出如下：
kid
```
当然，``elif``与``else``并不是必须的，你也可以不使用它们。

### Section 4.2: for - in 循环语句

for-in循环语句会将一个向量中的第一个维度中的每个元素循环一遍，如下面的例子中，我们将名为names的列表中的每一个元素都遍历了一遍，然后把每个元素都打印了出来。
```py
names = ['Michael', 'Bob', 'Tracy']
for name in names:
    print(name)

# 输出如下：
Michael
Bob
Tracy
```
一个for-in语句只会遍历一个维度的每一个元素，如下面的例子中，for-in循环只遍历了第一个维度的每一个元素:
```py
names = \[\['Michael','Tracy'\],\['Bob', 'Lucy'\]\]
for name in names:
    print(name)

\# 输出如下：
\['Michael', 'Tracy'\]
\['Bob', 'Lucy'\]
```
当然也可以将多个for-in语句嵌套使用，如：
```py
names = \[\['Michael','Tracy'\],\['Bob', 'Lucy'\]\]
for name in names:
    print(name)

#输出如下：
\['Michael', 'Tracy'\]
\['Bob', 'Lucy'\]

for name in names:
    for sub_name in name:
             print(sub_name)

\# 输出如下：
Michael
Tracy
Bob
Lucy
```
如果要同时循环两个list，如何实现？

### Section 4.3: while循环语句

while循环语句的写法与其它语言没有太多差别，这里给出一个基本的例子：

i = 0
while i < 3:
	print(i)
	i = i + 1

\# 输出如下：
0
1
2

> 需要提醒大家的是，写各个语句的时候一定不能缺少冒号，且每一层循环中缩进需要保持一致。

### Section 4.4: break、continue语句

break与continue语句用法和C语言基本相同。  
break语句执行会使得程序跳出循环。

\# break
i = 0
while i < 100:
    if i > 2:
        break  #在第三次循环break
    print(i)
    i = i + 1

\# 输出如下：
0
1
2

continue语句的执行会使得程序跳出本层循环。如下面这个例子中，本应输出数字1的语句被跳过，故只输出了数字2和3。

\# continue
i = 0
while i < 3:
    i = i + 1
    if i == 1:
        continue #在第一次循环直接跳入下一次循环
    print(i)

\# 输出如下：
2
3

## Section 5: 函数

### Section 5.1: 函数定义

如我们要简单定义一个加法函数，则格式如下所示，需要在函数开头声明中添加def关键字，并声明传入参数。需要说明的是，python并不要求在开头声明输出参数，只需要在return语句后声明输出参数即可。不要忘记在声明的最后添加冒号。

def sum(a,b): #参数a和b传入函数
\# 函数功能:对a和b求和。
\# 函数输入：a,b
\# 函数输出：c
    c = a + b
    return c #返回参数c

如果要一次性的返回多个函数值，则可以在return后依次排出多个参数的变量名。

def sum_multi(a,b):
\# 函数功能：对a和b求和求积
\# 函数输入：a,b
\# 函数输出：c,d
    c = a + b
    d = a * b
    return c,d   #同时返回参数c与d

### Section 5.2: 函数调用

调用函数时，通常来说输入参数个数与类型要与定义函数时相符合，如下面的例子中，调用sum函数和sum_multi函数传入了两个数字型参数，因此，在主函数中，也需要对应两个数字型参数。

def sum(a,b): #参数a和b传入函数
    c = a + b
    return c #返回参数c

def sum_multi(a,b):
    c = a + b
    d = a * b
    return c,d   #同时返回参数c与d

a = 2
b = 3
c = sum(a,b) #调用函数sum
print(c)
c,d = sum_multi(a,b) #调用多输出函数sum_multi
print(c,d)

\# 输出如下：
5
5,6

如果传入参数数量与类型不一致，则会出现个数不等报错：

sum(1)
Traceback (most recent call last):

  File "<ipython-input-11-5771d20eddf7>", line 1, in <module>
    sum(1)

TypeError: sum() missing 1 required positional argument: 'b'

或是类型不符报错：

sum(\[1,2\],1)
Traceback (most recent call last):

  File "<ipython-input-12-9d5b8cbaffec>", line 1, in <module>
    sum(\[1,2\],1)

  File "<ipython-input-8-45a3b49d1785>", line 2, in sum
    c = a + b

TypeError: can only concatenate list (not "int") to list

还需要注意的是，函数传入参数是按照顺序排列的，如下面的例子中，由于顺序的问题，将主程序中b的值传给了函数里的a，主程序中a的值传给了函数里的b，因此相减结果为-1。

def minus(a,b):
    c = a - b
    return c
a = 3
b = 2
c = minus(b,a)
print(c)

\# 输出结果：
-1

### Section 5.3: 函数参数传递

在python中，strings, tuples, 和 numbers 是不可更改的对象，而 list，dict 等则是可以更改的对象。以下两个例子将说明对这两类对象在函数中做出修改后的结果：

def ChangeInt( a ):
    a = 10

b = 2
ChangeInt(b)
print(b)  

\# 输出如下：
2               #注意到对象b并未被改变

def changeme( mylist ):
   mylist.append(\[1,2,3,4\])
   return

mylist = \[10,20,30\]
changeme( mylist )
print(mylist)

\# 输出如下：
\[10, 20, 30, \[1, 2, 3, 4\]\]   #注意到list发生改变

写程序时需要注意list,dict是在函数中会被修改的对象，以免出现错误。

### Section 5.4: 关键字参数、默认参数、不定长参数

以下是三类特殊函数传递的实例，希望给大家做一参考。  

在前面的例子中，参数需要按顺序传入，但是关键字传入参数仅与关键字相互对应。下面的例子说明了如何设置关键字参数：

\## 关键字参数：参数传递与关键字匹配，与顺序无关
def printinfo( name, age ):
   print("Name: ", name)
   print("Age: ", age)
   return

printinfo(age = 50, name = "miki")  

\# 输出如下：
Name:  miki
Age:  50

在函数定义时，可以直接设置默认参数。如果设置了默认参数，则可以在主函数中不传递这个参数，以函数定义时的默认值为准；但若主程序中给定了这个参数的值，则函数运行时以主程序给定的参数值为准。我们可以看下面的例子：

\## 默认参数： 初始化函数参数值，允许在主函数中不输入该参数
def printinfo( name, age = 35):
   print("Name: ", name)
   print("Age: ", age)
   return;

printinfo(name = "miki")   #会输出默认参数
printinfo(name = "miki", age = 50)  #会输出重新定义参数

\# 输出如下：
Name:  miki
Age:  35
Name:  miki
Age:  50

这里是一个很有意思的应用，可以向函数里传递不定长度的一到N个参数，下面的例子中，主程序可以向函数传递一个参数，也可以向函数传递多个参数。

\## 不定长参数：允许传入长度不定的参数值
def printinfo( arg1, *vartuple ):
   print(arg1)
   for var in vartuple:
      print(var)
   return

printinfo( 10 )
printinfo( 70, 60, 50 )

\# 输出如下：
10
70
60
50

## Section 6： lambda表达式及一些其它语法知识点

### Section 6.1: lambda表达式

Lambda表达式是一种简写的函数形式，可以使得程序更紧致。lambda表达式的基本形式是：

  lambda argument_list: expression

这里，使用lambda关键字后，先需要声明传入参数，然后声明对传入参数所完成的操作。  
比如，我们可以用lambda表达式完成一个加法函数的功能。

add = lambda x, y : x+y
add(1,2)

\# 输出结果：
3

### Section 6.2: lambda表达式与map，reduce，filter以及sorted的配合使用

Lambda表达式可以和其它函数配合使用，从而用非常简洁的一句话实现一些函数功能，例如：

#### 和map()配合使用

![avatar](3.png)  

map()函数可以将一个list中的所有元素都执行某个函数操作，与lambda表达式相结合，可以用一句简单的代码执行本应需要几行代码才能完成的功能，例如将一个list中所有tuple中的第一个元素取出：

\# 该程序可以将a中所有tuple的第一个元素取出
a = \[('a',1),('b',2),('c',3),('d',4)\]
a_1 = list(map(lambda x:x\[0\],a))  
print(a_1)

\# 输出结果：
\['a', 'b', 'c', 'd'\]

#### 和filter()配合使用  

![avatar](4.png)  

filter()函数可以将list中满足某个条件的元素筛选出来，我们可以和lambda表达式结合，筛选出一个list中所有小于4的数字：

\# 该程序会将list中所有小于4的数筛选出来
a = \[1,2,3,4,5,6,7\]
a_1 = list(filter(lambda x:x<4,a))
print(a_1)

\# 输出结果：
\[1, 2, 3\]

#### 和reduce()配合使用 

![avatar](5.png)  

reduce()函数是对序列中的元素进行累计操作，下面这个例子将一个list中所有元素进行累加：

#该程序会将list中所有元素累加起来
from functools import reduce
a = \[1,2,3,4,5,6,7\]
a_1 = int(reduce(lambda x,y:x+y,a))
print(a_1)

\# 输出结果：
28

#### 和sorted()配合使用 

sorted()函数是对list元素按照lambda表达式给定规律进行排序，因此可以和lambda表达式结合，对一个list中所有元素距离5的远近进行从近到远排序：

#该程序会将list中所有元素按照距离5的远近进行排序
a = \[1, 2, 3, 4, 5, 6, 7, 8, 9\]
a_1 = sorted(a, key=lambda x: abs(5-x))
print(a_1)

\# 输出结果：
\[5, 4, 6, 3, 7, 2, 8, 1, 9\]

### Section 6.3: set()

set()会创建一个无序不重复集合，可以认为set是dict中的key这一部分，即set中的每一个元素都是一个key，元素之间不会相互重复。如果对一个字符串做set运算，则会把重复字符删去；以下是关于set的一个实例：

>>> x = set('runoob')
>>> y = set('google')
>>> x, y
(set(\['b', 'r', 'u', 'o', 'n'\]), set(\['e', 'o', 'g', 'l'\]))   \# 重复的被删除
>>> x & y         \# 交集
set(\['o'\])
>>> x | y         \# 并集
set(\['b', 'e', 'g', 'l', 'o', 'n', 'r', 'u'\])
>>> x - y         \# 差集
set(\['r', 'b', 'u', 'n'\])

## Section 7: Python的类及其特性

作为一种面向对象的语言，类是python中一个重要的概念。类是一个模板，想要使用类就必须要将其实例化。实例化的类被称为对象。由一个类生成的众多对象有相同的方法，但是各自的数据可能不同。  

在python中，通过关键词**class**来定义一个类。通过.来给类绑定各种属性。下面的例子创建了一个叫做Animal的类，并生成一个实例。

```py
class dog():
  pass

haski = dog()
haski.name = "Tom"

print(dog)
print(haski)
print(haski.name)
```

输出如下：

```py
<class '__main__.dog'>
<__main__.dog object at 0x000002867C315E10>
Tom
```

在上例中，我们通过关键词class定义了一个叫做dog的类，直接输出dog的结果显示它为一个类。接下来通过dog类创造出一个实例haski，并赋予其名字"Tom"。直接输出haski则显示的是它的地址。  

通过``__init__()``方法，我们可以在创建类的时候就把想要的属性绑定上去，下面通过``__init__()``方法将名字等属性绑定到dog类上，``__init__()``的写法与函数的写法类似，通过def来定义。

```py
class dog():
  def __init__(self, name = "Tom", gender = "Male"):
    self.name = name
    self.gender = gender

haski1 = dog()
print(haski1.name)
print(haski1.gender)

haski2 = dog("Ada", "Female")
print(haski2.name)
print(haski2.gender)
```

输出如下：

```py
Tom
Male

Ada
Female
```

在上例中，我们在类中通过``__init__()``定义了name和gender两个属性，并给予初始值"Tom"和"Male"，如果我们在后面的类实例化中没有传参，那么将会使用这两个默认的参数。``__init__()``的第一个参数一定是self，表示创建的实例本身。haski1使用了默认参数。对于haski2，我们通过传参将其定义为一只名为Ada的母哈士奇。  

在类中，我们还可以定义各种各样的方法。方法的定义除了第一个参数仍为self外，其它与函数的定义完全相同。下面的例子我们给dog类附加run和bark的方法。

```py
class dog():
  def __init__(self, name = "Tom", gender = "Male"):
    self.name = name
    self.gender = gender
    self.sound = "wow, wow~~"

  def run(self):
    print("dog is running.")

  def bark(self):
    print(self.sound)

haski = dog()
print(haski.name, haski.gender)
haski.run()
haski.bark()
```

输出如下：

```py
Tom Male
dog is running.
wow, wow~~
```

使用类的一个好处是当我们需要定义一个新的类时，可以直接继承已有的类。新的class称为子类（Subclass），而被继承的class称为基类、父类或超类（Base class、Super class）。当我们定义一个类的时候，python3默认是继承python的object类。  

以下是对于继承的一个简单例子。

```py
# define a class named animal
class animal():
  def __init__(self, name):
    self.name = name

  def run(self):
    print("Animal is running......")

# define a new class named dog
class dog(animal):
  def run(self):
    print("dog is running.")

  def bark(self):
    print("wow, wow~~")

haski1 = animal("Tom")
haski2 = dog("Will")
print(dir(haski1))
print(dir(haski2))
print(haski1.name, haski2.name)
haski1.run()
haski2.run()
haski2.bark()
```

结果输出如下：

```py
# ...表示输出结果相同，这里省去不再占用篇幅
[..., 'name', 'run']
[..., 'bark', 'name', 'run']
Tom Will
Animal is running......
dog is running.
wow, wow~~
```

在上例中，我们首先生成了一个类``animal``，然后生成了它的子类``dog``，并通过``animal``和``dog``生成了两个实例``haski1``和``haski2``。类``dog``中并没有直接设置属性``name``，而可以从它的父类``animal``中继承``name``属性。而子类``dog``中的方法``run``与父类中的冲突，则直接覆盖了父类的方法。父类``animal``中没有方法``bark``，而子类``dog``中有。如果调用``haski1.bark()``，则会报错。  

## Section 8: 错误和异常处理

在程序运行过程中，如果出现错误，程序则会返回预先设计好的错误代码。语法错误（忘记加冒号等）是python常见的错误，在写代码时养成良好的习惯可以极大减少此类错误。即便python的语法是正确的，在运行它的时候也会出现各种各样的错误（除0错误等）。运行期检测到的错误被称为异常。  

错误和异常处理在程序设计中十分重要，当遇到程序错误或异常的时候，我们有时并不希望程序直接被杀掉，而是继续按照我们设定的方式运行下去。我们先介绍如何自定义和触发异常，然后介绍如何处理异常。  

当程序出现错误时，一般都是python自动的引发异常，我们也可以通过raise来引发自定义的异常。下面的例子将教给大家如何自定义异常并触发异常。假设我们通过设备接收外部参数parameter，parameter只能为0或1，0时处理fileOne，1时处理fileTwo，接收其它参数则认为是bug。

class parameterError(Exception):
    def \_\_init\_\_(self, message):
        self.message = message

parameter = 3
if parameter == 0:
  print("Now, processing fileOne......")
elif parameter == 1:
  print("Now, processing fileTwo......")
else:
  Emessage = r'''Parameter  must be 0 or 1!'''
  raise parameterError(Emessage)

我们首先定义了一个parameterError的类，继承于Exception。触发自定义的异常需要先自定义类似的一个类，然后在程序中使用raise。若运行上面的代码，则会触发以下的异常。

parameterError: Parameter  must be 0 or 1!

如果我们事前知道可能会出现的异常，并知道如何处理，那么就可以使用try语句来处理异常。try语句的语法如下：

try:
  可能会出错的代码
except：
  错误处理代码
finally：
  最后的语句

try中代码是可能出错的代码，except语句中有已经定义好的异常（可以是多个异常），如果出现了相应的错误，则会调到except语句执行，最后执行finally语句（finally可有可无，但如果有的话则一定会执行）。假如我们有一段代码需要执行，代码中可能出现除0错误(ZeroDivisionError)和变量错误(TypeError)，下面的代码演示了如何去用try去处理这些错误。

try:
  a = "10"
  \# a = 0
  b = 100/a
except TypeError as e:
    print('TypeError message is:', e)
    a = int(a)
    b =100/a
except ZeroDivisionError as e:
    print('ZeroDivisionError message is:', e)
    b = float("inf")
finally:
    print('finally...')

上述代码中，通过改变try中a的值，可以模拟两种错误。两种错误的输出如下。此处请大家根据try的语法自行分析代码运行过程。

\# a = "10"
TypeError message is: unsupported operand type(s) for /: 'int' and 'str'
finally...
\# a = 0
ZeroDivisionError message is: division by zero
finally...

## Section 9: 文件操作

文件操作在Python中是十分常用的，尤其是我们需要从外部读入数据时。这里我们只介绍最常用的文件操作，高阶文件操作请大家自行阅读[Python IO文档](https://docs.python.org/3/tutorial/inputoutput.html)。  

Python的文件操作与C/C++类似。Python使用open()方法用于打开一个文件，并返回文件对象，通过该文件对象我们可以实现文件读写。使用open()方法一定要保证关闭文件对象，即调用close()方法。

open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)

open()方法主要用到前两个参数，文件名和模式，模式默认为只读。常用的模式如下表所示，更多模式及其介绍请看此处[教程](http://www.runoob.com/python3/python3-file-methods.html)。

模式

描述

r

以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。

r+

打开一个文件用于读写。文件指针将会放在文件的开头。

w

打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。

w+

打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。

a

打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。

a+

打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。

假如我们在data.txt文件中存储了以下的内容。

```
1 2 3
4 5 6

```

我们可以调用read()方法将data.txt中所有的内容一次性读取，并存储到str对象中。

f = open(r"data.txt", "r")
text = f.read()
f.close()
print(text)

输出如下：

1       2       3
4       5       6

很多时候我们数据文件很大，那么此时不能够直接将所有的数据放入内存，那么我将就可以按行读取文件。readline()和readlines()方法可以实现该功能。readline()方法每次读出一行内容。readlines()则是读取整个文件到一个迭代器以供我们遍历。下面的例子则是通过readlines()读取文件所有内容。

f = open(r"data.txt", "r")
i = 1
for line in f.readlines():
  print("No.%d row: %s" % (i, line))
  i += 1

f.close()

输出如下：

No.1 row: 1    2    3
No.2 row: 4    5    6

readlines()方法独到的每一行数据都存在一个字符串中，如果需要将每个数据都拿出来，还需要使用split()方法来分割字符串。  

Python中写文件通过write()方法实现，将一个字符串传给write()方法就可以实现写文件操作。下面的例子读取data.txt，然后将一列数据加1，第二列加2，第三列加3之后保存到新的文件data_new.txt中。

f = open(r"data.txt", "r")
g = open(r"data_new.txt", "w")
for line in f.readlines():
  line_data = line.split()
  col1, col2, col3 = int(line_data\[0\]) + 1, int(line_data\[1\]) + 2, int(line_data\[2\]) + 3
  new_line = " ".join(\[str(i) for i in \[col1, col2, col3\]\])
  g.write(new_line + "\\n")

f.close()
g.close()

在文件data_new.txt中存储了新的数据：

```
2 4 6
5 7 9

```

以上内容对open()，close()，readlines()，write()方法进行了简单介绍，更多的文件操作方法可以参考此处[教程](http://www.runoob.com/python3/python3-file-methods.html)。除了Python自带的这些函数之外，[pandas模块](https://pandas.pydata.org/)也提供了很多的文件操作。


  

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNDMxNTE1OTIsODg5NTc3NzY2LC0xMT
M3NTcyMzldfQ==
-->