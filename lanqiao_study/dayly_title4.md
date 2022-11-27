# 蓝桥杯每日一题 (4 day)

## __题目__

请你找到最小的整数X同时满足：
* X是2019的倍数
* X的每一个数字都是奇数


## __分析__

> 对于这道题我们可以很直观的知道，存在那么一个数X，这个X能够是2019的倍数，那么这时候我们可以利用一个循环不断将X乘以一个i（i>1）

```python
i = 1
while (True):
	i+=1
	X = 2019 * i
```

> 当然，这时候代码还未完全（条件2未满足）

> 条件2的意思是我们需要保证X中每一个数都是奇数，那么我们可以先判断数字是不是奇数，如果不是继续循环，如果是，再判断每一个数又是不是奇数

```python
if X % 2 == 0: # 判断是否奇数，如果不是进行下一次循环（节省运算次数）
	continue
else: # 如果是奇数，进行以下判断
	ls = [] # 创建一个列表，用于保存各个数字
	for j in str(X):
		if int(j) % 2 != 0: #判断每一个数是不是奇数 
			ls.append(j)  # 如果是，保存在列表里
		if len(ls) == len(str(X)): # 如果列表的长度与X的位数一致，说明X是我们需要的数
			print(X) # 打印X
			break # 并结束循环
		else: 
			continue # 否则进入下一个循环	
```

## __代码__
```python
i = 1
while (True):
	i += 1
	X = 2019*i
	if X % 2 == 0:
		continue
	else:
		ls = []
		for j in str(X):
			if int(j) % 2 != 0:
				ls.append(j)
		if len(ls) == len(str(X)):
			print(X)
			break
		else:
			continue
```
