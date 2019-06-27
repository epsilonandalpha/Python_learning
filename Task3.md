Task3
=======
1. dict字典：定义、创建、字典的方法<br>
2. 集合：特性、创建、方法<br>
3. 判断语句（要求掌握多条件判断）<br>
4. 三目表达式<br>
5. 循环语句

学习总结
===
## dict字典
* 定义与创建<br>
    字典是一种可变容器模型，且可存储任意类型对象，具有极快的查找速度。字典的每个键值 key=>value 对用冒号:分割，每个键值对之间用逗号,分割，整个字典包括在花括号{}中，格式如下所示：
    ```
    d = {key1 : value1, key2 : value2 }
    ```
    值可以取任何数据类型，但键必须是不可变的，如字符串，数字或元组。
* 查询字典内某一个值<br>
    ```
    dict = {'a': 1, 'b':2, 'c' : 3}
    print(dict['b'])
    2
    ```
* 修改<br>
    把数据放入dict的方法，除了初始化时指定外，还可以通过key放入：
    ```
    dict = {'a': 1, 'b':2, 'c' : 3}
    dict['d']=7
    dict['a']=9
    print(dict['d']) #添加
    print(dict['a']) #修改
    7
    9
    ```
* 删除<br>
    删除单一的元素
    ```
    dict = {'a': 1, 'b':2, 'c' : 3}
    del dict['a']
    print(dict)
    {'b': 2, 'c': 3}
    ```
    删除所有元素
    ```
    dict = {'a': 1, 'b':2, 'c' : 3}
    dict.clear()
    print(dict)
    {}
    ```
    删除该字典
    ```
    dict = {'a': 1, 'b':2, 'c' : 3}
    del dict
    print(dict)
    <class 'dict'>
    ```
* 特性<br>
    1. 不允许同一个键出现两次。创建时如果同一个键被赋值两次，后一个值会被记住。<br>
    2. 键必须不可变，所以可以用数字，字符串或元组充当，所以用列表就不行。
## set集合
* 定义与创建<br>
    set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。<br>
    set可以看成数学意义上的无序和无重复元素的集合。<br>
    要创建一个set，需要提供一个list作为输入集合：
    ```
    s = set([1, 2, 3])
    print(s)
    {1,2,3}
    ```
    注意，传入的参数[1,2,3]是一个list，而显示的{1, 2, 3}只是告诉你这个set内部有1，2，3这3个元素，显示的顺序也不表示set是有序的。并且重复元素在set中自动被过滤。
* 添加与删除<br>
    通过add(key)方法可以添加元素到set中，可以重复添加，但不会有效果，会被自动过滤掉。
    ```
    s = set([1, 2, 3])
    s.add(4)
    print(s)
    {1, 2, 3, 4}
    ```
    通过remove(key)方法可以删除元素
    ```
    s = set([1, 2, 3])
    s.remove(1)
    print(s)
    {2, 3}
    ```
    此外，两个set可以做数学意义上的交集、并集等操作
    ```
    s1 = set([1, 2, 3])
    s2 = set([2, 3, 4])
    print(s1 & s2)
    print(s1 | s2)
    {2, 3}
    {1, 2, 3, 4}
    ```
## 判断（if）语句
* 基本语法<br>
    if语法与c语言基本相同，要注意的是其严格执行缩进规则
    ```
    age = 3
    if age >= 18:
        print('your age is', age)
        print('adult')
    else:
        print('your age is', age)
        print('teenager')
    your age is 3
    teenager
    ```
* 逻辑运算<br>
    在if语句中，逻辑运算包括三种，与（and）或（or）非（not）
    1. 与（and）<br>
        两个条件同时满足，返回True<br>
        只要有一个不满足，就返回False
    ```
    age = 13
    if age >= 8 and age <= 18:
        print('正确年龄')
    else:
        print('年龄错误')
    正确年龄
    ```
    2. 或（or）<br>
        两个条件只要有一个满足，返回True<br>
        两个条件都不满足，返回False
    ```
    age = 18
    weight = 130
    if age >= 18 or weight >= 120:
        print('合格')
    else:
        print('不合格')
    合格
    ```
    3. 非（not）
    ```
    age = 0
    if not age:
        print('不合格')
    ```
* 多条件判断<br>
    ```
    age = 14
    if age <= 5:
        print('幼儿园')
    elif age <= 12 and age > 5:
        print('小学')
    elif age <= 18 and age > 12:
        print('中学')
    elif age <= 22 and age > 18:
        print('大学')
    else:
        print('毕业')
    中学
    ```
    当然，跟C语言一样，python中IF语句也可以使用嵌套。
## 三目表达式
* 核心
    三目表达式的核心在于多条件判断的缩写。
    ```
    #编写一个Python程序，输入两个数，比较它们的大小并输出其中较大者
    x = int(5)
    y = int(8)

    print(x if (x > y) else y)
    8
    ```
## 循环语句
  Python的循环有两种，一种是for...in循环，依次把list或tuple中的每个元素迭代出来；第二种循环是while循环，只要条件满足，就不断循环，条件不满足时退出循环。
* for···in循环
    ```
    names = ['Michael', 'Bob', 'Tracy']
    for name in names:
        print(name)
    Michael
    Bob
    Tracy
    ```
* while循环
    ```
    sum = 0
    n = 99
    while n > 0:
        sum = sum + n
        n = n - 2
    print(sum)
    2500
    ```
