# Swift
利用强大的开放式语言构建应用

## Swift是什么

Swift是编写程序的绝佳选择,无论是手机,电脑还是服务器, 对于任何能运行代码的设备都是如此.
它是一门集现代语言之大成,集结了Apple的工程师文化精髓以及开源社区的多样化于一身的编程语言.编译器为专为性能所调优,语言专为开发所优化,二者绝不互相妥协.

Swift语言还对新的程序员十分友好.它是第一个工业级系统编程语言,却又像脚本语言那样富有张力且十分有趣.
你可以在Playground编写代码并实时查看Swift代码的运行结果,完全不需要再次从头编译.

Swift通过向其他现代编程语言学习,定义了大量类来避免常见的编程错误:

- 变量会在使用前进行初始化
- 数组索引会检查越界错误
- 整数会检查溢出
- 可选项保证了nil值会显式处理
- 拥有完善的内存自动管理
- 优秀的错误处理机制允许从意外错误中恢复控制
Swift代码为大部分现代硬件编译与优化.语法与基本库都基于统一的,先进的指导性原则设计,这显然也是程序语言使用的最佳方式.这使得集安全与速度于一身的Swift适用于任何场景,从编写"Hello, world"到制作一个操作系统,Swift都是你的最优选择.

Swift用轻量级的语法集合强大的类型接口与模式匹配,能够把复杂的想法以简洁优雅的形式表达.得益于此,代码不仅更易于书写,还变得更加易读与进行重构.

Swift已经投放市场多年,它还会继续演进,它将会带来更多的新特性与新功能.我们对Swift语言的发展充满信心,我们期待着你使用Swift进行开发!

## 概览

若要编写Swift代码,你需要一台装有Xcode或者Playground的Apple设备,或在任何设备上安装VScode与Swift扩展.
请注意,这不是一本面向完全初学者的使用手册.对于部分难以用语言描述的内容,我们将尝试着提供`等效的`Java与C#代码.

### 值

使用`let`来声明一个常量,用`var`来声明一个变量.
常量的值在编译时并不要求已知,但是你必须为其赋值一次.
你可以使用隐式的声明方式,即不在声明时指定值的类型,编译器会尽可能地进行类型判定,但判定通常会以失败告终.

```Swift
var em:String="QAQ"//显式声明
var emm="qwq"//隐式声明
```

值绝对不会隐式地转换为其他类型.如果你需要将一个值转换为不同的类型,需要使用对应的类型显式地声明,像这样:

```Swift
var bili=String(23333)
```

使用方括号来声明数组或字典,并使用方括号来使用它.数组的序数从零开始.

```Swift
var list:[Int]=[233,23333,2333333]
list[0]=666
```

你需要在创建空字典时添加冒号.
```Swift
var dic=[:]
var qwqdic=[Int:String]()//初始化器
```

添加问号以使得值可为nil.
```Swift
var value[Int?]=nil
```

### 流

使用`if`与`switch`来做逻辑判断.使用`for-in`,`for`,`while`与`repeat-while`来循环.使用括号包括条件或者循环变量不再是强制的了,不过仍旧需要使用大括号包括代码块.

```Swift
for em in ["qwq","QAQ"]{
    if 1=1{//不能直接写1,不会进行隐式转换
            Print(em)
        }
}
```
双问号表示"如果值为nil则将其更换为",并不是逻辑判断符号.双等号表示等于,叹号等号表示不等于.

```Swift
var null:String?==nil
var full:String="something"
var thing=null??full
```

Switch选择语句支持任意类型的数据与各种类型的比较操作.

```Swift
switch qwq{
    case "qwq":
    //不知道该做什么......
    case "QAQ":
    //这里也不知道该做些什么
    default:
    //好耶qwq
}
```
你可以使用`for-in`来遍历字典中的项目,这需要提供一对变量来储存键值对.字典使用无序集合,所以键值的遍历也是无序的.

```Swift
for (key,value) in ["1":1,"2":2,"3":3]{
    AArray[value]=key
}
```

使用`while`来重复代码块直到条件改变.循环的条件可以放置于末尾,这样可以保证循环至少运行一次.

```Swift
repeat{
    num=num*2
}while num<10
```

使用 `..<`或`...`以使用一个序列.

```Swift
for i in 0..<3{
    //不包括3
}
for i in 0...3{
    //包括3
}
```

## 函数

当函数作为类型时,其被声明为一级类型,可以作为参数使用.

```Swift
var write={
    (text:String)->String in
    Print(text)
    return "qwq"
}
```

当需要实现复杂声明,比如声明运算符时,可以写为:

```Swift
public func ==(left:ANewType,right:ANewType)->bool{//将会在`类`相关的内容中提到为什么需要新的类型
    return true
}
```

在函数名后面添加括号以调用函数,在没有上下文时函数只代表做一件事,在存在上下文的情况下函数表示其返回值.

```Swift
write(text:"qwq")
var note=write("text")
```

## 类

通过在`class`后接类名来创建一个类.

```Swift
class cat{

}
```

类中应当有一个初始化器,以规定该类型的对象应该成为的样子.
类中包含该类型应有的属性与函数,类中的函数应视作该类型对象可以进行的行为.

```Swift
class cat{
var cute:Bool
    public func 喵()->String{
        return "喵"
    }
    init(cute:Bool){
    self.cute=cute
    }
}
```

声明子类时在名字后面加上父类的名字,以冒号分隔.创建子类时不需要从标准根类来继承,所以你可以按需包含或者去掉父类声明.
子类继承父类的属性与函数,因此子类在重写父类函数时需要声明重载.

```Swift
class people:cat{
    var name:String
    init(cute:Bool,name:String){
        self.name=name
        super.init(cute:cute)
    }
    override func 喵()->String{
        return "qwq"
    }
}
```

当你需要在一个值被赋值前执行代码,你可以使用`willset`,当你需要在一个值被赋值后执行代码,你可以使用`didset`.

```Swift
class cat{
    var cute:Bool{
        willset{
            //做些什么
        }
        didset{
            //做些什么
        }
    }
}
```
