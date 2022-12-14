# 蓝桥杯每日一题
## 相乘

**题目**

小蓝发现，他将1至1000000007之间的不同的数与 2021相乘后再求除以1000000007的余数，
会得到不同的数。小蓝想知道，能不能在1至 1000000007之间找到一个数，
与 2021相乘后 再除以 1000000007后的余数为 999999999。如果存在，请在答案中提交这个数； 如果不存在，请在答案中提交 0。

__分析__

> 如题我们知道，我们需要求出这么一个n，这个n满足：n*2021%1000000007 = 999999999,
> 如果我们直接用以下式子：

```python
for n in range(1,1000000007):
  if n*2021%1000000007 == 999999999:
	  print(n)
	  break
```

> 我们会很清楚的发现循环时间过长容易运行超时。

> 这时候我们可以换个思路，只要保证（1<i<2022）（i*1000000007 + 999999999）% 2021 = 0,这个条件满足即可。这时候循环次数由原先的1000000007次变为2021次，大大降低了所需要的时间

> 于是，如若用for循环,有：

```python
for i in range(1,2022):
	n = i * 1000000007 + 999999999
	if n%2021 == 0:
		print(n//2021)
		break
```

> 用while 循环

```python
i = 1
while True:
	n = i * 1000000007 + 999999999
	if n%2021 == 0:
		print(n//2021)
		break
	i += 1
```

# [点此返回目录](https://github.com/YeaChur/python_study/blob/main/lanqiao_study/title/title.md)
