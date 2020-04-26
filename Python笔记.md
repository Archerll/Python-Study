# Python笔记

标签（空格分隔）： 
---
  1.python使用
---

 - 圆面积计算

        r=5
        aera=3.1415*r*r
        print（aera）
        print（"{：.2f}F"，aera）

 - 同切圆
 ```python
    import turtle
    turtle.pensize(2)
    turtle.circle(10)
    turtle.circle(40)
    turtle.circle(80)
    turtle.circle(120)
```

 - 五角星

        from turtle import*
        color('red','red')
        for i in rang(5):
            fd(200)
            rt(144)
        end_fill()

 - 科赫曲线

        import turtle
        def koch(size,n)
            if n==0:
                

 - 温度转换

        TempSt= import("请输入符号温度：")
        if Temstr[-1] in ['F','f']:
            C=(eval(TempStr[0:-1])-32)/1.8
            print("转换后的温度值为{：.2f}C".format(C))
        elif TempStr[-1] in['C','c']:
            F=1.8*eval(TempStr[0:-1])+32
            print("z转换后的温度值为{：.2f}F".format(F))
        else:
            print("Error")

2.python 语法
---
 - 基础语法
 
        1. 字符串(String)：
            1）反斜杠可以用来转义，使用r可以让反斜杠不发生转义。。 如 r"this is a line with \n" 则\n会显示，并不是换行。
            2）字符串可以用 + 运算符连接在一起，用 * 运算符重复。

        2. 一行多个语句：import sys; x = 'runoob'; sys.stdout.write(x + '\n')
        
        3. print 默认输出是换行的，如果要实现不换行需要在变量末尾加上 end=""：
        
        4. import 与 from...import：用 import 或者 from...import 来导入相应的模块。

 - 
         for<循环变量> in <遍历结构>    #range()用来生成一个结构<被执行的语句>
         扩展Range()函数：range(M,N,K)M开始，N结束，K为步长。

 - 
        字符串循环遍历： for c in string:
        string字符串的遍历

 - 列表遍历循环： 

            for Item in ls
            ls为列表，遍历出列表数值。

 - 文件遍历： for line in fi
    fi 是一个文件标识符
 - while循环：
 
        while <循环条件>：
            <循环体>

 - 循环控制：

         break,continue
         continue:跳出单次循环。

> 高级使用：
    for(  )   in(  )：     或   while(     ):
    else：
    当循环体未被break结束时，执行else语句


 - 单分支结构
 - 二分支结构

        <表达式1>if<条件>else<表达式2>
        
        if<条件>
        else

 - 多分支结构
 

        if
        elif
        else

 - 逻辑(与c不同)，条件（比较）

        x and y
        x or y
        x
        在条件比较时 < <= > >= 可以连用***
3.python 自带库
---

 - python第三方库
 
> pypi.orj   检索库
安装方法
1.pip
    `pip install <第三方库名>`
    `pip install -u <>`
    `pip uninstall`

2.集成安装——Anaconda  www.continuum.io
3.

 - turtle 库的使用
    库引用 import ，from .....import，import   as
    函数 setup(),penup(),pendown(),pensize(),pencolor()
    fd(),cirle()

 - **time()库**
 
 - **random库**

        import random 
        1.seed（a=None）    #初始化随机数种子
            random.seed(10) #产生种子对应的随机序列
        2.random()          #生成随即小数
            random.random()
        #扩展随机数库
        random.randint(a,b)        #产生从a,b的随即整数
        random.randrange(m,n[,k])    #生成一个[m,n]之间K步长的随机整数
        random.getrandbits(k)      #生成一个K比特长的随机整数
        random.uniform(a,b)        #生成一个[a,b]之间的随即小数
        random.choice(seq)         #从seq序列中随机选取一个元素
        random.shuffle(seq)        #将seq队列的顺序随机打乱并输出

 - Pyinstaller库

        cmd命令行下 pyinstaller -F <文件名.py>
        -h
        -i
        -

 - jieba库
中文分词

        cmd 下 pip install jieba
        函数：
        jieba.lcut()
        jieba.add_word()
三种模式：

> 1.精确模式
 2.全模式
3.搜索引擎模式
 
 - wordcloud 库
 

        w=wordcloud.WordCloud(<参数>)     #加载对象
        参数包括：width  heigh 
        w.generate(txt)             #输入文本
        w.to_flie(fliename)         #输出图片
        min_font_size
        max_font_size
        font_step
        font_path
        max_words
        stop_words      #排除
        
        mask            #词云形状
        background_color#词云背景颜色

 - **os库**
 

        os.path.abspath(path)
        os.path.normpath(path)
        os.path.relpath(path)

        os.system

        os.chdir(path)
        os.getcwd(path)
        os.getlogin()
        os. 
4.异常处理
--

    try:
        <语句块1>
    except:
        <语句块2>
    try:
        <>
    except <异常类型>:
        <>
        
高级使用

    try:                
        <>
    except:             如try异常，则except捕捉异常
        <>
    else:               若try执行，则else执行
        <>
    finally:
        
实现动态导入包：

        try:
            from cStringIO import StringIO
        except ImportError:
            from StringIO import StringIO
        
5.函数使用
----------

 1. 参数传递

        1.可选参数传递
            def fact (n,m=1)
                <函数体>
                return 0
        2.可变参数传递
            def fact(n<确定的参数>,*p<不确定的参数>) # *的参数会以tuple形式传入
                <函数体>
                return 0
            def fact(**arges)  # **的参数会以dict形式传入
        3.关键字参数
            de fact (str):
                <>
            fact(str = 'string')  #关键字参数，顺序任意

 2. 局部变量与全局变量

        1.对于基本数据类型，无论是否重名，全局变量与局部变量不相同
        2.使用global保留字可以将函数内部的局部变量转换为同名全局变量
        3.组合数据类型在函数中未被真实创建，即为全局变量。如果被真实创建则为局部变量。（未被真实创建时，组合类型指向全局组合类型）
    
 3. lambda()函数
用于只有一行表达式的函数定义

        <函数名>=lambda<参数>：<表达式>
        例如：
        f = lambda x,y:x+y
        #这是个加减法函数
        #不建议使用lambda函数。
 4. **可更改(mutable)与不可更改(immutable)对象**

在 python 中，strings, tuples, 和 numbers 是不可更改的对象，而 list,dict 等则是可以修改的对象。

    不可变类型：变量赋值 a=5 后再赋值 a=10，这里实际是新生成一个 int 值对象 10，再让 a 指向它，而 5 被丢弃，不是改变a的值，相当于新生成了a。

    可变类型：变量赋值 la=[1,2,3,4] 后再赋值 la[2]=5 则是将 list la 的第三个元素值更改，本身la没有动，只是其内部的一部分值被修改了。
5. **python 函数的参数传递：**

    不可变类型：类似 c++ 的值传递，如整数、字符串、元组。如fun（a），传递的只是a的值，没有影响a对象本身。比如在 fun（a）内部修改 a 的值，只是修改另一个复制的对象，不会影响 a 本身。

    可变类型：类似 c++ 的引用传递，如 列表，字典。如 fun（la），则是将 la 真正的传过去，修改后fun外部的la也会受影响

python 中一切都是对象，严格意义我们不能说值传递还是引用传递，我们应该说传不可变对象和传可变对象。
6.  **Python的内置函数**



---
6.组合数据类型
---

 **- 集合（set）数据类型** 
 -集合中为不可修改的数据    --> { }
 -无序，并且元素不能重复
 -***建立空集合必须用set（）非空集合需要set(list)***  

        A={'python',123,('pyhton'+123)}
        =>{python,123,python123}
        A=set("pypy123")
        =>{'1','2','3','p','y'}

 -集合运算：
 

        s|t  # 并运算  增强操作：s|=t
        s-t  # 差运算            s-=t
        s&t  # 交运算            s&=t
        s^t  # 补运算            s^=t
        s>=t  s>t
        s<=t  s<t

 -集合操作（存在集合S）

        S.add(x)        #向集合中添加元素x
        S.discard(x)    #删除集合中的x,不存在不报错
        S.remove(x)     #删除元素x，不存在返回 KeyError异常
        S.clear         #移除所有元素
        S.pop           #随机返回一个元素同时删除
        S.copy()        #返回S的一额副本
        len(S)          #返回集合元素的个数
        x in S          #x是否在集合中
        set(S)          #将其他类型转变为集合


 - **元组(tuple)&列表(list)类型**

-列表：[ ]或list( )创建   ---> [ ]
-元组：不可修改  --->(  )
-操作
    
        列表名.insert(index,value)  #指定index插入value
        列表名.append(value)     #列尾增加value
        列表名.extend(Iterable)  #将可迭代的数据追加到列表
        
        del 列表名[index]     #删除指定index数据
        列表名.remove(value)   #删除第一个出现的value
        列表名.pop()       #删除最后一个数据，并返回值
        列表名.clear()     #清空列表
        
        列表名.len(s)
        列表名.min(s)
        列表名.max(s)
        列表名.count(value)   #value出现的次数
        列表名.index(value)   #value首次出现时的索引
        
        zip([list1],[list2]) #合并两个list

 - **字典类型**
 -创建方法： {}和dict（）
 -字典操作

        d.values()
        d.keys()
        d.pop(key)   #删除给定key值的值
        d.get(key)   #在Key不存在的时候，返回None;存在则返回value
        
        d.items()      #将d转换成（key,value）的list   
        d.values()     #将d转换成含value的list
        2.7版本中还有：
        d.iteritems()   d.itervalues()
 -字典的特点：
 
        dict的第一个特点是**查找速度快**
        dict的第二个特点就是存储的key-value序对是没有顺序的！
        dict的第三个特点是作为 key 的元素必须不可变，Python的基本类型如字符串、整数、浮点数都是不可变的，都可以作为 key。但是list是可变的，就不能作为 key。
        

 - **字符串**
    -字符串运算符

        +       #字符串连接
        *       #输出重复的字符串        str*2
        []  [:] 
        in      #如果字符串中包含给定字符返回True: 'H' in str
        not in  #不包含给定字符返回Ture :'H' not in str 
        
    -格式化<一>
    
        %c  格式化字符
        %d  格式化正数
        %s  格式化字符串
        %f  格式化为浮点数，可以指定精度
        %e  格式化为科学计数法
        
    -格式化<二> 使用str.format()
    
        "{},{}".format("hello","world")   #自动填充{}
        "{0},{1}".format("hello","world")   #{1}指定填充的数据
        "{first},{Second}".format(first="hello",Second = "world")
        
    { }中对数字类型的格式化
    
        
        
 
7.文件和数据格式
---
**第三方库：（pickle）**

 -  文件类型
    -   文本文件
    -   二进制文文件
 - 文件打开方式
 -二进制打开或文本文件打开

        a=open("路径" ,"打开方式" )
        打开方式：
        'r'只读模式（默认）         'a'追加写
        'w'覆盖写                  'b'二进制文件
        'x'创建写                  't'文本文件（默认）
        '+'与r/w/x/a连用增加读写功能

 - 文件内容读取
 
        a.read()
        a.readline()
        a.readlines()
        
 - 数据的文件写入

        a.write()
        a.writeline()
        a.seek(offset) 0-文件开头，1-当前位置，2-文件结尾n

 - 一维数据（再看看）

> 1.存储
2.处理

 - 二维数据

> 1.存储格式（二维列表）
    1）CSV格式
    
    
8.迭代器和生成器
---
-   迭代器

    迭代器对象从集合的第一个元素开始访问，直到所有的元素被访问完结束。迭代器只能往前不会后退。

    迭代器有两个基本的方法：iter() 和 next()。

    字符串，列表或元组对象都可用于创建迭代器
    
    自定义迭代器并须实现`__iter__()`和 `__next__()`两个方法：
    
        class MyIteration:
            def __iter__(self):
                self.a=1
                return self
            def __next__(self):
                x= self.a
                self.a+=1
                return x
                
        myclass = MyIteration()
        myiter = iter(myclass)   （调用iter生成迭代器）
        

-   **生成器**
    在 Python 中，使用了 yield 的函数被称为生成器（generator）
            
        import sys

        def fibonacci(n):   #主生成器 斐波那契数列
             a,b,counter = 0,1,0
             while True:
                if counter>n:
                    return
                yield a       #yield 返回一个生成的迭代
                a ,b =b,a+b
                counter+=1
        f = fibonacci(10)     #f指向迭代对象

        while True:
            try:
                print(next(f),end=' ')
            except StopIteration:
                sys.exit()
            

9.python计算生态
---

 - 数据到人工智能
 
>.
 1. 数据分析：numpy，pandas，SciPy
 2. 数据可视化：matplotlib ，seaborn , mayavi
 3. 文本处理:PyPDF2 , NLTK（自然语言），python-docx
 - 机器学习：scikit-learn , TensorFlow ,MXNet(基于神经网络的深度学习计算框架)
 

- 从web解析到网络空间

>.
 1. 网络爬虫：requests（最友好的网络爬虫库），Scrapy(网络爬虫框架)，pyspider
 2. web信息提取：Beautiful Soup(HTML和XML解析库)，Re(正则表达式和处理功能库)，python-Goose(提取文章类型web页面)
 3. web网站开发：Django(),Pyramid(规模适中的网站框架),Flask（web应用微框架）
 4. 网络应用开发：WeRoBot,aip,MyQR(二维码生成库)
 
- 人机交互

> .
1. 图形用户界面：PyQt5,wxPython(跨平台GUI)，PyGObject
2. 游戏开发：PyGame,panda3D,cocos2D
3. 虚拟现实：VR Zero（树莓派上VR），pyovr(Oculus r) , Vizard(通用VR开发引擎)
4. 图形艺术：Quads() , ascii_art , turtle,


python 进阶
---
10.函数式编程 
---

- 高阶函数  将函数作为参数传入高阶函数
    
            def add(x,y,f)   #f接受一个函数
                return f(x)+f(y)
            add(-4,10,abs)         #函数名指向函数，所以可以被变量引用
            
        
**python内置的高阶函数：**
    

> map,reduce,filter 在python2x中返回list，py3中返回迭代器

        1.map(f，list)  #*有两个参数，一个为函数f，一个为列表list，可以将列表中每一个元素作为参数赋值到函数中,且返回一个列表。*
        2.reduce（f，list） 
        *#reduce()函数接收的参数和 map()类似，一个函数 f，一个list，但行为和 map()不同，reduce()传入的函数 f 必须接收两个参数，reduce()对list的每个元素反复调用函数f，并返回最终结果值。*
        3.filter(a，b) 
        #filter()函数是 Python 内置的另一个有用的高阶函数，filter()函数接收一个函数 f 和一个list，这个函数 f 的作用是对每个元素进行判断，返回 True或 False，filter()根据判断结果自动过滤掉不符合条件的元素，返回由符合条件元素组成的新list。
        4.sorted()
        #sorted()函数可对list进行排序,它可以接收一个比较函数来实现自定义排序，比较函数的定义是，传入两个待比较的元素 x, y，如果 x 应该排在 y 的前面，返回 -1，如果 x 应该排在 y 的后面，返回 1。如果 x 和 y 相等，返回 0。
                
-  python 中的闭包
        
        内层函数引用了外层函数的变量（参数也算变量），然后返回内层函数的情况，称为闭包（Closure）
        闭包的特点是返回的函数还引用了外层函数的局部变量，所以，要正确使用闭包，就要确保引用的局部变量在函数返回后不能变。

        # 此函数为正确的闭包 结果为  1，4，9
            def count():
                fs = []
                for i in range(1, 4):
                    def f(j):
                        def g():
                            return j*j
                        return g
                    r=f(i)
                fs.append(r)
                return fs
            f1, f2, f3 = count()
            print f1(), f2(), f3()   

        # 此函数就在闭包中引用了变量，结果为 9 9 9
            def count():
                fs = []
                for i in range(1,4):
                    def f():
                        return i*i
                    fs.append(f)
                    
            
-   匿名函数：lambda关键字    
    
        用法：
        lambda x:x*x      lambda （传入的参数）：运算
        自动返回运算结果

-    装饰器
        高阶函数覆盖原函数
        python中内置的@语法就是为了简化修饰器
        1. 无参数的decorator
            用法是：
            在需要装饰的函数前添加@（装饰器函数名）的标签
            f则作为参数传入装饰器中

            示例代码：
            import time
            def performance(f):
                def fn(*arg,**kw):
                    t1=time.time()
                    r = f(*arg,**kw)
                    t2 =time.time()
                    print ('call %s() in %fs' %(f.__name__,(t2 - t1))
                    return r
                return fn
                
            @performance    #将@此段注释掉之后
            def factorial(n,m):
                return reduce(lambda x,y: x*y, range(n, m+1))
            #若将@注释掉 @performance 同 factorial = performance(factorial)
            print factorial(1,10)
            
            代码解释：
            
            添加@performance 标签后
            factorial函数注入performance函数中且返回一个装饰后的新的函数
            
2.带有参数的decorator
            
            示例代码
            import time 
                def performance(unit):
                    def x(f):
                        def fn(*arg,**kw):
                            t1=time.time()
                            r = f(*arg,**kw)
                            t2 =time.time()
                            t=(t2-t1)*1000 if unit=='ms' else (t2-t1)
                            print 'call %s() in %f %s' %(f.__name__,t,unit)
                            return r
                        return fn
                    return x
            @performance('ms')
            def factorial(n):
                return reduce(lambda x,y: x*y, range(1, n+1))
            print factorial(10)
        3.@functools 
        
 Python内置的functools可以用来自动化完成把原函数的所有必要属性都一个一个复制到新函数上

            示例代码：
                import time, functools  #引入functools包
                def performance(unit):
                    def perf_dec(f):
                        @functools.wraps(f)  #使用此标签将f函数的信息拷贝到wrapper
                        def wrapper(*args, **kw):
                            t1=time.time()
                            r=f(*arg,**kw)
                            t2=time.time()
                            t=(t2-t1)*1000 if unit=='ms' else (t2-t1)
                            print 'call %s in %f %s' %(f.__name__,t,unit)
                            return r
                        return wrapper
                    return perf_dec
                @performance('ms')  
                def factorial(n):
                    return reduce(lambda x,y: x*y, range(1, n+1))
                print factorial.__name__
                

python含有的装饰器：

        1）@property 装饰器
        既要保护类的封装特性，又要让开发者可以使用“对象.属性”的方式操作操作类属性，除了使用 property() 函数，Python 还提供了 @property 装饰器。通过 @property 装饰器，可以直接通过方法名来访问方法，不需要在方法名后添加一对“（）”小括号。
        
        2）@classmethod
        将一个类的函数定义为 类函数
        
        3）@abc.abstractmethod
        将类中的函数设置为虚函数，必须在继承时实例化
        例如：
        class BaseService(metaclass=abc.ABCMeta):
            #1. 第一种解决方案： 在父类的方法中抛出异常
            # def login(self):
            #     raise NotImplementedError
            #2. 第二种解决方案： 使用抽象基类
            @abc.abstractmethod      # 抽象基类装饰器
            def login(self):
                pass
            @abc.abstractmethod
            def check_cookie(self, cookie_dict):
                pass
                
                
        
                
4.偏函数
    
        functools.partial()可以创建一个偏函数
        functools.partial可以把一个参数多的函数变成一个参数少的新函数，少的参数需要在创建时指定默认值，
        例如：
        import functools
        int2 = functools.pratial(int , base = 2)
        print(int2('1000'))
        

        
   
   
   
11.面向对象
---
-   定义类并实例化对象

        class Person:
            def __init__(self,name,gender,birth):
                self.name=name
                self.gender = gender
                self.birth = birth
        p1 = Person('name',12,'2020')
        
        #除了使用 self.name = name创建属性还可以使用 setattr(self, 'name', 'xxx') 设置属性。

-   属性的访问限制
    Python对属性权限的控制是通过属性名来实现的，如果一个属性由双下划线开头(__)，该属性就无法被外部访问。例如：

        class Person:
            def __init__(self,name,score):
                self.name =name
                self.__score =score
        

-   类属性 （c++类中的静态属性）
    类属性是直接绑定在类上的，所以，访问类属性不需要创建实例，就可以直接访问
    例如：

            class Person:
                count = 0
                def __init__(self,name):
                    Person.count+=1
                    self.name =name
    由于Python是动态语言，类属性也是可以动态添加和修改的
    
    当类属性设置为 __count 私有类属性时，只有类中的成员函数可以调用这个属性
    例如：
        
            class Person:
                __count = 0
                def __init__(self,name):
                    self.name =name
                def c ():
                    Person.__count+=1
                    
    

> 类属性名与对象属性名冲突：
        当实例属性和类属性重名时，实例属性优先级高，它将屏蔽掉对类属性的访问
        如果对象没有实例化属性，则会使用类属性
        
    - 类方法
    使用@classmethod可以将方法绑定到类名上从而成为类方法
    
            class Person:
                __count = 0
                def __init__(self):
                
                @classmethod
                def get_c(cls):    ###cls
                    return cls.__count
                    
-  类继承
 例如：

        class Student(Person):  #Student继承自Person
            def __init__(self, name, gender, score):
                super(Student, self).__init__(name, gender)
                #使用super初始化父类
                self.score = score
                
                Person.__init__(self,name,gender)
                #第二种初始化父类
                
 多继承

        class Student(Person,A):    #Student继承Person，和A两个父类
-   多态

-   获取对象

        filter（）
        
        getattr(对象,字段[值])
        例:
            getattr(s,"age") #无age字段则报错
            getattr(s,"age",20) #无age字段则返回 20
        
        setattr(对象,属性名，属性值)  向类中新加一个属性
        例如：
            class Student():
                def __init__(self,name,gender,**kw):  
                #kw可接收任意数量的新字段  **为关键字参数封装为dict
                    self.name = name
                    self.gender = gender
                    for k,v in kw.items():
                        setattr(self,k,v)
-   Python中的@property 将函数设置为可以类似于属性的调用

        class Student:
            def __init__(self,name,score):
                self.name=name
                self.__score = score
            @property
            def score(self):
                return self.__score
            @score.setter
            def score(self,score):
                if score<0 or score<100:
                    return 'Error!'
                else :
                    self.__score = score


