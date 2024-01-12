# 1. input
 ```
name = input('please enter your name: ')
print('hello,', name)
这样可以直接输入
```
# 2. 除法 / 和 // 
```
>>> 10 / 3
3.3333333333333335
>>> 9 / 3
3.0
/   除法计算结果是浮点数，即使是两个整数恰好整除，结果也是浮点数：
>>> 10 // 3
3
// 除法只取结果的整数部分
```
# 3. 字符编码和替换  %.2f 保留两位小数，四舍五入
```
s1 = 72
s2 = 85
s3=(s2-s1)/s1*100
print("%.2f%%" % s3)
18.06%
```
# 4. nonlocal
如果内部函数没有通过 nonlocal 声明外部函数的变量，内部函数可以访问外部函数的变量值，但是如果尝试对这个变量进行赋值，Python 会将其当作内部函数的本地变量，而不是外部函数的变量。
```
def outer_function():
    outer_variable = 42

    def inner_function():
        # 没有使用 nonlocal 关键字
        # 所以这里创建了一个名为 outer_variable 的本地变量
        outer_variable = 100
        print("Inner Function:", outer_variable)

    inner_function()
    print("Outer Function:", outer_variable)

outer_function()
Inner Function: 100
Outer Function: 42
```
# 5. python可以不按顺序提供部分默认参数,js不可以
```
def enroll(name, gender, age=6, city='Beijing'):
    print('name:', name)
    print('gender:', gender)
    print('age:', age)
    print('city:', city)
enroll('Adam', 'M', city='Tianjin')
```











