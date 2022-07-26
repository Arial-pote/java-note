# java数据类型

## 枚举（Enumeration）

枚举对象中的元素



## 数组（Array）

数组在内存中是连续分布的，增删O(nn)查找O(1)，不能内存扩展。java的多维数组在空间中的分布



数组转list

运用java1.8的stream，[来源于：](https://blog.csdn.net/x541211190/article/details/79597236)

```java
List<Integer> intList= Arrays.stream(new int[] { 1, 2, 3 }).boxed().collect(Collectors.toList());
List<Long> longList= Arrays.stream(new long[] { 1, 2, 3 }).boxed().collect(Collectors.toList());
List<Double> doubleList= Arrays.stream(new double[] { 1, 2, 3 }).boxed().collect(Collectors.toList());
```



## 列表（List）



位集合（BitSet）



## 链表

可以自定义，亦可以LinkedList（实现Queue）

插入删除



## 向量（Vector）



## 栈（Stack）

特性：先进先出

常用属性

```
boolean empty()
object pop()
push(object a)
object peek()
int 
```



## 字典（Dictionary）



## 哈希表（Hashtable）

Map<K,V> a = new HashMap<K,V>();

HashSet 是无序的，需要以添加顺序保存的可以存为LinkedHashSet

HashSet 基于 HashMap 来实现的，是一个不允许有重复元素的集合。



属性（Properties）



集合（Collection

做题贴士：记得考虑头一位和最后一位，很容易忽略特殊情况

考虑输入空集，输入的各种特殊情况

哈夫曼树：又名最优二叉树，是带权路径长度最小的二叉树。

结点的带权路径长度：在一棵树中，如果其结点上附带有一个权值，通常把该结点的路径长度与该结点上的权值之积称为该结点的带权路径长度（weighted path length）



# 题目类型：

[Java 读取输入字符和字符串 - SheepCore - 博客园 (cnblogs.com)](https://www.cnblogs.com/sheepcore/p/12366661.html#:~:text=Java 读取输入字符和字符串. 1. 使用Scanner读取字符和字符串. 2. 使用System.in.read ()读取单个字符.,如果只要读取一个字符可以通过read ()方法实现。. 3. 通过BufferedReader以缓冲方式读取字符串. 这种方法可以读取一行中的空格 (space and tab)，而Scanner读取时按空格分隔，空格后面无法读取，如果想要读取含有空格的字符串就需要使用这种方法。.)

acm模式下 如果一行代表一个数据，使用scanner尽量使用nextLine()

`scanner.nextInt() `,`next() `,` nextDouble()`, `nextFloat()`方法的识别终止符是**空格**，且会留下代表结束的换行符。

而`Scanner.nextLine()`方法的识别终止符是**换行符**。

==切记：在使用sc.next()或者sc.nextInt()等方法后，不能使用sc.nextLine()，否则后者因直接读到前者留下的换行符而读不到任何数据。==

## 二分法：

两种分发：

1. [ left, right ] 区间：

   1. ```
      while（left <= right） left = middle + 1 right = middle + 1
      ```

2. [ left, right ) 区间：

   1. ```
      while（left < right） left = middle + 1 right = middle
      ```

      



感觉这题不该这样做

一道题需要反反复复的if-else举例的话，应该是归类错误了，写题不应该是在每一种特殊情况if-else 而是尽力去避免特殊处理；

比如说处理两个数组，又可能短的先处理完导致长的剩余一截，不应该写一个单独处理长短不一使得情况，应该先去确认短的并基于短的来处理；

## 位运算：

7种位运算符：按位与（&）、按位或（|）、按位异或（^）、取反(~)、左移(<<)、带符号右移(>>)和无符号右移(>>>)；

**位运算符是对long、int、short、byte和char这5种类型的数据进行运算的**，我们不能对double、float和boolean进行位运算操作。

特殊预算：

（n）&（n-1）的结果恰为n的二进制表达式最后的1位变为0；（负数也如此）

堆排序（Heap Sort）：

堆指的是二叉堆，顾名思义，二叉堆是利用

dfs算法：

深度优先算法，遍历图或者数的算法；（区别：有向或无向）

有向和无向可以使用不同的算法   

可以是通过递归+visited集合实现，但这样容易堆栈溢出，因此通过显式栈模板调用。

回文算法一定要注意：最后几位数的处理：例如以0结尾的数

## 字符串处理：

- 将`char c = '6'`转为数字的方法 ` int i = c - '0' `;
- 

易错点：

1. 字符串不能用的 `==` 来比较，因为`==`比较的是字符串的地址，要用`s.equals(b)`；

2. 字符串处理的题目往往涉及复杂的流程以及条件情况，如果直接上手写程序，一不小心就会写出极其臃肿的代码。(考虑自动机概念处理) [例子](https://leetcode-cn.com/problems/string-to-integer-atoi/solution/zi-fu-chuan-zhuan-huan-zheng-shu-atoi-by-leetcode-/)

3. 字符串考虑字典序的时候，用`a.compareTo(b)`返回一个正数时，代表a在字典序中比较大；

   ```java
   
   ```

4. 

## 链表：

#### 快慢指针：

适用范围：环形链表

初始化快指针和慢指针的方法：

1. 快指针初始化在第2个节点，慢节点初始化在第1个节点；
2. 快、慢指针都初始化在第1个节点；

| 法一：节点数保持两倍 | o<br />o-o | o-o<br />o-o-o-o |
| -------------------- | ---------- | :--------------- |
| 法二：间距保持两倍   | o<br />o   | o-o<br />o-o-o   |



## 大数：

1. 善用long类型转换比较；

2. 运用char数组计算最后转换为String；

   ```
   char[] c = char[] c = {'s', 's', 'f'};
   String a = new String(c); //方法一
   String b = String.valueOf(c); //方法二
   ```

3. tmp

## 二叉树：

- 前序：根->左->右
- 中序：左->根->右 
- 后序：左->右->根

### 归并排序：

可以理解为二叉树的后续排序，先对左子树、右子树进行sort，然后merge（根节点操作）；

由于在归并排序中，左区间和右区间虽然各自在`[left,mid] ` `[mid+1,right]`范围内因为改变有所排序，但总体来说左区间节点恒小于右区间节点，因此很适用于一些跟区间相关的题：

https://labuladong.gitee.io/algo/2/19/26/

## 图论：

图的两种表达方式：邻接表、邻接矩阵；

<img src="https://s2.loli.net/2022/07/10/RN63ise7A4XOLc9.png" alt="image-20220318204349774" style="zoom:67%;" />

以及图的种类可细分为有向无向、有环无环、是否加权；

### 图的遍历：

如果图包含环，就需要一个`visited[n][n]`（n为点的数量）帮助判断该点是否已遍历过；

### 并查集：

```java
class UF {
    private int count;
    private int[] parent;

    public UF(int n) {
        this.count = n;
        parent = new int[n];
        for (int i = 0; i < n; i++) {
            parent[i] = i;
        }
    }

    public void union(int p, int q) {
        int rootP = find(p);
        int rooQ = find(q);
        if (rooQ == rootP)
            return;
        parent[rooQ] = rootP;
        count--;
    }

    public int find(int x) {
        while (parent[x] != x) {
            parent[x] = parent[parent[x]];//路径压缩
            x = parent[x];
        }
        return x;
    }

    public boolean connected(int a, int b) {
        return find(a) == find(b);
    }

    public int getCount() {
        return count;
    }
}
```

注意并查集==先并再查==，即先union再check是否满足条件

### 最小生成树：

在加权图中生成最小生成树的算法，要求：**权重和最小，不含环；**

#### Prim算法：

#### Kruskal算法：

从小到大排列所有的权重边并遍历，如果不会形成环，则将其加入集合；否则跳过该边；

设有节点V个，边的数量E，

时间复杂度：O(ElogE)，排序ElogE，其余for循环E；

空间复杂度：O(V+E)

#### Dijkstra算法：



## 数组：

### 前缀数组：



#### 差分数组：

使用差分数组要注意，包含最后一个数的范围很容易数组越界，就是去剪第n+1个数把它复原;

差分的时候，开始和结束的下标的设置跟具体的值有关：买票题1109和车站超载题end值不一样->买票在end值也要消耗票，下车在end值人数已经减少



### 线段树：

线段树是一种二叉搜索树，它将一段区间划分为若干单位区间，每一个节点都存储着一个区间。

应用场景：区间求和、区间最大值、区间修改、单点修改等。但可以线段树维护的问题必须满足==区间加法==。

> 区间加法：仅当对于区间`[L,R]`的问题的答案可以由`[L,M],[M+1,R]`答案合并得到，如区间求和，区间最大值；不满足该条件的有：区间众数，区间的最长不下降子序列；

<img src="https://img-blog.csdn.net/20180819213931568#pic_center" alt="img" style="zoom: 33%;" />

实现：运用==堆式存储法==，即编号为k的左儿子编号为`2k`，右儿子编号为`2k+1`，父节点编号为`⌊2k⌋ `（向下取整）；用位运算优化一下即为 `k<<1` , `k<<1|1` , `k>>1` 。**线段树的大小其实是 5n 左右的。**【注：在根节点编号为1时满足上式，根节点编号为0时左节点`2k+1` 右节点`2k+2` 】

1. 初始化：遍历整棵线段树，给每一个节点赋值，注意要递归到线段树的叶节点才结束。
1. 单点修改：要把下标为 k k*k* 的数字修改（加减乘除、赋值运算等）时，可以直接在根节点往下DFS。走到了只包含 k的节点修改即可。最后记得在回溯的时候把沿途经过的所有的点的值全部修改一下。
1. 区间修改：
   1. 找到区间中全部都是要修改的点的线段树的区间；
   1. 修改这一段区间的所有点；

区间修改运用到==懒惰标记==：

**标记的含义：本区间已经被更新过了，但是子区间却没有被更新过，被更新的信息是什么（区间求和只用记录有没有被访问过，而区间加减乘除等多种操作的问题则要记录进行的是哪一种操作）。**
这里再引入两个很重要的东西： **相对标记** 和 **绝对标记** 。

相对标记：指的是可以共存的标记，且打标记的顺序与答案无关，即标记可以叠加。 比如说给一段区间中的所有数字都 + a +a+a ，我们就可以把标记叠加一下，比如上一次打了一个 + 1 +1+1 的标记，这一次要给这一段区间 + 5 +5+5 ，那么就把 + 1 +1+1 的标记变成 + 6 +6+6 。
绝对标记：是指不可以共存的标记，每一次都要先把标记下传，再给当前节点打上新的标记。这些标记不能改变次序，否则会出错。 比如说给一段区间的数字重新赋值，或是给一段区间进行多种操作。









