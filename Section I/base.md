# Swift 基本语法 

##注释
```
//这是单行注释

多行注释，哈 笨办法就是 多条单行注释
//第一行注释
//第二行注释

但是呢 有一个愉快的方式
/*
这里是注释哦
想写什么都可以
...
*/

复杂的注释情况，嵌套 (这种好像没啥必要吧)

/*
  外层注释
  balabala...
  /*
    内层注释
    balabala...
  */
  
*/

```
##打印
```
/*
  很多情况下，我们需要在控制台打印内容以判断程序的运行情况。
  想必你对NSLog(@"balabala...") 还是不能忘怀，没关系这里都是新的内容。
*/

print("嗨，这句话会出现在控制台哦~~~  终于摆脱Objective-C 的@了，幸运")

//源文件中的定义
public func print(_ items: Any..., separator: String = default, terminator: String = default)
public func print<Target>(_ items: Any..., separator: String = default, terminator: String = default, to output: inout Target) where Target : TextOutputStream

/*
从这里开始，需要注意了。相较于OC，语句的结尾再也不用带上拖油瓶了 对就是它 ";"
另外，print 函数也体现了Swift下重载的概念。
那些让你觉得蒙蒙的字符，这里剧透下。
<Target> //泛型
_ //忽略符，这里用于隐去外部参数名 
inout //还记得传址参数的概念么，该关键字就是用来表明这种行为的。
Any //public typealias Any = protocol<> ,Swift中任何类型（如Int、String、Struct、Enum...）都会遵循这个协议，反过来说Any可以用来表示任何类型。
... //表示可变参数
//eg: (to output: inout Target) 关于内部参数名和外部参数名
// to 是外部参数名，表示外部在调用此函数时必须显式的携带to这个参数名。
// output 是内部参数名，表示函数实体内部使用此参数名进行调用。 

*/

```
##基础运算符
常见的加减乘除Swift当然也要有
+ eg.: 1 + 2 
- eg.: 3- 2
* eg.: 3*6
/ eg.: 4/5

这里停顿下，这些操作符很简单吧 但是上面的例子是有错误的，是语法错误。
```
+ eg.: 1 + 2  
- eg.: 3- 2  // Error
* eg.: 3*6
/ eg.: 4/5

/*
这个问题涉及到操作符的 关联性 associativity 和 优先级 precedence.(自定义操作符的时候，你会体会深刻) 

运算符使用的位置： prefix、infix、postfix 
associativity 有三个值：left、right、none
precedence 默认值是：100

示例中操作符属于infix，所以swift 建议在操作符前后添加空格或移除掉空格。这应该是编译器特性导致的，所以要有一定规范。
*/

//浮点型计算
22.0 / 7.0 
//除余计算
28 % 10 
(28.0).truncatingRemainder(dividingBy: 10.0) (等同于上面的表达式)

/*
移位操作 这个有基础的应该都了解了
这里主要说一下，移位运算相对于其它操作会高效。
*/
<<、>>  

/*
运算符的优先级及结合方向（这一点和其它编程语言以及数学上概念没有不同）
明智的做法是，在表达式中嵌入（）显式的为编译器提供运算依据。
*/
((8000 / (5 * 10)) - 32) >> (29 % 5)
350 / 5 + 2
350 / (5 + 2)

//数学函数
sin(45 * Double.pi / 180)    //正弦函数
cos(135 * Double.pi / 180)   //余弦函数
(2.0).squareRoot()           //平方根
max(5, 10)                   //双值最大数
min(-5, -10)                 //双值最小数

//eg.:
max((2.0).squareRoot(), Double.pi / 2)

```
//命名空间 相关
```
在Swift中使用Unicode characters命名是合法的。
命名语法
var variableNumber: Int = 42 
这里啰嗦几句
var 关键字表示变量
variableNumber 变量名
: Int 表示类型约束，这种约束语法在Swift中大量存在。这里表明，声明的类型是整型

//虽然使用任意字符进行命名是合法的，但是还是别过火哦  毕竟代码可能别人也会看，需要起有意思的名字。另外驼峰命名法也是不错的规范~~~

//符合运算符
var counter: Int = 0
counter += 1
counter -= 1

//等同于
var counter: Int = 0
counter = counter + 1
counter = counter - 1

counter = 10
counter *= 3
counter /= 2

let a = 3 //常量 let 关键字 

Tip:来丰富下英文词汇
Add: +
Subtract: -
Multiply: *
Divide: /
Remainder: %
Add and assign: +=
Subtract and assign: -=
Multiply and assign: *=
Divide and assign: /=

```







