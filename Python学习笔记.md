# Python学习笔记

## 小函数
~~~python
sum([a,b,c])    //求 a,b,c 的和
sum =1 
del(sum)	//restore sum
id(a)	//obserbe the adress of a
type(a)	//show the data type of a
st = input()	//regard all the input as string
a,b = input().split()
n = int(input("please input a interger"))
print(a,b)	//printf a and b, split by a space
for i in range(5):
    print(i)
print(a,end='')	//control the end
round(0.1+0.2,2)==0.3	//true
a = complex(1,2)	//a = 1+2j
s.find(arg1,arg2,arg3)
s.replace()
s.strip() s.rstrip() s.lstrip() //delete the blank space in side
~~~

## 字符与数字的转换

~~~python
str(123)	//'123'

~~~



## 特性

1. 小整数不分配内存空间，例如id(1)的地址恒定
2. 字符串不可修改

## 库

1. math
2. turtle：用来绘制图形