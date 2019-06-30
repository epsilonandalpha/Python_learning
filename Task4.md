Task4
=======
1. 函数关键字
2. 函数的定义
3. 函数参数与作用域
4. 函数返回值
5. file：打开文件方式（读写两种方式）、文件对象的操作方法、学习对excel及csv文件操作
6. os模块
7. datetime模块

学习总结
===
## 函数关键字
函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。函数能提高应用的模块性，和代码的重复利用率。关键字是python内置的，具有特殊意义的标识符，自定义标识符命名时不可与之重复。可通过以下代码查看python内置的关键字内容：
  ```
  import keyword
  print(keyword.kwlist)
  ['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally',         'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while',         'with', 'yield']
  ```
## 函数的定义
在python中，我们可以自定义自己想要功能的函数，实现代码的简洁、高效、方便。以下是简单的规则：
* 函数代码块以def关键词开头，后接函数标识符名称和圆括号()。
* 任何传入参数和自变量必须放在圆括号中间。圆括号之间可以用于定义参数。
* 函数的第一行语句可以选择性地使用文档字符串—用于存放函数说明。
* 函数内容以冒号起始，并且缩进。
* return [表达式] 结束函数，选择性地返回一个值给调用方。不带表达式的return相当于返回 None。
  ```
  import math

  def quadratic(a,b,c):
      d = b ** 2 - 4 * a * c
      if d > 0:
          print('该方程有2个不同的实数根')
          x1 = (-b + math.sqrt(b ** 2 - 4 * a * c)) / (2 * a)
          x2 = (-b - math.sqrt(b ** 2 - 4 * a* c)) / (2 * a)
          return x1,x2
      elif d == 0:
          print('该方程仅有唯一实数根')
          x = -b / (2 * a)
          return(x)
      else:
          return '该方程无实根'
  print('这里是计算一元二次方程 ax^2+bx+c=0的两个解，请依次输入a，b，c的值')
  a=float(input('a='))
  b=float(input('b='))
  c=float(input('c='))
  print(quadratic(a,b,c))
  ```
## 函数的参数与作用域
* 函数的参数<br>
函数中的参数起到了传递数据的作用，函数调用者可以通过函数参数把函数内部需要的数据从外部传递过去。定义函数的时候，我们把参数的名字和位置确定下来，函数的接口定义就完成了。对于函数的调用者来说，只需要知道如何传递正确的参数，以及函数将返回什么样的值就够了，函数内部的复杂逻辑被封装起来，调用者无需了解。Python的函数定义非常简单，但灵活度却非常大。除了正常定义的必选参数外，还可以使用默认参数、可变参数和关键字参数，使得函数定义出来的接口，不但能处理复杂的参数，还可以简化调用者的代码。
1. 必选参数(位置参数)<br>
实参和形参的数量上必须要保持一致。
    ```
    def sum(a,b):
        c = a+b
        print(c)
    sum(1,2)
    ```
2. 默认参数<br>
调用函数时，默认参数的值如果没有传入，则被认为是默认值。设置默认参数时注意事项：必选参数在前，默认参数在后。
    ```
    def printinfo( name, age = 35 ):
       "打印任何传入的字符串"
       print "Name: ", name;
       print "Age ", age;
       return;
    #调用printinfo函数
    printinfo( age=50, name="miki" );
    printinfo( name="miki" );
    ```
3. 关键字参数<br>
通过定义关键字获取实参的值，与形参的顺序无关。
    ```
    def show(name,age):
        print('姓名是：%s  年龄是：%s'%(name,age))
    show(age='20',name='张三')
    ```
4. 可变参数<br>
形参的数据会根据实参的数量的变化而变化。加了星号（\*）的变量名会存放所有未命名的变量参数。\*vartuple:接收N个位置参数，并且会把位置参数转换成元组的形式。(通俗点就是说vartuple中保存的是没有利用的所有多余参数，保存方式为元组)
    ```
    # 可写函数说明
    def printinfo( arg1, *vartuple ):
       "打印任何传入的参数"
       print "输出: "
       print arg1
       for var in vartuple:
          print var
       return;
    # 调用printinfo 函数
    printinfo( 10 );
    printinfo( 70, 60, 50 )
    ```
* 函数的作用域<br>
Python 中，程序的变量并不是在哪个位置都可以访问的，访问权限决定于这个变量是在哪里赋值的。变量的作用域决定了在哪一部分程序可以访问哪个特定的变量名称。Python的作用域一共有4种，分别是：
* L （Local） 局部作用域
* E （Enclosing） 闭包函数外的函数中
* G （Global） 全局作用域
* B （Built-in） 内建作用域
以 L –> E –> G –>B 的规则查找，即：在局部找不到，便会去局部外的局部找（例如闭包），再找不到就会去全局找，再者去内建中找。<br>
Python 中只有模块（module），类（class）以及函数（def、lambda）才会引入新的作用域，其它的代码块（如 if/elif/else/、try/except、for/while等）是不会引入新的作用域的，也就是说这这些语句内定义的变量，外部也可以访问。<br>
变量的作用域决定了在哪一部分程序你可以访问哪个特定的变量名称。两种最基本的变量作用域如下：
* 全局变量
* 局部变量
定义在函数内部的变量拥有一个局部作用域，定义在函数外的拥有全局作用域。局部变量只能在其被声明的函数内部访问，而全局变量可以在整个程序范围内访问。调用函数时，所有在函数内声明的变量名称都将被加入到作用域中。
    ```
    total = 0; # 这是一个全局变量
    # 可写函数说明
    def sum( arg1, arg2 ):
       #返回2个参数的和."
       total = arg1 + arg2; # total在这里是局部变量.
       print "函数内是局部变量 : ", total
       return total;
    #调用sum函数
    sum( 10, 20 );
    print "函数外是全局变量 : ", total
    函数内是局部变量 :  30
    函数外是全局变量 :  0
    ```
## 函数的返回值
