# 算法晋级之路

基于python的算法学习

## 目录
* [查找算法](#查找算法)
    * [简单查找](#简单查找)
    * [二分查找](#二分查找)
    * [大O表示法](#大O表示法)
* [排序算法](#排序算法)
    * [选择排序](#选择排序)
## 查找算法
学习两种简单查找算法：简单查找和二分查找。  

### 简单查找
[code](./查找算法/simple_search.py)
其实就是暴力匹配，依次比较库中的元素是否是你要查找的目标，知道找到为止，或者将库中元素遍历完。 因为要遍历所有元素，显然时间复杂度为：
<img src="https://latex.codecogs.com/gif.latex?O(n)" title="O(n)" />

### 二分查找 
[code](./查找算法/binary_search.py)
对于一个有序的列表，可用二分查找快速找到目标值。其原理简单来说就是每次将**目标值**与列表**中间的值**进行比较。因为列表有序，因此每比较一次，就可以排除一半的数据。最后如果找到目标值，则返回其下标，否则返回NULL。每次都可以排除一半的结果，因此时间复杂度为：
<img src="https://latex.codecogs.com/gif.latex?O(\log&space;n)" title="O(\log n)" />

### 大O表示法
大O表示法指出了算法有多快。例如假设列表包含n个元素，简单查找需要检查所有的元素，因此需要n步，用大O表示法就是O(n)。没有单位，大O表示法让你能够比较操作数，指出了算法运行时间的**增速**。而使用二分查找只需要执行log(n)次操作。
![](./查找算法/O_algorithm.png)

## 排序算法
学习两种排序算法：选择排序和快速排序

### 选择排序
* 数组和链表

```
1.数组：内存空间连续
2.链表：元素可存储在内存任何一个位置，因为每个元素都存储了下一个元素的位置
```
区别：  

| # | 数组 | 链表 |
|----|-----|-----|
|`读取`|*O(1)*|*O(n)*|
|`插入`| _O(n)_|*O(1)*|
|`删除`| _O(n)_|*O(1)*|

注意：仅当能够立刻访问到要删除的元素时，操作才为O(1),通常记录链表中的第一个和最后一个元素，当删除它们时，为O(1)

* 选择排序  [code](./排序算法/selectionSort.py)  
选择排序是一种简单的排序算法，思想非常简单：依次从待排序的集合(S)中取出最大的元素放到新的数组/链表中(T)，当S中的元素取完时，T就构成了一个有序的数组/链表，其中的元素按由大到小排列。  
因为每次都要遍历一遍集合S,以找出最大元素，因此算法的复杂度为*O(n^2)*  
```
实现：对数组中的元素按由小到大排列  
输入：S = [5, 10, 7, 3, 99]  
输出：T = [3, 5, 7, 10, 99]  
```

### 快速排序

- 递归

```
简单来讲递归就是程序调用自身。递归可以让问题的解决方案更加的清晰，但是并没有！没有！没有！性能上的优势！
编写递归函数一定一定一定要有基线条件和递归条件。
如果使用循环，程序的性能可能更高；如果使用递归，程序可能更易理解。如何选择取决于什么对你更重要。
```

简单练手：

编写递归函数实现阶乘计算，如输入：3；输出：6

```python
def fact(x):
	if x == 1:		# 基线条件
		return 1
	else:
		return x * fact(x-1)	# 递归条件
```

- 栈

```
程序的执行其实就是在不断的压入栈和弹出栈。当程序在调用另一个程序时，当前程序会暂停并处于未完成的状态。上述程序,运行fact(3)的执行过程如下图所示。
```

![1569943426425](README.assets/1569943426425.png)