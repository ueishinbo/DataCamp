# numpy

numpy是一个一种集合。

## numpy的基本操作

比如现在有一个集合：

```python
list1 = [1, 2, 4, 6, 7, 8, 9, 11, 32, 53, 21]
```

现在你可以把它转换成为numpy格式的集合

```python
import numpy as np
numpy1 = np.array(list1)
```

numpy1也是一种集合只不过是numpy类型的，使用numpy的意义是你可以对numpy里的每一个元素进行操作，而使用原先的list1却很难(目前来看)对集合里每一个元素操作变得比较费劲。比如：

```python
list2 = list1 * 2
print(list2)
#out:[1, 2, 4, 6, 7, 8, 9, 11, 32, 53, 21, 1, 2, 4, 6, 7, 8, 9, 11, 32, 53, 21]
numpy2 = numpy1 * 2
print(numpy2)
#[  2   4   8  12  14  16  18  22  64 106  42]
```

可以发现当对集合*2的时候，numpy就可以对每个元素都成2，而不是像list1一样扩大了两倍

## numpy的范围操作

还是最开始的集合

```python
list1 = [1, 2, 4, 6, 7, 8, 9, 11, 32, 53, 21]
numpy1 = np.array(list1)
```

如果你想找出集合中大于10的你可以

```python
compare = numpy1 > 10
print(compare)
#out:[False False False False False False False  True  True  True  True]
print(numpy1[compare])
#out: [11 32 53 21]
```

## numpy➕numpy

现在有两个集合你想让他们中的元素一一去做运算，用numpy就很方便,普通list就不行，只是简单的把两个list拼接起来了

```python
import numpy as np
list1 = [1, 2, True]
list2 = [False, 3, True]
numpy1 = np.array(list1)
numpy2 = np.array(list2)
print(list1 + list2)
#out: [1, 2, True, False, 3, True]
print(numpy2 + numpy1)
#out:[1 5 5]
```

但是如果用numpy的话就回一一相加 <mark>(注意: True = 1, False = 0)</mark>

**还有一点你得保证两个numpy中的个数一样，不然就会发生ValueError: operands could not be broadcast together with shapes**

## numpy的子集

```python
import numpy as np
#构建一个numpy
numpy1 = np.array([1, 2, 3, 4, 5, 6])
#取前三个
print(numpy1[:3])
#out:[1 2 3]
#取后俩
print(numpy1[-2:])
#out:[4 5]
```



## 二维numpy

可以想像成一个表格有行和列

```python
import numpy as np
list1 = [[180, 78.4],
            [215, 102.7],
            [210, 98.5],
            [188, 75.2]]
numpy1 = np.array(list1)
print(numpy1.shape)
#out:(4, 2) 也就是说有4行2列
```

### 二维numpy的子集

```python
import numpy as np
list1 = [[180, 78.4],
            [215, 102.7],
            [210, 98.5],
            [188, 75.2]]
numpy1 = np.array(list1)

print(numpy1[1,1])
#out:102.7 表示输出的是第一行的第一列
print(numpy1[1,:])
#out: [215.  102.7] 表示的是输出第一行的全部内容
print(numpy1[1:])
#out :[[215.  102.7]
# [210.   98.5]
# [188.   75.2]]
```

## numpy的一些工具

```python
import numpy as np
x = [1, 4, 8, 10, 12]
y = np.mean(x) #平均数
z = np.median(x) #中位数
print(y)
print(z)
```

















































