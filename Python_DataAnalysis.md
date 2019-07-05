Table of Contents
=================
* [利用Python进行数据分析](#利用Python进行数据分析)
  * [第一章 Numpy包](#1-Numpy包)  
     * [1.1 基本介绍](#11-基本介绍)
     * [1.2 数据容器ndarray](#12-数据容器ndarray)  
         * [1.2.1 创建ndarray](#121-创建ndarray)
         * [1.2.2 ndarray中数据类型](#122-ndarray中数据类型) 
     * [1.3 通用函数](#13-通用函数)   
  * [第九章 代码知识补充](#9-代码知识补充)  
     
# <center><div id="利用Python进行数据分析">利用Python进行数据分析</div></center>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;学习[《利用python进行数据分析》](./References/利用python进行数据分析.pdf)时的个人总结分析及补充，代码都是在Anoconda的Jupyter notebook中输入，不了解Anaconda或Jupyter notebook可以参考博客[anaconda安装tensorflow](https://blog.csdn.net/lrglgy/article/details/90732675#2-anaconda安装tensorflow)。

# <center><div id="1-Numpy包">第一章 Numpy包</div></center>  
## <div id="11-基本介绍">1.1 基本介绍</div>    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在Python中，Numpy（Numericl Python）包是数值计算最重要的包。大多数提供科学计算的包都是用Numpy的数组作为构建基础。  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Numpy包的部分功能如下：  

+ ndarray，一个具有矢量算术运算的复杂广播能力的快速且节省许多空间的多维数组；  
+ 对整组数据进行快速运算的标准数学函数；  
+ 用于读写磁盘数据和操作内存映射文件的工具；  
+ 线性代数，随机数生成和傅立叶变换功能。  
   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;包Numpy在数据计算中特别重要的作用是，它可以高效处理大数组的数据，而它具有这个优势的原因如下：  

+ Numpy是在一个连续内存块中存储数据，独立于其它的Python内置对象。  
`Numpy中C语言编写的算法库可以操作内存，而不必进行类型检查等前期工作，比起Python的内置序列, Numpy数组使用内存更小`  
+ Numpy可以在整个数组上执行复杂计算，而不需要Python的for循环。

**代码实例**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;通过将包含一百万个整数的数组乘二，比较Numpy和Python列表的性能：  
  
```python 
import numpy as np
 
my_arr = np.arange(1000000)
my_list = list(range(1000000))  
%time for _ in range(10): my_arr2 = my_arr * 2
# 结果为：CPU times: user 18.3 ms, sys: 11.5 ms, total: 29.9 ms
#        Wall time: 52.7 ms
%time for _ in range(10): my_list2 = my_list * 2
# 结果为：CPU times: user 122 ms, sys: 21.4 ms, total: 143 ms
#        Wall time: 164 ms 
```

## <div id="12-数据容器ndarray"> 1.2 数据容器ndarray</div>   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Numpy包最重要的特点之一就是N维数组对象ndarray，该对象是一个大数据集容器。利用该对象可以对整块大数据执行一些数学计算，而不必编写循环，并且它的语法与标量元素的运算一样（见如下代码）。  
  
  ```python
  In [1]:import numpy as np
  In [2]:data = np.random.randn(2,3)
  In [3]:data
  Out[3]:array([[-1.16604111,  0.25365658,  1.10927193],
                [-0.29861289,  0.95307362, -0.64044019]])
  In [4]:data * 10
  Out[4]:array([[-11.66041108,   2.53656577,  11.09271926],
                [ -2.98612887,   9.53073619,  -6.4044019 ]])
  In [5]:data + data
  Out[5]:array([[-2.33208222,  0.50731315,  2.21854385],
                [-0.59722577,  1.90614724, -1.28088038]])
  ```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在上述代码中，先将所有元素都乘以10，再将每个元素与自身相加。  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ndarray是一个通用的同构数据多维容器，即其中的元素具有相同的数据类型。因此ndarray有两个重要属性分别为shape(表示数组各维度大小)和dtype(表示数组数据类型)。  
  
  ```python
  In [6]:data.shape
  Out[6]:(2, 3)
  In [7]:data.dtype
  Out[7]:dtype('float64')
  ```  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;本节通过介绍Numpy数组的基本用法，了解面向数组的编程和思维方式。  
> 注意：  
> 一般情况下，“ndarray”、“数组”，“Numpy数组”三者都指ndarray对象。

### <div id="121-创建ndarray">1.2.1 创建ndarray</div>  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;创建ndarray的最常用方式就是使用array函数，向array函数中传入序列型的对象，array会将其转化为含有该数据的ndarray。具体见如下代码：  

  ```python
  # 转换一个列表
  In [8]:data1 = [1,3,4,7,9]
  In [9]:arr1 = np.array(data1)
  In [10]:arr1
  Out[10]:array([1, 3, 4, 7, 9])
  # 转换嵌套序列
  In [11]:data2 = [[1,5,8.8,3.2],[4.5,3.3,5.1,3]]
  In [12]:arr2 = np.array(data2)
  In [13]:arr2
  Out[14]:array([[1. , 5. , 8.8, 3.2],
                 [4.5, 3.3, 5.1, 3. ]])
  ```  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;除非特别说明，函数array会尝试推断出一个数据类型给新建数组。  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;除了array函数外，还有其它函数可以新建ndarray数组。如ones和zeros可以新建一个指定形状的且元素均为1或0的数组。函数empty则可以创建一个没有具体值的数组。函数arrange是python函数range的数组版本。具体用法见如下代码：  
  
  ```python
  # 创建全为1的数组
  In [15]:np.ones(4)
  Out[15]:array([1., 1., 1., 1.])
  # 创建全为0的数组
  In [16]:np.zeros(4)
  Out[16]:array([0., 0., 0., 0.])
  # 创建无具体值数组
  In [17]:np.empty(4)
  Out[17]:array([0., 0., 0., 0.])
  # 用arrange创建数组
  In [18]:np.arrange(4)
  Out[18]:array([0, 1, 2, 3])
  ```  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在上述代码中，函数empty返回的是一些未初始化的垃圾值，只分配空间但不填充值，不可认为返回全为0的数组。并且如果没有特别指定，Numpy中的数据类型一般都是float64（即浮点数）。 下表罗列Numpy中其它数组创建函数。

|函数        |引用类型|   
|:---------:|:-----:|    
|asarray    |将输入转换为ndarray,若输入是ndarray,则不进行复制|  
|ones_like  |以另一个数组为参数，根据其形状和数据类型创建全<br>为1的数组|
|zeros_like |与ones_like作用类似，元素全为0|
|full(shape, fill_value, dtype, order)<br>full\_like|用fill value中的所有值，根据形状和dtype创建数组；full_like则利用利用另一个数组的形状和dtype创建数组|
|eye(N)<br>identity(N)|创建一个N*N的单位方阵|  

### <div id="122-ndarray中数据类型">1.2.2 ndarray中数据类型</div>  
  
## <div id="13-通用函数">1.3 通用函数</div>  
# <center><div id="9-代码知识补充">第九章 代码知识补充</div></div>   
%time用法