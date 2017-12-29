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
