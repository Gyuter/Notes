#### 读代码时产生的python笔记

##### 1.  内置list与numpy数组支持的切片功能不尽相同

```python
import numpy as np
a=[[i*10+j  for j in range(10)] for i in range(10)]
b=a
a=np.array(a)
rmask=[0,1,3,4]
cmask=[0,1,3,4]
print(a[rmask,cmask])
print(b[rmask,cmask])

#输出为
[ 0 11 33 44]
Traceback (most recent call last):
  File "c:/Users/15120/Desktop/crap.py", line 8, in <module>
    print(b[rmask,cmask])
TypeError: list indices must be integers or slices, not tuple
```

##### 2. defaultdict

普通的dict在试图访问不存在的元素时会报错

```python
>>> a={}
>>> a[7]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 7
```

defaultdict接受一个工厂函数，当访问一个不存在的键时，返回这个工厂函数产生的默认值

```python
from collections import defaultdict
a=defaultdict(int)
print(a[8])
#输出
0
```

##### 3. torch.nn 的奇妙模块

1. nn.Bilinear()

   ```python
   Bilinear(in1_features: int, in2_features: int, out_features: int, bias: bool)
   
   import torch
   import torch.nn as nn
   
   a=nn.Bilinear(10,20,1,False)
   nn.init.zeros_(a.weight)
   x=torch.tensor([i for i in range(10)],dtype=torch.float32)
   y=torch.tensor([i for i in range(20)],dtype=torch.float32)
   print(a(x,y))
   
   #输出
   tensor([0.], grad_fn=<AsStridedBackward>)
   ```

   它实现的功能相当于
   $$
   f(x,y)=x^TAy+b
   $$
   其中x为n维，y为m维，A是$n\times m$维，b是标量；如果输出的维度是多维，则有多组$A$和$b$，参数的数量为
   $$
   in1\_ features\times in2\_ features \times out\_ features+out\_ features
   $$
   
2. nn.Embedding()

   其实就是一个查询函数的生成器而已

   ```python
   import torch
   import torch.nn as nn
   f=nn.Embedding(10,10)
   f.weight=nn.Parameter(torch.FloatTensor([[i*10+j for j in range(10)] for i in range(10)]))
   print(f(torch.LongTensor([3])))
   #输出
   tensor([[30., 31., 32., 33., 34., 35., 36., 37., 38., 39.]],
          grad_fn=<EmbeddingBackward>)
   ```


##### 4. len shape 与size

```python
#内置的list
>>> b=[ i for i in range(10)]
>>> len(b)
10
>>> b.__len__()
10
>>> b.size
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'list' object has no attribute 'size'
>>> b.shape
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'list' object has no attribute 'shape'
#numpy 数组
>>> import numpy as np
>>> a=np.ones((5,5))
>>> a.shape
(5, 5)
>>> a.size
25
```
