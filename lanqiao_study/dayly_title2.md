# 蓝桥杯每日一题（2 day）
## 分数


**题目**
1/1​+1/2​+1/4​+1/8​+⋯
每项是前一项的一半，如果一共有 20 项,求这个和是多少，结果用分数表示出来。
类似：3/2​，当然，这只是加了前 2项而已。分子分母要求互质。

**分析**

> 观察题意我们可以清楚的了解，可变为等比数列求和，只不过我们需要将求和结果转化成分数而已，

> 我们大概能够知道。第20项分母为2**19，那我们是不是可以一开始将其所有数通分呢？

```python
# 存在分母为2**19
fm = 2**19
# 计算通分后的分子
fz = 0
for i in range(20):
	fz += 2**i
```

> 我们便获得的通项之后的分子分母，这时候我们需要不断求出公约数互相约去即可

> 这是可以导入一个第三方库math，在math中的gcd()函数能够更好的帮助我们求出公约数

```python
import math
fm = 2**19
fz = 0
for i in range(20):
	fz += 2**i
a = math.gcd(fm,fz)
# 循环，如果公约数不为1，一直相除
while (a!=1):
	fm = fm/a
	fz = fz/a
	# 重新看一下公约数
	a = math.gcd(fm,fz)
print(f"{fz}/{fm}")
```
# [点此返回目录](https://github.com/YeaChur/python_study/blob/main/lanqiao_study/title/title.md)
