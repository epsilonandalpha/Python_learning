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
函数中的参数起到了传递数据的作用，函数调用者可以通过函数参数把函数内部需要的数据从外部传递过去。定义函数的时候，我们把参数的名字和位置确定下来，函数的接口定义就完成了。对于函数的调用者来说，只需要知道如何传递正确的参数，以及函数将返回什么样的值就够了，函数内部的复杂逻辑被封装起来，调用者无需了解。Python的函数定义非常简单，但灵活度却非常大。除了正常定义的必选参数外，还可以使用默认参数、可变参数和关键字参数，使得函数定义出来的接口，不但能处理复杂的参数，还可以简化调用者的代码。