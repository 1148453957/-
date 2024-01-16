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
# 6. python默认参数，*list可变参数，关键字参数
默认参数必须指向不变对象  
```
def add_end(L=[]):
    L.append('END')
    return L
add_end() //   ['END']  
add_end() //   ['END','END']  
add_end() //   ['END','END','END']
Python函数在定义的时候，默认参数L的值就被计算出来了，即[]，因为默认参数L也是一个变量，它指向对象[]，每次调用该函数，如果改变了L的内容，则下次调用时，默认参数的内容就变了，不再是函数定义时的[]了

def add_end(L=None):
    if L is None:
        L = []
    L.append('END')
    return L
```
# 7. generator函数 yield
每次调用next()的时候执行，遇到yield语句返回，再次执行时从上次返回的yield语句处继续执行
```
from datetime import datetime


def triangles():
    r = [1]
    while True:-
        print(1, datetime.now())
        yield r
        r = [1] + [r[i] + r[i + 1] for i in range(len(r) - 1)] + [1]


n = 0
results = []
#for循环相当于手动调用next(),每循环一次，就执行一次next()
# 1 2 1 2 1 2
for t in triangles():
    print(2, datetime.now())

    results.append(t)
    n = n + 1
    if n == 10:
        break

for t in results:
    print(3, datetime.now())

    print(t)
```









