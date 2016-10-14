编码：
1.	ord()获取字符的整数表示，chr()相反
2.	str变bytes：’ABC’变b’ABC’， ‘ABC’.encode(‘ascii’)；相反：b’ABC’.decode(‘ascii’)
3.	len()计算str包含多少字符：len(‘ABC’); len(b’ABC’)
4.	%d f s x（十六进制整数）占位符：’…%s’ % (‘…’)
5.	注意：’%2d-%02d’ % (3, 1)  ‘ 3-01’; ‘%.2f’ % 3.1415926  ‘3.14’; %转义%%

List
1.	list是[]，可以用len()获得个数，从0开始（[0]）；反数为-1
2.	.append()增加；.insert(位置, ‘s’)插入；.pop(位置)删除，同时也会返回被删除的s，默认从最后删起；替换name[位置] = ‘新元素’
3.	list包含list，提取内list元素：外name[外][内]

tuple
1.	tuple是()
2.	定义一个元素t=(1,)
3.	其他跟list一样，就是不能替换。
4.	tuple内有list，list可以变，tuple的不变是指这个list本身不变。

Input输入的是str，必须转换成int

Continue break

Dic
1.	[key: value]; value可以通过key放入：d[‘key’] = value
2.	判断key是否存在：’key’ in dic; d.get(‘key’, -1)
3.	删除key：d.pop(‘key’)
4.	key必须不能改变，比如不能用list作为key

set
1.	set([1, 2, 3])
2.	set内重复元素自动过滤，也无法重复添加
3.	添加s.add(元素); 删除s.remove(元素)

函数与调用
1.	例：定义abs保存为abstest.py，则当前目录下可以from abstest import abs
2.	pass

默认参数
1.	尽量指向一个不变的量，如str，NONE

可变参数*
1.	需要把一个list或tuple导入函数：函数(*list)

关键字参数
1.	*kw：参数录入不受限制，可以录入新的参数名称，方法是参数名：参数，即可以接受dic

命名关键字参数
1.	必须录入*后面的参数名称：*, d, e则必须录入d=参数, e=参数
2.	def variable(name1, name2, * name3, name4)即3和4是命名关键字参数。1和2叫位置参数，区别是1和2只需录入参数，3和4必须参数名+参数（3和4是不是定义的时候设置默认值比较好?）
3.	命名关键字参数必须传入参数名，可以设置默认值

参数组合
1.	顺序：必选、默认、可变、命名关键字、关键字：def var(a, b, c=0, *args, **kw)

***递归函数中提到的递归优化以及课后题的汉诺塔没做

切片
1.	L[0:1:2]: 0代表起始位置，1代表结束位置，3代表每几个取数
2.	从后往前就是L[-2: -0]
3.	list切片还是list，tuple切片还是tuple

迭代
1.	for … in …
2.	必须是可以迭代的对象：from collections import Iterable  isinstance(对象, Iterable)  True or False
3.	可以同时引用两个变量for x, y in [(1, 1), (2, 2)…]:  1 1…
4.	isinstance还可以用来判断别的

列表生成器
1.	[x * x for x in range(1, 11) if x % 2 == 0]: 选出1×1，2×2…中的偶数
2.	[m + n for m in ‘ABC’ for n in ‘XYZ’]
3.	[s.lower() for s in L]

生成器
1.	与列表生成器的区别就是不是[]而是（），通常用for来打印列表
2.	与函数的区别：函数遇到return返回，生成器遇到yield就返回，下次从yield继续。
def fib(max):
    n, a, b = 0, 0, 1
    while n < max:
        print(b)
        a, b = b, a + b
        n = n + 1
return 'done'

def fib(max):
    n, a, b = 0, 0, 1
    while n < max:
        yield b
        a, b = b, a + b
        n = n + 1
return 'done
3.	生成器需要显示return值，要用捕捉错误的方法try…except

迭代器
1.	迭代器Iterator和可迭代对象Iterable的区别不是很懂
2.	可用for都是Iterable, 可用next()都是Iterator
3.	
