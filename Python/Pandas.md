# pandas

## Dataframe

```python
# Pre-defined lists
names = ['United States', 'Australia', 'Japan', 'India', 'Russia', 'Morocco', 'Egypt']
dr =  [True, False, False, False, True, True, True]
cpc = [809, 731, 588, 18, 200, 70, 45]

# Import pandas as pd
import pandas as pd

# Create dictionary my_dict with three key:value pairs: my_dict
my_dict = {'country':names, 'drives_right':dr, 'cars_per_cap':cpc}

# Build a DataFrame cars from my_dict: cars
cars = pd.DataFrame(my_dict)

# Print cars
print(cars)
```

输出

```
         country  drives_right  cars_per_cap
0  United States          True           809
1      Australia         False           731
2          Japan         False           588
3          India         False            18
4         Russia          True           200
5        Morocco          True            70
6          Egypt          True            45
```



Pandas.Dataframe()是用来建表格的,上表的行是0～6很难看 所以得用Dataframe.inde = XXX 来给赋值，如下。

```python
import pandas as pd

# Build cars DataFrame
names = ['United States', 'Australia', 'Japan', 'India', 'Russia', 'Morocco', 'Egypt']
dr =  [True, False, False, False, True, True, True]
cpc = [809, 731, 588, 18, 200, 70, 45]
cars_dict = { 'country':names, 'drives_right':dr, 'cars_per_cap':cpc }
cars = pd.DataFrame(cars_dict)
print(cars)

# Definition of row_labels
row_labels = ['US', 'AUS', 'JPN', 'IN', 'RU', 'MOR', 'EG']

# Specify row labels of cars  给rows赋值
cars.index = row_labels

# Print cars again
print(cars)
```

输出

```
     cars_per_cap        country  drives_right
US            809  United States          True
AUS           731      Australia         False
JPN           588          Japan         False
IN             18          India         False
RU            200         Russia          True
MOR            70        Morocco          True
EG             45          Egypt          True
```

---

读csv文件的时候让第一个不显示

```python
# Import pandas as pd
import pandas as pd

# Fix import by including index_col index_col = 0就是不显示
cars = pd.read_csv('cars.csv', index_col = 0)


# Print out cars
print(cars)
```

---

打印前n行

```
import pandas as pd

# Build cars DataFrame
names = ['United States', 'Australia', 'Japan', 'India', 'Russia', 'Morocco', 'Egypt']
dr =  [True, False, False, False, True, True, True]
cpc = [809, 731, 588, 18, 200, 70, 45]
cars_dict = { 'country':names, 'drives_right':dr, 'cars_per_cap':cpc }
cars = pd.DataFrame(cars_dict)

# 打印前3行
print(cars[:3])
```

---

Pandas中loc和iloc函数用法详解（源码+实例）

https://www.jianshu.com/p/dadf2f1b88fc

原csv文件内容

```
     cars_per_cap        country  drives_right
US            809  United States          True
AUS           731      Australia         False
JPN           588          Japan         False
IN             18          India         False
RU            200         Russia          True
MOR            70        Morocco          True
EG             45          Egypt          True
```

代码

```python
# Import cars data
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)

# Print out drives_right column as Series
print(cars.iloc[:,2])
print("----")
# Print out drives_right column as DataFrame
print(cars.iloc[:,[2]])
print("---")
# Print out cars_per_cap and drives_right as DataFrame
print(cars.iloc[:,[0,2]])
```

输出

```

US      True
AUS    False
JPN    False
IN     False
RU      True
MOR     True
EG      True
Name: drives_right, dtype: bool
---
     drives_right
US           True
AUS         False
JPN         False
IN          False
RU           True
MOR          True
EG           True
---
     cars_per_cap  drives_right
US            809          True
AUS           731         False
JPN           588         False
IN             18         False
RU            200          True
MOR            70          True
EG             45          True
```

