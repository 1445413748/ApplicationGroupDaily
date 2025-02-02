## 一.static（静态）关键字
#### 1. 用法
是一个修饰符，用于修饰成员（成员变量，成员函数）；
#### 2.被修饰的成员具备特点
###### 2.1随着类的加载而加载

- 也就说：静态会随着类的消失而消失，说明它的生命周期最长；

###### 2.2优先于对象存在

- 静态是先存在的，对象是后存在的；

###### 2.3==被所有对象共享==

###### 2.4多了一个调用方式
- （除了可以被对象调用外）可以直接被类名所调用（类名.静态成员）；

#### 3.实例变量（即成员变量）和类变量（即静态的成员变量）的区别：

###### 3.1存放位置

- 类变量随着类的加载而存在于方法区（即共享区）中；
- 实例变量随着对象的建立而存在于堆内存中；

###### 3.2生命周期

- 类变量生命周期最长，随着类的消失而消失；
- 实例变量生命周期随着对象的消失而消失；

#### 4.使用注意

- 静态方法只能访问静态成员（包括变量和函数）；非静态方法既可以访问静态，也可以访问非静态；
- 静态方法中不可以定义this，super关键字（因为静态优先于对象存在）
- 主函数是静态的；

#### 5.有利有弊
- **利**：对对象的共享数据进行单独空间的存储，节省空间；没有必要每一个对象中都存储一份；

可以直接被类名调用；
- **弊**：生命周期过长； 访问出现局限性

#### 6.什么时候使用静态

- **静态变量（类变量）**：当对象中出现共享数据时，该数据被静态所修饰；

而对象中的特有数据要定义成非静态存在于堆内存中；
- **静态函数**：当功能内部没有访问到非静态数据（对象的特有数据）时，该功能可以定义成静态；

#### 7.应用（工具类）
- 每一个应用程序中都有**共性的功能**，可将这些功能进行抽取，独立封装，以便复用；
- 将方法都**静态**，可便于使用，但是该类还是可被其他程序建立对象，可将构造函数**私有化**，强制让该类不能建立对象
- 接下来将class文件发送给其他人，只要将该文件设置到classpath路径下，就可**使用该工具类**； 
要知道类中定义的方法，需要使用**说明书**
- java的说明书通过**文档注释**来完成
- 引伸：java的软件**包**就有很多工具类

## 二.api帮助文档的制作

cmd中输入   
javadoc -d（表示当前目录） test(文件夹) -author -version ArrayTool.java(工具类)

## 三.主函数

#### 1.主函数
是一个特定的函数，作为程序的入口，可以被jvm调用；

#### 2.主函数的定义

- **public**：代表着该函数访问权限是最大的；
- **static**：代表主函数随着类的加载就已经存在了；
- **void**：主函数没有具体的返回值；
- **main**：不是关键字，是一个特殊的单词，可以被jvm识别；
- **（String[ ] arr）**：函数的参数，参数类型是一个数组，该数组中的元素是字符串；字符串类型的数组；
- 主函数是**固定格式**的：jvm识别（可重载但不识别）；
- jvm在调用主函数时，传入的是new String[0]；

## 四.静态代码块

#### 1.格式
static

{
    静态代码块中的执行语句
}
#### 2.特点
- 随着类的加载而执行，并优先于主函数，**只执行一次**；
- 用于给类进行初始化；

## 五.对象的初始化过程
**Person p = new Person("zhangsan",20);**

1.因为new用到了Person.class，所以先找到该class文件并**加载**到内存中；

2.如果有的话，执行该类中的**static代码块**，给Person.class类进行初始化；

3.在**堆内存**中开辟空间，分配内存地址；

4.在堆内存中建立对象的特有属性，并进行**默认初始化**；

5.对属性进行**显示初始化**；

6.对对象进行**构造代码块**初始化；

7.对对象进行对应的**构造函数**初始化；

8.将内存地址赋给**栈内存**中的p变量；

## 六.对象调用成员过程

## 七.单例设计模式
#### 1.设计模式
解决某一类问题最行之有效的方法；

#### 2.单例设计模式
java中23中设计模式之一，解决一个类在内存只存在一个对象；

#### 3.步骤
- **将构造函数私有化**：禁止其他程序建立该类对象；
- **在类中创建一个本类对象**：让其他程序可以访问该类对象；
- **提供一个方法可以获取到该对象**：方便其它程序对自定义对象的访问

==当需要将事物的对象保证在内存中唯一时，就将以上的三步加上即可==

#### 4.代码例子
private static Student s = new Student();

private Student(){}

public static Student getStudent()

{
    return s;
}

#### 5.方式二（建议使用方式一）

- **方式一**：先初始化对象（饿汉式）；
- **方式二**：对象时方法被调用时才初始化，也叫做对象的延时加载（懒汉式）

private static Single s = null;

private Single(){}

public static Single getInstance()

{
    
    if(s==null)
    
    {
    
        synchronized(Single.class)
        
        {
            
            if(s==null)
            
                s = new Single();
        }
    
    }
    
    return s;
    
}