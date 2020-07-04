# [Numpy](https://numpy.org/doc/stable/)
```py
TODO:
数组的拼接
reshape
多维数组的切片(slicing)和索引(indexing)
enumerate 遍历numpy数组
读取.npy文件，numpy.load和numpy.save函数
```

## 1. `array operation`

numpy中的基本数据类型是array，array可以通过python中的list生成。下面是对于array的常用操作。

```py
import numpy as np
# 生成一个数组
a = np.array([1,2,3,4,5])

# 数组大小
np.shape(a)
a.shape()

# 寻找最大最小值
np.max(a)
a.max()
np.min(a)
a.min()
np.max(a, axis = 0)
np.min(a, axis = 1)

#生成一个3*3的数组
a = np.array([[1,2,3], [4,5,6], [7,8,9]])

# 将a变为一维数组
a.flatten()# return a copy  
a.ravel()# A copy is made only if needed.

# 3x3的浮点型2维数组，并且初始化所有元素值为1
np.ones((3, 3), dtype=np.float)

# 创建一个一维数组，元素值是把3重复4次，array([3, 3, 3, 3])
f = np.repeat(3, 4)

# 2x2x3的无符号8位整型3维数组，并且初始化所有元素值为0
g = np.zeros((2, 2, 3), dtype=np.uint8)
g.shape                    # (2, 2, 3)
h = g.astype(np.float)  # 用另一种类型表示

l = np.arange(10)      	# 类似range，array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
m = np.linspace(0, 6, 5)# 等差数列，0到6之间5个取值，array([ 0., 1.5, 3., 4.5, 6.])
```

对于array，默认执行对位运算，涉及到多个array的对位运算需要array的维度一致。

```py
# 绝对值，1
a = np.abs(-1)

# sin函数，1.0
b = np.sin(np.pi/2)

# tanh逆函数，0.50000107157840523
c = np.arctanh(0.462118)

# e为底的指数函数，20.085536923187668
d = np.exp(3)

# 2的3次方，8
f = np.power(2, 3)

# 点积，与矩阵运算定义相同，1*3+2*4=11
g1 = np.dot([1, 2], [3, 4])

# 星积，逐元素相乘，结果为[3,8]
g2 = np.multiply([1, 2], [3, 4])

# 开方，5
h = np.sqrt(25)

# 求和，10
l = np.sum([1, 2, 3, 4])

# 平均值，5.5
m = np.mean([4, 5, 6, 7])

# 标准差，0.96824583655185426
p = np.std([1, 2, 3, 2, 1, 3, 2, 0])

a = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

b = np.array([
    [1, 2, 3],
    [1, 2, 3]
])

'''
维度一样的array，对位计算
array([[2, 4, 6],
       [5, 7, 9]])
'''
a + b

'''
array([[0, 0, 0],
       [3, 3, 3]])
'''
a - b

'''
array([[ 1,  4,  9],
       [ 4, 10, 18]])
'''
a * b

'''
array([[1, 1, 1],
       [4, 2, 2]])
'''
a / b

'''
array([[ 1,  4,  9],
       [16, 25, 36]])
'''
a**2

'''
array([[  1,   4,  27],
       [  4,  25, 216]])
'''

c = np.array([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
    [10, 11, 12]
])
d = np.array([2, 2, 2])

'''
d和c的每一行分别进行运算
array([[ 3,  4,  5],
       [ 6,  7,  8],
       [ 9, 10, 11],
       [12, 13, 14]])
'''
c + d

'''
array([[ 2,  4,  6],
       [ 8, 10, 12],
       [14, 16, 18],
       [20, 22, 24]])
'''
c * d

'''
1和c的每个元素分别进行运算
array([[ 0,  1,  2],
       [ 3,  4,  5],
       [ 6,  7,  8],
       [ 9, 10, 11]])
'''
c - 1
```

numpy中的矩阵关键词为matrix，matrix可以使用多维的array代替，具体matrix的有关性质请大家自行查阅python手册。

### Section 11.2: 随机数操作

在科学计算中，会经常用到随机数，比如初始化神经网络的权重等。numpy中提供了很多的统计分布和随机数操作。

```py
import numpy as np
import numpy.random as random

# 设置随机数种子
random.seed(42)

# 产生一个1x3，[0,1)之间的浮点型随机数
# array([[ 0.37454012,  0.95071431,  0.73199394]])
# 后面的例子就不在注释中给出具体结果了
random.rand(1, 3)

# 产生一个[0,1)之间的浮点型随机数
random.random()

# 下边4个没有区别，都是按照指定大小产生[0,1)之间的浮点型随机数array，不Pythonic…
random.random((3, 3))
random.sample((3, 3))
random.random_sample((3, 3))
random.ranf((3, 3))

# 产生10个[1,6)之间的浮点型随机数
5*random.random(10) + 1
random.uniform(1, 6, 10)

# 产生10个[1,6]之间的整型随机数
random.randint(1, 6, 10)

# 产生5x2的标准正态分布样本
random.normal(size=(5, 2))

# 产生5个，n=5，p=0.5的二项分布样本
random.binomial(n=5, p=0.5, size=5)

a = np.arange(10)

# 从a中有回放的随机采样7个
random.choice(a, 7)

# 从a中无回放的随机采样7个
random.choice(a, 7, replace=False)

# 对a进行乱序并返回一个新的array
b = random.permutation(a)

# 对a进行in-place乱序
random.shuffle(a)
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI4NDEyMjQ3MCwxMjcyOTIzNDI5XX0=
-->