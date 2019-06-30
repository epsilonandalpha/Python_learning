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
