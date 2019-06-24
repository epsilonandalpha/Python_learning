Task2
=======
1. 列表：标志、基本操作(创建，append( )，pop( ) ,del( ), 拷贝）、列表相关方法<br>
2. 元组：标志、基本操作（创建及不可变性）<br>
3. string字符串：定义及基本操作（+，*，读取方式）、字符串相关方法、字符串格式化问题<br>

学习总结
===
## 列表
* 创建<br>
    在Python中，列表的标志，也即其使用符号就是'List'。List是一种有序的集合，可以随时添加和删除其中的元素，是Python中最基本的数据结构。<br>
    序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推。列表的数据项不需要具有相同的类型。创建一个列表，只要把逗号分隔的不同的数据项使用方括号括起来即可：<br>
    ```
    list=['information','science',1992,5]
    ```
* append()<br>
list是一个可变的有序表，所以，如果我们要往里面添加元素到末尾，可以使用append()
    ```
    list.append('hybrid')
    print(list)
    list=['information','science',1992,5,'hybrid']
    ```
* insert()<br>
也可以把元素插入到指定的位置，比如索引号为2的位置(注意，list的索引号从0开始)，可以使用insert()
    ```
    list.insert(2，'system')
    print(list)
    list=['information','science','system',1992,5,'hybrid']
    ```
* pop()<br>
    要删除list末尾的元素，用pop()
    ```
    list.pop()
    print(list)
    list=['information','science','system',1992,5]
    ```
    要删除指定位置的元素，用pop(i)方法，其中i是索引号
    ```
    list.pop(3)
    print(list)
    list=['information','science','system',5]
    ```
* 替换元素<br>
要把某个元素替换成别的元素，可以直接赋值给对应的索引号
    ```
    list[1]='nature'
    print(list)
    list=['information','nature','system',5]
    ```
* del<br>
可以使用 del 语句来删除列表的元素
    ```
    list=['information','nature','system',5]
    del list[0]
    print(list)
    list=['nature', 'system', 5]
    ```
* 拷贝<br>
copy() 函数用于复制列表
    ```
    list=['nature', 'system', 5]
    list1=list.copy()
    print(list1)
    ['nature', 'system', 5]
    ```
* 列表元素截取<br>
以`list=['information','nature','system',5]`为例

    | Python 表达式 | 结果 | 描述 | 
    | :-: | :-: | :-: | 
    |list[2]	|'system'	|读取列表中第三个元素|
    |list[-1]	|5 |读取列表中倒数第一个元素|
    |list[1:]	|['nature','system',5]|	从第二个元素开始截取列表|
* 列表脚本操作符<br>
列表对 + 和 * 的操作符与字符串相似。+ 号用于组合列表，* 号用于重复列表

    |Python 表达式|	结果|	描述|
    |len([1, 2, 3])|	3	|长度|
    |[1, 2, 3] + [4, 5, 6]|	[1, 2, 3, 4, 5, 6]|	组合|
    |['Hi!'] * 4|	['Hi!', 'Hi!', 'Hi!', 'Hi!']|	重复|
    |3 in [1, 2, 3]|	True|	元素是否存在于列表中|
