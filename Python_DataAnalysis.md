Table of Contents
=================
* [利用Python进行数据分析](#利用Python进行数据分析)
  * [第一章 Numpy包](#1-Numpy包)  
     * [1.1 基本介绍](#11-基本介绍)
     * [1.2 数据容器ndarry](#12-数据容器)
     * [1.3 通用函数](#13-通用函数)   
  * [第九章 代码知识补充](#9-代码知识补充)  
     
# <center><div id="利用Python进行数据分析">利用Python进行数据分析</div></center>
学习[《利用python进行数据分析》](./References/利用python进行数据分析.pdf)时的个人总结分析及补充。

# <center><div id="1-Numpy包">第一章 Numpy包</div></center>  
## <div id="11-基本介绍">1.1 基本介绍</div>    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在Python中，Numpy（Numericl Python）包是数值计算最重要的包。大多数提供科学计算的包都是用Numpy的数组作为构建基础。  
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

## <div id="13-通用函数">1.3 通用函数</div>  
# <center><div id="9-代码知识补充">第九章 代码知识补充</div></div>  
np.arrange()用法  
range()用法  
%time用法