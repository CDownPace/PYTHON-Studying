# python基础知识总结 (1)
### python的几种数据类型
* 数字
* 字符串
* 列表
* 元组
* 字典

### 其他方面
* 类型相互转换
* 循环
* 函数
* 参数
* 变量
* 面向对象
* 捕获异常
* 读写文件
*以下分别介绍这几个方面*
## 数字

> a**b   表示a的b次方
   符号和数字相乘会得到数字个符号  c="="*30

> a//b    做除法然后取整

> 逻辑与
（a>b）and（a<b）  a与b 都成立才能返回true

> 逻辑或
（a>b）or（a<b）  a与b有一个成立就能返回true

> not:
```python
a=6
if not a=='4'
      print('不是4')
```

> '''用于定义多行变量          如果不想换行的话就加 \
```python
str6='''akgfmfjfjj
 fmfkrkkfll
sjklllke'''

print(str6)
# akgfmfjfjj
# fmfkrkkfll
# sjklllke
```

> 把数据类型转化为bytes
```python
text =b'hello world'
print(text)
print(type(text))
```

> 解码
```js
text_bytes=b'hello world'
text=text_bytes.decode('utf-8')
print(text)
print(type(text))
```

>字符串

> 替换字符串
```js
name = 'CDownPace'
age =18
green = 'My name is %s , my age is %s '%(name,age)
print(green)
```

> 格式化
格式化整型：%d

格式化浮点类型：%f       %.2f  表示保留多少位

> format
```python
course='python'
school='zhidao'
text='from {} , to study {}'.format(course,school)
print(text)
# 另外一种不用在乎顺序：
course='python'
school='zhidao'
text='from {arg1} , to study {arg2}'.format(arg1=course,arg2=school)
print(text)
```


> 字符串是不可以修改的
*如果想修改就需要把字符串变为列表*
```python
>>>list1=list(str1)
>>>list1
['a','b','c']
>>>list1[0]='A'
>>>list1
['A','b','c']
>>>str1=''.join(list1)    
#拼接字符串 ''里表示字符之间的分割符，可以为空
>>>str1
'Abc'
```

> find方法
```python
text='hello zhidao'
position=text.find('zhidao')
if position>0:
    print('在里面')
else:
    print('不在里面')
```

> index方法    查找并且返回个数
```python
text='hello zhidao'
position=text.index('zhidao')
# relatex=text.index('balabala')
print(position)
# print(relatex)
```

> len方法     返回个数
```python
text='hello zhidao'
length=len(text)
print(length)
```

> count方法：查找有多少个符合条件的字符串
```python
text='hello zhidao'
length=text.count('l')
print(length)
```

> replace方法：替换 

*不会改变原来字符串的值*
```python
text='hello zhidao'
length=text.replace('l','n')
print(length)
```

> split方法  以某字符串进行分割
```python
text='hello zhidao'
length=text.split(' ')
print(length)
```

> startswith方法： 判断是否以某字符串开头
```python
text='hello zhidao'
if text.startswith('hello'):
    print("是以hello开头的")
else:
    print("不是以hello开头的")
```

> endswith方法：是否以某字符串结尾

> lower方法：改成小写
```python
text='I am CDownPace'
new_text=text.lower()
print(new_text)
```

> upper方法：改成大写

> strip方法：把空格去掉
*（lstrip：删除左边的空格 rstrip:删除右边的空格）*
```python
text='     I am CDownPace   '
new_text=text.strip()
print(new_text)
```


## 列表
> 写入  
```python
# 列表[]里的数据可以是多种的。
  fruit=['apple','pear','grape']
print(fruit)
```

> 查找
```python 
fruit[0]
fruit[0：2]   
#从第一个开始查找，截止到第二个    左闭右开
```

> 遍历列表

```python
var l2=[1,2,'ab',8.9]
for var in l2:
print(var)

index=0
fruits=['苹果','香蕉','鸭梨']
length=len(fruits)
while index<length:
    x=fruits[index]
    print(x)
    index+=1

a=[1,2,3,['a','b','c']]
for x in a:
    if type(x)==list:
        for y in x:
            print(y)
    else:
        print(x)
```

> append方法：把另外一列表添加到列表后面

> count方法：统计某个元素在列表中出现的次数

> extend方法：将一个列表追加到另外一个列表中

> index方法：某个字符串出现的位置

> insert方法：插入某个元素
```python
temps=['a','b','c']
temps.insert(0,'1')
print(temps)
```

> pop方法：删除列表中的最后一个元素并返回这个元素
```python
temps=['a','b','c']
value=temps.pop()
print(value)
```

> remove方法：移除某个元素
```python
temps=['a','b','c']
temps.remove('a')
print(temps)
```

> reverse方法：反转

> sort方法：排序      

> sorted方法：也是排序，不会更改之前的列表

> in关键字：查找有没有
```python
temps=['a','b','c']
if 'b' in temps:
    print(True)
else:
    print(False)
```

> list方法：将字符串转换为列表
```python
temps='hello world'
new_temps=list(temps)
print(new_temps)
```

## 元组
*元组不可以修改*
```python
# 元组是以()将数据元素括起来，各个元素之间用逗号隔开。可以创建空元组。当元组中只有一个元素时，需要在元素后面添加逗号    也可以是任意的数据类型。
aList=[1,2,3]
aTuple=tuple(aList)
print(aTuple)
print(type(aTuple))
```

>查找操作：
```python
aTuple=('zhaoling','18','python')
age=aTuple[1]
print(age)
```
>切片操作：
```python
aTuple=('zhaoling','18','python')
newTupe=aTuple[0:2]
print(newTuple)
```
>赋值   如果不想取到某个值可以用_代替
```python
aTuple=('zhaoling','18','python')
username,age,classname=aTuple
print(username)
print(age)
print(classname)
tu1=('a','b')
tu2=(1,2)
tu3=(1,'a')
type(tu2)

tu5(9)
type(tu5)     #<class 'int'>
tu6(9,)
type(tu6)     #<class 'tuple'>
```

>删除元组
```python
del tu1
```

>内置方法
```python
1)len():计算元组元素的个数      #len(tu2)
2)max():返回元组元素的最大值
3)min():返回元组中元素的最小值
```

## 字典
```python
# 不能通过索引查找，只能通过”键：值“对的方式声明和存在的数据集合。
# 字典与列表相对，最大的不同在于字典是无序的，其成员位置只是象征性的，在字典中通过键来访问成员，而不能通过其位置来访问该成员。
dict1={key1:value1,key2:value2}
dict1={'name':'ycc','age':22}
# 字典中可以存储任意个“键值”对。
# 每个键值对中的键必须是唯一的，不可变的，但值则不必。
# 键值可以取任意数据类型。
```

>添加
```python
dict1['d']=4
```

>删除
```python
del dict1['a']
# 访问字典中的值
dict=['d']
```

>内置函数
```python
len():计算字典中的元素个数，即键的总数
str():输出字典并且可打印的字符串表示
```

>查找键的总数
```python
person={"username":"zhidao","age":18,"weight":160}
count=len(person)
print(count)
```

>查找值
```python
person={"username":"zhidao","age":18,"weight":160}
username=person['username']
print(username)
```

>修改
```python
person={"username":"zhidao","age":18,"weight":160}
person['username']='ketang'
print(person)
```

>添加
```python
person={"username":"zhidao","age":18,"weight":160}
person['classname']='python'
print(person)
```

>清除
```python
person={"username":"zhidao","age":18,"weight":160}
print(person)
person.clear()
print(person)
```

>get 方法：查找
```python
person={"username":"zhidao","age":18,"weight":160}
username=person.get("username1")
print(username)
```

>pop方法：删除最后的键和值  可以返回值
```python
person={"username":"zhidao","age":18,"weight":160}
username=person.pop("weight")
print(username)
```

>popitem 方法：
```python
person={"username":"zhidao","age":18,"weight":160}
value=person.popitem()
print(value)
print(person)
```

>update 方法
```python
# 如果遇到相同则会覆盖
```

>setdefault 方法：
```python
# 如果键在字典中存在，那么就会返回字典中的值
#如果键在点中不存在，那么会把这个键值添加到字典中。
# 并且返回这个值
```

>keys 方法：获取键
```python
person={"username":"zhidao","age":18,"weight":160}
keys=person.keys()
for key in keys:
    print(key)
```

>values 方法：获取值
```python
person={"username":"zhidao","age":18,"weight":160}
values=person.values()
for values in values:
    print(values)
```

>items 方法：解刨
```python
person={"username":"zhidao","age":18,"weight":160}
items=person.items()
for key,value in items:
    print(key)
    print(value)

for key,value in person.items():
     print("key:%s,value:%s"%(key,value))
```

>input
```python
name=input("请输入你的名字：")
# 请输入你的名字：Cdown
print(name)
# Cdown
```

>sep表示以什么符号分割    end表示以什么符号结尾
```python
print('a','b','c')
# a b c
print('a','b','c',sep=',')  
# a,b,c
print('a','b','c',end=';')  
# a b c;
```
## 类型相互转换
```python
# 将浮点类型转化为整形：
a=3.4
b=int(a)
print(b)

# 将字符串转化为整形：
a='1259'
b=int(a)

# 将整形转换为字符串：
a=1235
b=str(a)
print(type(a))

# 将字符串转换为浮点类型：
a='123'
b=float(a)
```

## 循环
```python
prince=26
     if prince<=20:
            print('buy cherry')
            print('buy cherry1')
            print('buy cherry2')
print('buy cherry6')
# 不满足条件则执行与if语句顶齐的代码

prince=26
if prince<=20:
            print('buy cherry')
else:
            print('buy cherry1')
            print('buy cherry2')
print('buy cherry6')
# =表示赋值   ==表示判断是否相等
```

>while语句

```python
# 最大的特点就是不知道循环多少次使用它，当不知道语句或者语句块需要重复多少次的时候，可以用while循环
count=0
while count<10:
    print(count)
    count=count+1
print('Done.')
```

>continue:只跳过本次循环，继续向下执行

```python
# 输出10以内的除去5的数
a=1
while a<=10:
    if a==5:
        a += 1
        continue
    print(a)
    a += 1
# 输出10以内的奇数：
b=1
while b<=10:
    if b%2==0:
        b+=1
        continue
    print(b)
    b+=1
```

>for循环语句

```python
# for循环语句通过循环遍历某一序列对象（列表，元组，字典等 ）来构建循环，循环结束的条件就是对象遍历完成。

for letter in 'python':
    print(letter)

fruit=['apple','grape','cherry','peach']
for fruit in fruit:
    print(fruit)
print('Done.')

# 重复一定的次数 range(）左闭右开
for num in range(0,10):
    print(num)


# 1加到10
result=0
for x in range(1,11):
      result+=x
print(result)
```

>定义函数

```python
# 在使用函数之前必须先定义（声明）函数，然后才能调用它。使用关键字def可以定义一个函数。
# def<函数名>（参数列表）：
    #  <函数语句>
    #  return<返回值>
# 其中，参数列表和返回值不是必须的，return后可以不跟返回值，甚至连return也可以没有。如果return后面没有返回值，或者没有return ，那么函数将会返回None值。
# 有些函数也可能不需要传输参数。
# 注意：即使函数没有参数，函数名后面的圆括号及冒号也要写上。
def hello():
    print('Hello,world')

def sum_func(a,b):
    '''
        
    :param a:
    :param b:
    :return:
    '''
    result=a+b
    return result
hello()
res=sum_func(2,3)
print('2+3=',res)
```

>位置参数
```python
# 严格按照函数定义的时候的参数顺序传递的参数
add(1,2)
```
>关键字参数：按照参数的名字来传递参数
```python
add(a=1,b=2)
add(b=2,a=1)
# 混合参数：传递参数的时候既包括位置也包括关键字参数
# 混合参数的注意事项：位置参数必须要在关键字参数的前面
add(1,b=2)
```

>缺省的位置参数
```python
def add(*args):
    print(args)
add(1,5,3,6,8)
```

>缺省的关键参数
```python
def add(**kwargs):
    print(kwargs)
add(a=1,b=2,c=3)
```

>混合参数
```python
def add(*args,**kwargs):
      print(args)
      print(kwargs)
add(1,2,3,a=4,b=5,c=6)
```

>默认参数
```python
# 默认参数只能在其他参数后面
# 如果默认参数和缺省的位置参数和关键字参数组合在一起，那么就要放在缺省的参数前面
def green(username,age=18):
    print(username)
    print(age)
#green('zhidao')
green('zhidao',age=20)
```

>返回值
```python
def add(a,b)
     return a+b
```

>一次性返回多个值
```python
def green(username,age)
      return username,age
username,age=green('zhidao',18)
print(username)
print(age)
```

>局部变量
```python
def green():
    username='zhidao'
    print('hello %s'%username)
# print(username)
```

>全局变量
```python
username='zhidao'
def green():
    print("hello %s"%username)
green()
print(username)
```

>模块
```python
import os
# 引入整个模块
print(os.listdir(r'D:/Kingsoft'))
#  r的作用  是防止转意

# 模块在python文件夹的lib下

from os import listdir
# 导入指定函数
print(listdir(r'D:/Kingsoft'))


from os import *
# 导入所有函数
print(listdir(r'D:/Kingsoft'))
```
## 面向对象
> 正常用法：
```python
class Person:  # 定义一个人类
    role = 'person'  # 人的角色属性都是人

    def __init__(self, name, aggressivity, life_value):
        self.name = name  # 每一个角色都有自己的昵称;
        self.aggressivity = aggressivity  # 每一个角色都有自己的攻击力;
        self.life_value = life_value  # 每一个角色都有自己的生命值;

    def attack(self,dog):
        # 人可以攻击狗，这里的狗也是一个对象。
        # 人攻击狗，那么狗的生命值就会根据人的攻击力而下降
        dog.life_value -= self.aggressivity

class Dog:  # 定义一个狗类
    role = 'dog'  # 狗的角色属性都是狗

    def __init__(self, name, breed, aggressivity, life_value):
        self.name = name  # 每一只狗都有自己的昵称;
        self.breed = breed  # 每一只狗都有自己的品种;
        self.aggressivity = aggressivity  # 每一只狗都有自己的攻击力;
        self.life_value = life_value  # 每一只狗都有自己的生命值;

    def bite(self,people):
        # 狗可以咬人，这里的狗也是一个对象。
        # 狗咬人，那么人的生命值就会根据狗的攻击力而下降
        people.life_value -= self.aggressivity

egg = Person('egon',10,1000)  #创造了一个实实在在的人egg
ha2 = Dog('二愣子','哈士奇',10,1000)  #创造了一只实实在在的狗ha2
print(ha2.life_value)         #看看ha2的生命值
egg.attack(ha2)               #egg打了ha2一下
print(ha2.life_value)         #ha2掉了10点血
```

> 面向对象编程组合用法
#### 组合指的是，在一个类中以另外一个类的对象作为数据属性，称为类的组合
```python
class Weapon:
    def prick(self, obj):  # 这是该装备的主动技能,扎死对方
        obj.life_value -= 500  # 假设攻击力是500

class Person:  # 定义一个人类
    role = 'person'  # 人的角色属性都是人

    def __init__(self, name):
        self.name = name  # 每一个角色都有自己的昵称;
        self.weapon = Weapon()  # 给角色绑定一个武器;
        
egg = Person('egon')
egg.weapon.prick() 
#egg组合了一个武器的对象，可以直接egg.weapon来使用组合类中的所有方法
```

> 面向对象编程三大特点
* 继承
* 多态
#### 继承是一种创建新类的方式，在python中，新建的类可以继承一个或多个父类，父类又可称为基类或超类，新建的类称为派生类或子类
```python
 #python中类的继承分为：单继承和多继承
class ParentClass1: #定义父类
    pass

class ParentClass2: #定义父类
    pass

class SubClass1(ParentClass1): #单继承，基类是ParentClass1，派生类是SubClass
    pass

class SubClass2(ParentClass1,ParentClass2): #python支持多继承，用逗号分隔开多个继承的类
    pass

>>> SubClass1.__bases__ #__base__只查看从左到右继承的第一个子类，__bases__则是查看所有继承的父类
(<class '__main__.ParentClass1'>,)
>>> SubClass2.__bases__
(<class '__main__.ParentClass1'>, <class '__main__.ParentClass2'>)
```

```
提示：如果没有指定基类，python的类会默认继承object类，object是所有python类的基类，它提供了一些常见方法（如__str__）的实现。
>>> ParentClass1.__bases__
(<class 'object'>,)
>>> ParentClass2.__bases__
(<class 'object'>,)
```

```python
#继承的代码实现
class Animal:

    def eat(self):
        print("%s 吃 " %self.name)

    def drink(self):
        print ("%s 喝 " %self.name)

class Cat(Animal):

    def __init__(self, name):
        self.name = name
        self.breed = '猫'

    def climb(self):
        print('爬树')

class Dog(Animal):

    def __init__(self, name):
        self.name = name
        self.breed='狗'

    def look_after_house(self):
        print('汪汪叫')


# ######### 执行 #########

c1 = Cat('小白家的小黑猫')
c1.eat()

c2 = Cat('小黑的小白猫')
c2.drink()

d1 = Dog('胖子家的小瘦狗')
d1.eat()
```

### 继承  继承自一个类
```python
#多态代码的实现
class Animal(object):
    eyes=2
    def __init__(self,kind,name):
        self.kind=kind
        self.name=name

    def run(self):
        print('In class Animal,'+self.name+' is running. ')

class Cat(Animal):
    def eat(self):
        print('Cat eatting.')
    def run(self):
        print('In class Cat,'+self.name+'is running.')

cat=Cat('cat','Kitty')
cat.run()
```

```python
#继承    继承自多个类       若各个类有同一属性，那选择先继承的类
class Animal(object):
    eyes=2
    def __init__(self,kind,name):
        self.kind=kind
        self.name=name

    def run(self):
        print('In class Animal,'+self.name+' is running.')

class Cat(Animal):
    def eat(self):
        print('Cat eatting.')
    def run(self):
        print('In class Cat,'+self.name+'is running.')
class Dog(Animal):
    def run(self):
        print('In class Dog,'+self.name+'is running.')

class CatDog(Cat,Dog):
    pass

cd=CatDog('catdog','C&D')
cd.run()
cat=Cat('cat','Kitty')
cat.run()
```
### 捕获异常
> try...except... 捕获单个异常
   * 可能产生错误的代码放在try中
   * 产生错误后要做的处理放到except中
```python
try:
    file1=open('test.txt','r')
#r表示只读
    print ('filel is open')
except （IOError，NameError):
    print ('file not exist')
```

```python
#这样就可以显示出错误
try:
    file1=open('test.txt','r')
    print ('file1 is open')
except IOError as result:
    print (result)
```
> 捕获多个异常
   * 多个异常之间用逗号隔开
```
try:
    file1=open('test.txt','r')
    print ('file1 is open')
except Exception as result:
    print (result)
```
> 无论是否异常都运行
```python
try:
    file1=open('test.txt','r')
    print ('file1 is open')
except Exception as result:
    print (result)
else:
    print('no exception')
finally:
    file1.close()
```
## 读写文件
> 读文件
```js
>>>f1=open(r'F:\temp\users.txt)
>>>lines=f1.readlines()
>>>lines
>>>f1.close()
目录前的r表示不转义
```

> 写文件    文件之前的内容会被覆盖
```js
>>>f2=open(r'F:\temp\users.txt,'w')
>>>f2.write('6842')
>>>f2.close()
```

```js
writelines 每一行作为一个列表
>>>f3=open(r'F:\temp\users.txt','w')
>>>lines=['a\n','b\n','c\n']
>>>f3.writelines(lines)
>>>f3.close()
```

```js
a 表示追加到文件后面
>>>f4=open(r'F:\temp\users.txt','a')
>>>f4.writelines(lines)
>>>f4.close()
```
