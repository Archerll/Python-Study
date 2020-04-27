# Python必刷面试题

标签（空格分隔）： Python

---

1、一行代码实现1—100之和

    reduce(lambda x,y:x+y for i in range(1,101))

2、如何在一个函数内部修改全局变量

     global

3、列出5个python标准库

    os,sys,re,
    
4、字典如何删除键和合并两个字典
    
    del和update方法
    del dict["key"]
    dict.update(dict2)
    
5、**谈下python的GIL**

    全局解释器锁：为了增强python多线程时的线程安全，只有当一个线程结束或者阻塞时，才将锁释放。

6、python实现列表去重的方法

    转set（）再转list（）
    
7、fun(*args,**kwargs)中的*args,**kwargs什么意思？

    *args，**kwargs都是不确定参数
    *args会将参数转换成tuple
    **kwargs会转成dict

8、python2和python3的range（100）的区别

    python2中range（100）是生成一个列表用来迭代
    python3中range（100）是生成一个可供迭代的range对象，而在python2中可以用xrange实现，这样可以减少内存开销。

9、一句话解释什么样的语言能够用装饰器?
    
    函数可以作为参数传递的语言，可以使用装饰器

10、python内建数据类型有哪些

    int float string bool list tuple set dict

11、简述面向对象中__new__和__init__区别

    init 在对象创建时调用，
    new 在对象创建前调用，并返回给init.

    __init__是初始化方法，创建对象后，就立刻被默认调用了，可接收参数
　　1、__new__至少要有一个参数cls，代表当前类，此参数在实例化时由Python解释器自动识别

　　2、__new__必须要有返回值，返回实例化出来的实例，这点在自己实现__new__时要特别注意，可以return父类（通过super(当前类名, cls)）__new__出来的实例，或者直接是object的__new__出来的实例

　　3、__init__有一个参数self，就是这个__new__返回的实例，__init__在__new__的基础上可以完成一些其它初始化的动作，__init__不需要返回值

　　4、如果__new__创建的是当前类的实例，会自动调用__init__函数，通过return语句里面调用的__new__函数的第一个参数是cls来保证是当前类实例，如果是其他类的类名，；那么实际创建返回的就是其他类的实例，其实就不会调用当前类的__init__函数，也不会调用其他类的__init__函数。
　　

**12、简述with方法打开处理文件帮我我们做了什么？**

    with方法帮我们实现了finally中f.close

13、列表[1,2,3,4,5],请使用map()函数输出[1,4,9,16,25]，并使用列表推导式提取出大于10的数，最终输出[16,25]

    list = []
    for i in filter(lambda x:x>10,map（lambda x:x*x, [1,2,3,4,5]）):
        list.append(list)
    print(list)

14、python中生成随机整数、随机小数、0—1之间小数方法
    
    random.randint()
    random.random()

15、避免转义给字符串加哪个字母表示原始字符串？

    r"string\n"  输出 string\n
    
**16、`<div class="nam">中国</div>`，用正则匹配出标签里面的内容（“中国”），其中class的类名是不确定的**
    
    r"<div class=".*">(.*?)</div>"
    
17、python中断言方法举例

    在做单元测试时，用断言抛出测试结果

18、**数据表student有id,name,score,city字段，其中name中的名字可有重复，需要消除重复行,请写sql语句**

    select distinct name from student

19、10个Linux常用命令

    mkdir cd ls tree rm cp rename
    grep 查找
    top 占用最多资源的进程 
    ping 查看连接状态
    kill ps 杀死进程，查看进程
    telnet

20、python2和python3区别？列举5个
    
    2,3 的print
    3的map reduce filter 变为迭代器
    2中的xrange，和range。在3中统一为range
    2默认ascii编码，3默认utf8编码
    2中 / 除法默认int，3中 / 除法默认浮点型，使用 // 为默认int
    

21、列出python中可变数据类型和不可变数据类型，并简述原理

    可变对象和不可变对象，可变对象又list和dict、set，其他都是不可变对象

22、s = “ajldjlajfdljfddd”，去重并从小到大排序输出”adfjl”

    s=set(s)
    s=list(s)
    s.sort(reverse=False)
    

23、用lambda函数实现两个数相乘

    lambda x,y:x*y

24、字典根据键从小到大排序dict={“name”:”zs”,”age”:18,”city”:”深圳”,”tel”:”1362626627”}

    s = sorted(dict.items(),key=lambda i:i[0],reverse = False)

25、利用**collections库的Counter方法**统计字符串每个单词出现的次数”kjalfj;ldsjafl;hdsllfdhg;lahfbl;hl;ahlf;h”

    res = Counter(a)

26、**字符串a = “not 404 found 张三 99 深圳”，每个词中间是空格，用正则过滤掉英文和数字，最终输出”张三  深圳”**

    # 先找出字母和数字，然后删掉原文中的字母和数字
    a = a.split(" ")
    list = re.findall("\d+|[a-zA-Z]+",a)
    for i in list:
        if i in a:
            a.remove(i)
            

27、filter方法求出列表所有奇数并构造新列表，a =  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

    list = []
    a =  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    for i in filter(lambda x:x%2==1,a)
        list.append(i)
    print(list)

28、列表推导式求列表所有奇数并构造新列表，a =  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

    [ i for i in a if i%2!=0]

29、**正则re.complie作用**

    re.compile是将正则表达式编译成一个对象，加快速度，并重复使用

30、a=（1，）b=(1)，c=(“1”) 分别是什么类型的数据？

    tuple int string

31、两个列表[1,5,7,9]和[2,2,6,8]合并为[1,2,2,3,6,7,8,9]
    
       def F(a,b):
        a_index = 0
        b_index = 0
        list=[]
        while a_index<len(a) and b_index<len(b):
            if(a[a_index]<b[b_index]):
                list.append(a[a_index])
                a_index+=1
            else:
                list.append(b[b_index])
                b_index+=1
        if a_index<len(a):
            for i in a[a_index:]:
                list.append(i)
        if b_index<len(b):
            for i in b[b_index+1:]:
                list.append(i)
        print(list)

    
32、用python删除文件和用linux命令删除文件方法

33、log日志中，我们需要用时间戳记录error,warning等的发生时间，请用datetime模块打印当前时间戳 “2018-04-01 11:38:54”

34、数据库优化查询方法

35、请列出你会的任意一种统计图（条形图、折线图等）绘制的开源库，第三方也行

    matplitlab

36、写一段自定义异常代码

    class MyException（Exception）：
    （为什么不是继承baseException，因为继承baseException，）

37、正则表达式匹配中，（.）和（.?）匹配区别？

    .是贪婪匹配
    .?是非贪婪匹配

**38、简述Django的orm**

39、[[1,2],[3,4],[5,6]]一行代码展开该列表，得出[1,2,3,4,5,6]

    a = [[1, 2], [3, 4], [5, 6]]
    print([j for i in a for j in i])

40、x=”abc”,y=”def”,z=[“d”,”e”,”f”],分别求出x.join(y)和x.join(z)返回的结果

    

41、举例说明异常模块中try except else finally的相关意义

    try下是可能出现异常的代码，try没有成功，则excpet捕捉异常且进行处理，若try成功则可以在运行else下的代码

42、python中交换两个数值

    a,b=ba

43、举例说明zip（）函数用法
    
    可以将两个列表按key：value的方式组装在一起
    
44、**a=”张明 98分”，用re.sub，将98替换为100**

45、写5条常用sql语句

46、a=”hello”和b=”你好”编码成bytes类型

47、[1,2,3]+[4,5,6]的结果是多少？

48、**提高python运行效率的方法**

    使用合适的数据结构和算法
    区分cpu密集型和io密集型程序，使用不同的多核策略

49、简述mysql和redis区别

    mysql 是关系型数据库
    redis 是Nosql数据库，存储方式是key：value

50、遇到bug如何处理

51、1、正则匹配，匹配日期2018-03-20


52、list=[2,3,5,4,9,6]，从小到大排序，不许用sort，输出[2,3,4,5,6,9]

    冒泡排序：
    length = len(list)
    for i in range(length):
        for j in range(i,length-1):
            if list[j]>list[j+1]:
                list[j],list[j+1] = list[j+1],list[j]

53、**写一个单列模式**



54、保留两位小数
题目本身只有a=”%.03f”%1.3335,让计算a的结果，为了扩充保留小数的思路，提供round方法（数值，保留位数）

55、求三个方法打印结果

56、列出常见的状态码和意义

    200 请求成功
    300+：网页重定向
    400+：页面请求错误
    500+：服务器请求错误

57、分别从前端、后端、数据库阐述web项目的性能优化

58、使用pop和del删除字典中的”name”字段，dic={“name”:”zs”,”age”:18}

59、**列出常见MYSQL数据存储引擎**

    如果数据表需要事务处理，应该考虑使用 InnoDB，因为它完全符合 ACID 特性。
    如果不需要事务处理，使用默认存储引擎 MyISAM 是比较明智的

60、计算代码运行结果，zip函数历史文章已经说了，得出[(“a”,1),(“b”,2)，(“c”,3),(“d”,4),(“e”,5)]

61、简述同源策略

62、**简述cookie和session的区别**



63、**简述多线程、多进程**

    进程是运行时程序的封装，是系统资源分陪和调度的基本单位，

64、简述any()和all()方法

65、IOError、AttributeError、ImportError、IndentationError、IndexError、KeyError、SyntaxError、NameError分别代表什么异常

66、python中copy和deepcopy区别

    浅拷贝和深拷贝
    copy是浅拷贝，只会copy一层引用，例如一个二维list,a[1,2,[3,4]],b是a的浅拷贝，修改b中的3,4为5,6，a 中也会发生改变
    
    
**67、列出几种魔法方法并简要介绍用途**

68、C:\Users\ry-wu.junya\Desktop>python 1.py 22 33命令行启动程序并传参，print(sys.argv)会输出什么数据？

69、请将[i for i in range(3)]改成生成器

    for i in range(3):
        yield i 
    or 直接用 range(3)
    
70、a = “  hehheh  “,去除收尾空格

71、**举例sort和sorted对列表排序**，list=[0,-1,3,-10,5,9]

72、对list排序foo = [-5,8,0,4,9,-4,-20,-2,8,2,-4],使用lambda函数从小到大排序

    

73、使用lambda函数对list排序foo = [-5,8,0,4,9,-4,-20,-2,8,2,-4]，输出结果为
[0,2,4,8,8,9,-2,-4,-4,-5,-20]，正数从小到大，负数从大到小



74、列表嵌套字典的排序，分别根据年龄和姓名排序

75、列表嵌套元组，分别按字母和数字排序

76、列表嵌套列表排序，年龄数字相同怎么办？

77、根据键对字典排序（方法一，zip函数）

78、根据键对字典排序（方法二,不用zip)

79、列表推导式、字典推导式、生成器

80、最后出一道检验题目，根据字符串长度排序，看排序是否灵活运用

81、举例说明SQL注入和解决办法

82、s=”info:xiaoZhang 33 shandong”,用正则切分字符串输出[‘info’, ‘xiaoZhang’, ‘33’, ‘shandong’]

83、正则匹配以163.com结尾的邮箱

84、递归求和

85、**python字典和json字符串相互转化方法**

86、**MyISAM 与 InnoDB 区别：**

87、统计字符串中某字符出现次数

88、字符串转化大小写

89、用两种方法去空格

    list = a.split(" ")
    a = "".join(list)

90、正则匹配不是以4和7结尾的手机号

91、简述python引用计数机制

    python的内存管理

92、int(“1.4”),int(1.4)输出结果？

93、列举3条以上PEP8编码规范

    类名是驼峰式编码
    私有属性 _
    模块名是小写

94、正则表达式匹配第一个URL

95、正则匹配中文

96、简述乐观锁和悲观锁



97、r、r+、rb、rb+文件打开模式区别

98、Linux命令重定向 > 和 >>

99、正则表达式匹配出 `<html><h1>www.itcast.cn</h1></html>`

    r'<html><h1>(.*?)</h1></html>'

100、python传参数是传值还是传址？

    其实是要区别，是传递可变对象还是不可变对象

101、求两个列表的交集、差集、并集

    list(set(a)&set(b))
    list(set(a)-set(b))
    list(set(a)|set(b))

102、生成0-100的随机数

    random.randint(0,100)

103、lambda匿名函数好处

    一行代码就可以定义一个简单的函数

104、常见的网络传输协议

    tcp/ip协议

105、单引号、双引号、三引号用法

    单引号，双引号，三引号的作用都是可以定义字符串，
    单引号和双引号相似不可以随意换行，单引号中可以嵌套双引号，双引号中可以嵌套单引号。
    三引号可以作为注释使用

106、**python垃圾回收机制**

    1.引用计数 使用一个int对一个对象的引用数进行记录
    2.标记清除 对象互相引用，当del之后，引用计数都没有为0，所以就无法对其进行回收，原理：根对象寻找所以可达的点，而不可达的点，则被认为没有其他的对象引用他们，就将这种点进行标灰
    3.分代回收

107、HTTP请求中get和post区别

    GET数据传输安全性低，POST传输数据安全性高，因为参数不会被保存在浏览器历史或web服务器日志中；

    在做数据查询时，建议用GET方式；而在做数据添加、修改或删除时，建议用POST方式；

    GET在url中传递数据，数据信息放在请求头中；而POST请求信息放在请求体中进行传递数据；

    GET传输数据的数据量较小，只能在请求头中发送数据，而POST传输数据信息比较大，一般不受限制；

    POST 请求可能会导致新的资源的建立和/或已有资源的修改
    
    在执行效率来说，GET比POST好


108、python中读取Excel文件的方法

109、简述多线程、多进程

110、python正则中search和match

    match()函数只检测 RE 是不是在 string 的开始位置匹配，
    search()会扫描整个 string 查找匹配；
    也就是说 match()只有在 0 位置匹配成功的话才有返回，
    如果不是开始位置匹配成功的话，match()就返回 none。
————————————————


补充：

1.python实现单例模式

    class Singleton:
        def __new__(cls,*args,*kwargs):
            if not hasattr(cls,"_instance"):
                _instance = super().__new__(cls,*args,*kwargs)
                cls._instance = _instance
            return cls._instance

2.线程安全

    一个操作可以再多线程环境中安全使用->原子操作
    
3.线程同步
    
    互斥量机制
    信号量机制

4.如何进行sql查询优化

    1）储存引擎选择：如果数据表需要事务处理，应该考虑使用 InnoDB，因为它完全符合 ACID 特性。如果不需要事务处理，使用默认存储引擎 MyISAM 是比较明智的
    2）尽量避免全表索引
    3）在where中尽量不对null进行判断，避免使用 != 或 <>，避免使用 or 来连接条件，这些都会让数据库放弃索引进行全表扫描
    
