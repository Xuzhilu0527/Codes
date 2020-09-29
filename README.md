# 学习心得

# 什么是文件扩展名

```
- 文件扩展名（filename extension）也称为文件的`后缀名`，是操作系统用来`标记文件类型`的一种机制。扩展名几乎是每个文件必不可少的一部分。如果一个文件没有扩展名，那么Windows系统就无法处理这个文件，无法判别到底如何处理该文件。就是文件名称中`最后一个.`之后的内容。
``` 

# C语言如何让电脑执行

```
-  通过C语言的语言规则写出一段代码后， `编译器(CComplire.exe)` 把这段源代码编译成机器指令 `(*.obj)`，再使用 `链接器（CCLINKER.EXE）` 把这些机器指令串成一个.EXE文件让机器执行。
```

# 环境变量执行顺序

```
1..在运行应用程序之前对命令行的设置。
2..作为用户变量在 Windows 中的设置。
3..作为系统变量在 Windows 中的设置。
```

# JAVA如何让电脑执行

```
-  通过JAVA语言的语言规则写出一段代码后，`JAVAC编译器（JAVAC.EXE）`把这段源代码编译成 `(*.class)` 文件 { 面向JAVA虚拟机的二进制文件（中间文件）}，再透过`JAVA虚拟机（runtime)` 直接让机器执行
```

25+25+25+50+45+50+50+30+30+50+50+50+30+50+60+80+20+30+15
# javac -d  java -cp

- src 按包名存放.java文件。

- bin 用javac -d 编译出放在根目录下bin文件夹。

- javac -d (想要编译.class文件存放的目录) (按路径（不是包名）输入.java文件目录，多个.java用空格隔开)。

- java -cp (查找main主程序的目录(多在./bin) ) (需要运行的带main方法的主程序的类名。包+类名)

# Properties

- 用于读写配置文件，此文件只能使用ASCII编码。

- 可以从ClassPath或文件系统读取.properties文件。

- 读写Properties时：只使用getProperty()  和 setProperty()方法。


# final关键字

- 一个.java文件只能包含一个public class但可以包含多个非public的class

- final修饰class可以防止被继承，修饰method可以防止被覆写，修饰field可以防止被重新赋值。

- 在Java中，final关键字可以用来修饰类、方法和变量（包括成员变量和局部变量）

- 当用final修饰一个类时，表明这个类不能被继承。也就是说，如果一个类你永远不会让他被继承，就可以用final进行修饰。在使用final修饰类的时候，要注意谨慎选择，除非这个类真的在以后不会用来继承或者出于安全的考虑，尽量不要将类设计为final类。

- 当用final修饰一个方法时，使用final方法的原因有两个。第一个原因是把方法锁定，以防任何继承类修改它的含义；第二个原因是效率。在早期的Java实现版本中，会将final方法转为内嵌调用。但是如果方法过于庞大，可能看不到内嵌调用带来的任何性能提升。在最近的Java版本中，不需要使用final方法进行这些优化了。因此，如果只有在想明确禁止 该方法在子类中被覆盖的情况下才将方法设置为final的。即父类的final方法是不能被子类所覆盖的，也就是说子类是不能够存在和父类一模一样的方法的。final修饰的方法表示此方法已经是“最后的、最终的”含义，亦即此方法不能被重写（可以重载多个final修饰的方法）。此处需要注意的一点是：因为重写的前提是子类可以从父类中继承此方法，如果父类中final修饰的方法同时访问控制权限为private，将会导致子类中不能直接继承到此方法，因此，此时可以在子类中定义相同的方法名和参数，此时不再产生重写与final的矛盾，而是在子类中重新定义了新的方法。（注：类的private方法会隐式地被指定为final方法。）

-final成员变量表示常量，只能被赋值一次，赋值后值不再改变。当final修饰一个基本数据类型时，表示该基本数据类型的值一旦在初始化后便不能发生变化；如果final修饰一个引用类型时，则在对其初始化之后便不能再让其指向其他对象了，但该引用所指向的对象的内容是可以发生变化的。本质上是一回事，因为引用的值是一个地址，final要求值，即地址的值不发生变化。final修饰一个成员变量（属性），必须要显示初始化。这里有两种初始化方式，一种是在变量声明的时候初始化；第二种方法是在声明变量的时候不赋初值，但是要在这个变量所在的类的所有的构造函数中对这个变量赋初值。当函数的参数类型声明为final时，说明该参数是只读型的。即你可以读取使用该参数，但是无法改变该参数的值。


# 不可以继承

```
- 类中的构造方法，只负责创建本类对象，不可以继承。
Java 构造方法有以下特点：
方法名必须与类名相同
可以有 0 个、1 个或多个参数
没有任何返回值，包括 void
默认返回类型就是对象类型本身
只能与 new 运算符结合使用

- 用Private修饰的属性和方法，不可以继承。用final修饰的也不能继承

- 父子类不在同一个package中时，default修饰的属性和方法不可以继承。
```

![avatar](\继承.PNG)

# package 包作用域

- 指一个类允许访问同一个package的：1、没有public\private修饰的class,没有public、protected、private修饰的字段和方法。包名必须完全一致。

# 逻辑运算符

``` 
在java的逻辑运算符中，有这么四类&&（短路与）、&（与）、||（短路或）、|（非短路或）

&&和&都表示与，&&表示第一个条件为false时，后面的条件就不执行，&要对所有的条件都进行判断

||和|都表示或，||表示第一个条件为true时，后面的条件都不判断；| 对所有的条件进行判断
```

# JDK常用的工具类

```
Math:数学计算
Random:生成伪随机数
SecureRandom:生成安全的随机数
BigInteger:任意大小的整数。内部是Int类型数组组成。
BigDecimal:表示任意精度的浮点数
BigInteger和BigDecimal都继承自Number
```

# 程序中的多态

```
- 概念：父类引用指向子类对象，从而产生多种形态。 EX: Animal a = new Dog()

- 二者具有直接或者间接的继承关系时，父类引用可指向子类对象，即形成多态。

- 父类引用仅可以调用父类所声明的属性和方法，不可以调用子类独有的属性和方法。

- 一个对象变量（例如变量e） 可以指示多种实际类型的现象称为多态(polymorphism)    P159
```

# super关键字

```
- super(name, salary, year, month, day)是调用超类Employee中带有name,salary....参数的构造器的简写形式。
```

# 反射

- Java除了基本类型（byte, short, int, long, float, double, boolean, char）外其他都是class(包括Interface,String, Object) 

- JVM为每个加载的Class创建对应的class实例，并在实例中保存该class的所有信息。如果获取了某个class实例，则可以获取到该实例对应的class的所有信息。

- 通过Class实例获取Class信息的方法叫反射（Reflection).

- 反射的目的是当前获得某个Object实例时，我们可以获取该Object的class信息。

- JVM总是动态加载class,可以再运行期根据条件控制加载class.

```
通过Class实例获取field信息：
- getField(name) 获取某个public的field(包括父类)
- getDeclaredField(name) : 获取当前类的某个field(不包括父类)。
- getFields() ： 获取所以public的field(包括父类)。
- getDeclaredFields(): 获取当前类的所有field(不包括父类)
```

```
通过Class实例获取method信息：
- getMethod(name,Class...): 获取某个public的method(包括父类)。
- getDeclaredMeethod(name, Class):获取当前类的某个method(不包括父类)
- getMothods(): 获取所有public的method(包括父类)
- getDeclaredMethods(): 获取当前类的所有method(不包括父类)。
```

```
通过Class实例获取Constructor信息：
- getConstructor(Class..):获取某个public的Constructor
- getDeclaredConstructor(Class..):获取某个Constructor.
- getConstructors(): 获取所有public的Constructor
- getDeclaredConstructors(): 获取所有Constructor.
- 通过设置setAccessible(true)来访问非public的构造方法。
```

```
获取父类的Class:
- Class getSuperclass()
- Object的父类是null
- interface的父类是Null
如果要获取当前类实现的interface:
Class[] cls = Integer.class.getInterfaces(); // [Comparable.class]
Class[] cls  = java.util.ArrayList.class.getInterfaces(); // [List.class, RandomAccess.class, Cloneable.class, Serializable.class]
class[] cls = Math.class.getInterfaces(); // [];
class[] cls = java.util.List.getInterfaces(); // [Collection.class] (interface返回继承的interface)
判断向上转型是否成立
boolean isAssignableFrom(Class)
Integer i = ..; Number x = i ?
Number.class.isAssignableFrom(Integer.class); // true
```

# public static void

``` 
public void定义的是普通的方法，而public static void 定义的是静态的方法。
普通的方法需要new对象去调用，而静态的方法可以直接用类名去调用。
```

## public static void

```
- static 方法可以被main方法直接调用，而非static方法不可以。

- 因为static方法是属于类的，是类方法。可以通过类名，方法名直接调用。

- 而非static方法必须等对象被new出来以后才能使用，因而不能在main中直接调用
```

## public void

```
- 修饰是非静态方法，该类方法属于对象，在对象初始化（new Object()）后才能被调用；

- public static void 修饰是静态方法，属于类，使用类名.方法名直接调用。
```

# 泛型

```
E - Element 元素。
T - Type 类
K - Key 键 
V - Value 值
？ 


 泛型中的约束和局限性
1,不能实例化泛型类
2,静态变量或方法不能引用泛型类型变量，但是静态泛型方法是可以的
3,基本类型无法作为泛型类型
4,无法使用instanceof关键字或==判断泛型类的类型
5,泛型类的原生类型与所传递的泛型无关，无论传递什么类型，原生类是一样的
6,泛型数组可以声明但无法实例化
7,泛型类不能继承Exception或者Throwable
8,不能捕获泛型类型限定的异常但可以将泛型限定的异常抛出



泛型类型继承规则
1,对于泛型参数是继承关系的泛型类之间是没有继承关系的
2,泛型类可以继承其它泛型类，例如: public class ArrayList<E> extends AbstractList<E>
3,泛型类的继承关系在使用中同样会受到泛型类型的影响
```

public class Test {
	public static void main(String[] args) {
		int a = 100;
		//创建对象，对象名为test，通过对象名.show()方法调用
		Test test=new Test();
		//在对象初始化（new Object()）后才能被调用
		test.show(a);
		//直接调用
	7、	hello(a);
	}
	//public void修饰是非静态方法，该类方法属于对象，在对象初始化（new Object()）后才能被调用；
	public void show(int a) {
		System.out.println(a);
	}
	//public static void方法可以被main方法直接调用，而非static方法不可以。
	public static void hello(int a) {
		System.out.println(a);
	}
}
Java 可以`通过对象名调用静态方法`（对象名.静态方法）。Java 中不会导致语法错误（syntax error），但是不推荐这样使用，静态方法与非静态方法调用时应当绝对区分；而且其他 OOP 语言如 C#，Swift，Objective-C 都没有这样的语法。

## 访问控制修饰符

| private | 仅对本类可见 |
| ---     | ---         |
| public  | 对外部完全可见 |
| protected | 对本包和所有子类可见 |
| 不写修饰符 | 默认对本包可见|

 
 - abstract修饰类： 不能new对象，但可以声明引用。

 - abstract修饰方法：只有方法声明，没有方法实现。

 - 抽象类中不一定有抽象方法，但有抽象方法的类一定是抽象类。

 - 子类继承抽象类后，必须覆盖父类中所有的抽象方法，否则子类还是抽象类。

 ## 关于强制类型转换（P167） (尽量少用)

 - 只能在继承层次内进行强制类型转换。

 - 在将超类强制转换成子类之前，应该使用instanceof进行检查   if (staff[1] instanceof Manager) {boss = (Manager) staff[1];}

## 接口（interface）与抽象类的异同

### 相同：

- 可编译成字节码文件（.class）

- 不能创建（new） 对象

- 可以作为引用类型 

- 具备Object类中所定义的方法

### 不同：

- 所有属性都是公开静态常量，隐式的使用public static final修饰。

- 所有方法都是公开抽象方法，隐式使用public abstract修饰。

- 没有构造方法、动态代码块、静态代码块。

 ### Static关键字

 - 静态属性是整个类共同持有的共享空间（一份），任何对象修改都会影响到其他对象。

 - 静态可以修饰属性和方法。

 - 称为静态属性（类属性）、静态方法（类方法）。

 - 静态成员是全类所有对象共享的成员。

 - 在全类中只有一份，不因创建多个对象而产生多份。

 - 不必创建对象，可以直接通过类名访问。

 - 静态方法允许直接访问静态成员，不能直接访问非静态成员（实例）。

 - 静态方法中不允许使用this或者super关键字。

 - 静态方法可以继承，但是不能重写，而且没有多态。

 ### 方法签名

 - 一个方法的修饰符，方法名，方法参数列表以及每一个参数的类型。

 - 方法签名和方法的不同： 有无方法体。

 - 一个类除了成员方法以外还有字段（成员变量）。

### LAMBDA

 - lambda表达式的语法规则：有一标志性的箭头符号（ -> ），箭头符号左边是LAMBDA参数列表（），右边是lambda方法体{}。

 - 自己定义一个类，就做面积比较，有一个方法  接受两个SHAPE 三角形和矩形 ，定义一个Compare 方法。用comparable方法来运行，得到INT值来比较，用lambda。

### 抽象

 - 抽象方法的本质实际上是定义接口规范，给子类继承定义规范

 - 如果一个抽象类没有字段，所以方法全部都是抽象方法就可以把该抽象类改写为接口（interface）

 - 一个类里有什么：方法和属性

 - 定义了抽象方法的类就是抽象类。 

 - 从抽象类继承的子类必须实现抽象方法，如果不实现抽象方法， 则该子类仍是一个抽象类。

 - 子类从父类中继承了什么东西。protected  public

 - overwrite,virtul, abstract.
 
 - abstract修饰类,会使这个类成为一个抽象类,这个类将不能生成对象实例,但可以做为对象变量声明的类型,也就是编译时类型,抽象类就像当于一类的半成品,需要子类继承并覆盖其中的抽象方法。

 - 重写（同名同参） override
重写就是覆盖，动态多态性，同名又同参 好比一个人我不用餐具吃饭了一样我让人喂！这种情况最好把A定义为抽象类，A 的方法 a() 为抽象方法
也就是说某一个类型确定肯定有一个运作，但是这个运作具体该怎么做，在父类型时还无法确定（但是确定一定会有这么一个运作），于是这个运作被定义为抽象。到子类时，这个运作就被具体化了

- 重载（同名不同参）overload 返回值类型和方法名相同，参数列表不同。
重载是静态多态性，即同名不同参 好比一个人可以用不同种餐具。
一.方法名一定要相同。
二.方法的参数表必须不同，包括参数的类型或个数，以此区分不同的方法体。
1.如果参数个数不同，就不管它的参数类型了！
2.如果参数个数相同，那么参数的类型必须不同。
三.方法的返回类型、修饰符可以相同，也可不同。


- 多态的概念： 是指属属性或方法在子类中表现为多种形态 

- void,string....返回值类型

- 方法包括访问修饰符，静态访问修饰符，返回值类型， 方法名，参数列表，方法体。

- 什么是属性： 一个类中定义的字段， 也叫成员变量。

- 什么是参数: 方法中小括号里的，分为参数类型和形式参数。new出来后变成实际参数。

- 重载：（参数列表不同）：1、参数类型不同 2、参数数量不同。

- 一个方法的参数列表，参数类型，参数数量，形式参数，实际参数。属性。

- comparator是一个 函数式接口。

- lambda表达式为什么可以隐式的转换成comparator这个函数式接口：

- 函数式接口 ：  返回值类型 方法名 参数数量 参数类型

- lambda表达式 参数数量 参数类型 箭头符号 方法体 返回值类型 

- 函数式接口：也就是只有一个抽象函数的接口。多一个或者少一个抽象函数都不能定义为函数接口，如果使用了函数接口注解又不止一个抽象函数，那么编译器会拒绝编译。函数接口在使用时候可以隐式的转换成 Lambda 表达式。

```
lambda表达式：
Arrays.sort(array, (s1, s2) -> { retrun s1.compareTo(s2); })
方法引用：
Arrays.sort(array, String::compareTo);
```

### 内部类

- 内部类可以对同一个包中的其他类隐藏。

- 内部类可以访问定义这个类的作用域中的数据，包括原本私有的数据。

- 内部类： 所谓内部类就是在一个类内部进行其他类结构的嵌套操作。

- 编译之后可以生成独立的字节码文件 $隔开

- 内部类可以直接访问外部类的私有成员，而不破坏封装。

- 可为外部类提供必要的内部功能组件。

## 成员内部类

- 在类的内部定义，与实例变量、实例方法同级别的类。

- 外部类的一个实例部分，创建内部类对象时，必须依赖外部类对象
Outer out = new Outer();
Inner in = out.new Inner();

- 当外部类、内部类存在重名属性时，会优先访问内部类的属性。

- 成员内部类不能定义静态成员。

## 静态内部类

- 不依赖外部对象，可直接创建或者通过类名访问，可声明静态成员。

- 只能直接访问外部类的静态成员（实例成员需要实例化外部类对象）
Outer.Inner inner = new Outer.Inner();
Outer.Inner.show();


## 接口

- 接口定义的方法默认是public abstract (不需要写)

- 实现Interface 使用 implements，可以实现多个Interface。

- 在接口中定义default方法，所有子类不必实现此方法也可以实现此接口。

- 一个Interface可以继承自另一个Interface,同样使用extends关键字，相当于拓展了接口的方法。

## List

- 按照索引顺序访问的长度可以变的链表。

- 优先使用ArrayList 而不是LinkedList

- 可以和Array 相互转换。

- boolean contains(Object o) 是否包含o

- int indexOf(Object o) 是否包含某个元素。

- 可以直接遍历，最推荐用foreach

- List元素可以重复，并且元素可以是NULL

- 遍历一个List<E>： 1、使用ger(int index)  2、使用Iterator<E> 3、使用foreach(最推荐)： 
List<String> list = ...
for (String s : list)
{do something}

- 把List<E> 变为Array: 1、Object[] toArray()  2、 <T> T[] toArray(T[] a)

```
如果要在List中查找元素：
1、List的实现类通过元素的equals方法比较两个元素。
2、 放入的元素必须正确的覆写equals方法。（String、Integer等已经覆写了equals)
3、编写equals方法可以借助Objects.equals()判断
如果不在list中查找元素：
1、不必覆写equals方法。、
```

## Map

- Map 是一种键-值（Key-Value)映射表。

- 可以通过Key快速查找Value(元素)。

- 方法： V put(K key, V value):把Key- Value放入Map.
V get(K key): 通过Key获取Value.
boolean containsKey(K key):判断key是否存在于Map.

```
遍历Map:
可以使用foreach循环遍历keySet()
Map<String, Integer> map = ...
for(String key : map.keySet()){
  Integer value = map.get(key);
}

同时遍历Key和Value可以使用foreach循环遍历entrySet()
Map<String, Integer> map = ...
for (Map.Entry<String, Integer> entry : map.entrySet()){
  String key = entry.getKey();
  Integer value = entry.getValue();
}
```

- 最常用的实现类是HashMap,但他内部存储不保证有序，遍历时不一定是put放入的顺序，也不一定是Key的排序顺序。

- SortedMap保证遍历时以Key的顺序排序，其实现类是TreeMap

- 正确的使用Map 必须保证：
1、 作为Key的对象必须正确的覆写equals()方法。
2、 作为Key的对象必须正确的覆写hashCode()方法。如果两个对象相等，则两个对象的hashCode()必须相等。因为HashMap通过计算Key的hashCode()定位Key的存储位置，继而获得Value。
a.equals(b) == true，则a.hashCode() == b.hashCode().

## Set

- Set<E> 用于存储不重复的元素集合：
boolean add(E e)
boolean remove(Object o)
boolean contains(Objec o)
int size()

- 其实相当于不存储Value的Map

- 用于去除重复的元素。

- 放入Set的元素要正确实现equals()和hashCode()

- Set不保证是有些的：
HashSet 是无序的。
TreeSet 是有序的
实现了SortedSet接口的是有序的Set

## Queue

- Queue<E>实现了一个先进先出（FIFO)的队列。
获取队列长度：size()
添加元素到队尾： boolean add(E e)/boolean offer(E e)
获取队列头部元素并且删除：E remove() / E poll()
获取队列头部元素但不删除： E element() / E peek()

- 避免把null添加到队列、

- PriorityQueue<E> 具有Queue<E>接口。也就是Queue<E>的方法都可以使用。但当他从队首获取元素时，总是获取优先级最高的元素。



### IDE

```
IDE 是 Intergreated Development Environment 的缩写，中文称为集成开发环境，用来表示辅助程序员开发的应用软件，是它们的一个总称。
通过前面章节的学习我们知道，运行 C 语言（或 Java 语言）程序必须有编译器，而运行 Python 语言程序必须有解释器。在实际开发中，除了运行程序必须的工具外，我们往往还需要很多其他辅助软件，例如语言编辑器、自动建立工具、除错器等等。这些工具通常被打包在一起，统一发布和安装，例如 PythonWin、MacPython、PyCharm 等，它们统称为集成开发环境（IDE）。
```

0- Editor    文本编辑器。


### 类库 Class Library

```
类库(ClassLibrary)是一个综合性面向对象可重用类型的集合，这些类型包括：接口、抽象类和具体类。类库可以解决一系列常见编程任务（包括诸如字符串管理、数据收集、数据库连接以及文件访问等任务），还可以解决多种专用开发任务（桌面应用程序、WEB应用程序、控制台应用程序等）。
类库字面意思就是类的集合，类库不等于框架(Framework)，Framework 是比类库更高一级的概念。
是一个综合性面向对象可重用类型的集合，这些类型包括：接口、抽象类和具体类。
```

### 键值对  Key-Value Pair

```
是计算机科学技bai术，查du看jdk文档，找MAP接口。键值对存储是数据库最zhi简单的组织形式。
键：就是存的值的编号
值：就是要存放的数据
```

### json 

```
JSON(JavaScript Object Notation, JS 对象简谱) 是一种轻量级的数据交换格式。它基于 ECMAScript (欧洲计算机协会制定的js规范)的一个子集，采用完全独立于编程语言的文本格式来存储和表示数据。简洁和清晰的层次结构使得 JSON 成为理想的数据交换语言。 易于人阅读和编写，同时也易于机器解析和生成，并有效地提升网络传输效率。
{...} 键值对
[... ] 数组
String 字符串
Number 数值（整数和浮点数）
Boolean 布尔值
null 空值
```

## StringBuilder

- 可以高效拼接字符串，因为他是一个可变对象，可以预分配缓冲区

- StringBuilder可以进行链式操作。

- StringBuffer是StringBuilder的线程安全版本。很少使用。

## 包装类型

- JDK为每种基本类型都创建了对应的包装类型：除了int - Integer, char - Character外，其他类型的包装类型就是基本类型的首字母大写。
Interger n = new Integer(99);
int i = n.intValue();

## 强类型语言 java   弱类型语言 javascript/json

```
强类型和弱类型主要是站在变量类型处理的角度进行分类的。
强类型是指不允许隐式变量类型转换，弱类型则允许隐式类型转换。
所以，关键在于变量数据类型的转换。
什么叫隐式类型转换？
隐式是指源码中没有明显的类型转换代码，也就是说，一个变量，你可以直接给他赋值字符串，也可以直接给他赋值数值，你还可以直接让字符串类型的变量和数值类型的变量相加，虽然得出的最终结果未必是你想象的那样，但一定不会报错。
这就是隐式类型转换，弱类型语言，如javascript、php。
Java是强类型语言，不允许隐式类型转换，也就是说，如果你需要拿一个字符串变量当做整型来用，你必须显式地将变量类型转换好。
换句话说：
强类型语言，当你定义一个变量是某个类型，如果不经过代码显式转换（强制转化）过，它就永远都是这个类型，如果把它当做其他类型来用，就会报错
弱类型语言，你想把这个变量当做什么类型来用，就当做什么类型来用，语言的解析器会自动（隐式）转换。
比较
弱类型显然让开发者更省力一些，一些数据类型不是很复杂的场景中基本可以不用关注数据类型的问题，这可以提高开发者的业务处理专注力，提升逻辑开发效率。
但同样，弱类型也因为它的特性，使开发者在开发过程中对变量类型的检测力度不够大，由此提高数据类型方面问题出现的可能性。
另外，弱类型语言的运行效率，内存利用率显然也比不上强类型语言。因为弱类型语言在运行过程中，存在变量类型的隐式转换，多了一些需要执行的操作，并且，分配内存时，会考虑通用而多分配一些，而强类型则专门为各种类型的变量量身定做地分配内存，内存利用率显然比弱类型会高。
选择
对于开发者来说，一般很少会去想，选择什么语言开发，而是去想我学了这门语言，如何找到这门语言的工作。
但其实，语言的选择，是存在的。
比如，你负责一个项目，在做选型的时候，弱类型与强类型的一些优缺点，就是一个需要考虑的因素。
```


Terminal 1.x
PowerShell Core 7.x


- 幂运算：x的a次方 int a = Math.pow(x, a)    需要import static java.lang.Math.*;

- for each 循环： for(int element : a) System.out.println(element);  P81

- 冒泡排序：
 int[] numbers=new int[]{1, 2, 8,3,7,13,54,32,11,4};
        int i,j;
        for(i = 0; i < numbers.length-1; i++) // 死记硬背
        {
            for(j = 0; j < numbers.length-1-i; j++)  // 死记硬背
            {
                if(numbers[j] > numbers[j+1])
                {
                    int temp = numbers[j];
                    numbers[j] = numbers[j+1];
                    numbers[j+1] = temp;
                }
            }
        }
        System.out.println("从小到大排序后的结果是:");
        for(i = 0; i < numbers.length; i++)
            System.out.print(numbers[i] + " ");


# finally关键字

```
finally 关键字用来创建在 try 代码块后面执行的代码块。

无论是否发生异常，finally 代码块中的代码总会被执行。

在 finally 代码块中，可以运行清理类型等收尾善后性质的语句。

finally 代码块出现在 catch 代码块最后，语法如下：

try{
  // 程序代码
}catch(异常类型1 异常的变量名1){
  // 程序代码
}catch(异常类型2 异常的变量名2){
  // 程序代码
}finally{
  // 程序代码
}
```

# Java检查型异常和非检查型异常

```
检查型异常（CheckedException）
在Java中所有不是RuntimeException派生的Exception都是检查型异常。当函数中存在抛出检查型异常的操作时该函数的函数声明中必须包含throws语句。调用改函数的函数也必须对该异常进行处理，如不进行处理则必须在调用函数上声明throws语句。

检查型异常是JAVA首创的，在编译期对异常的处理有强制性的要求。在JDK代码中大量的异常属于检查型异常，包括IOException，SQLException等等。

非检查型异常（UncheckedException）
在Java中所有RuntimeException的派生类都是非检查型异常，与检查型异常对比，非检查型异常可以不在函数声明中添加throws语句，调用函数上也不需要强制处理。
常见的NullPointException，ClassCastException是常见的非检查型异常。非检查型异常可以不使用try...catch进行处理，但是如果有异常产生，则异常将由JVM进行处理。对于RuntimeException的子类最好也使用异常处理机制。虽然RuntimeException的异常可以不使用try...catch进行处理，但是如果一旦发生异常，则肯定会导致程序中断执行，所以，为了保证程序再出错后依然可以执行，在开发代码时最好使用try...catch的异常处理机制进行处理。
```

- java使用异常来表示错误，通过try{} catch{}来捕获异常。

- java的异常是class并且从Throwable继承。

- Error是无需捕获的严重错误，Exception是应该捕获的可处理的错误。

- RuntimeException无需强制捕获，非RuntimeException(checked Exception)需要强制捕获，或者用throws声明。

- try后可以使用多个catch，当catch到后就不会再catch了，所以异常子类必须写在前面的catch中。

- 如果某些异常的逻辑处理相同：不存在继承关系的话必须编写多条catch语句，可以再参数列表里（无继承关系）用 | 表示多种Exception.

- catch住一个异常后又抛出另外一个异常，finally语句会比后抛出异常的语句先执行。如果执行的finally语句中也抛出了一个异常，那么catch中抛出的异常就不会执行了。此未抛出的异常被称为被屏蔽异常。


# 断言

```
1、assert <boolean表达式>
如果<boolean表达式>为true，则程序继续执行。
如果为false，则程序抛出AssertionError，并终止执行。
 
2、assert <boolean表达式> : <错误信息表达式>
如果<boolean表达式>为true，则程序继续执行。
如果为false，则程序抛出java.lang.AssertionError，并输入<错误信息表达式>。
```


- Classpath设置的目的，在于告诉Java执行环境，在哪些目录下可以找到您所要执行的Java程序所需要的类或者包。

- 通过VScode 三种运行程序方法：1、通过gradle 插件中的build 和 run运行程序。 2、通过VSCODE运行 （ctrl + shift + D),编写launch.json。
3、通过F5也就是red hat的run方法编译执行程序。

- ctrl + c 在批处理中是终止当前运行的操作。                                     






# Git

```
1.2、常用术语
1)、仓库（Repository）
受版本控制的所有文件修订历史的共享数据库

2)、工作空间（Workspace)
本地硬盘或Unix 用户帐户上编辑的文件副本

3)、工作树/区（Working tree）
工作区中包含了仓库的工作文件。您可以修改的内容和提交更改作为新的提交到仓库。

4)、暂存区（Staging area）
暂存区是工作区用来提交更改（commit）前可以暂存工作区的变化。

5)、索引（Index）
索引是暂存区的另一种术语。

6)、签入（Checkin）
将新版本复制回仓库

7)、签出（Checkout）
从仓库中将文件的最新修订版本复制到工作空间

8)、提交（Commit）
对各自文件的工作副本做了更改，并将这些更改提交到仓库

9)、冲突（Conflict）
多人对同一文件的工作副本进行更改，并将这些更改提交到仓库

10)、合并（Merge）
将某分支上的更改联接到此主干或同为主干的另一个分支

11)、分支（Branch）
从主线上分离开的副本，默认分支叫master

12)、锁（Lock）
获得修改文件的专有权限。

13)、头（HEAD）
头是一个象征性的参考，最常用以指向当前选择的分支。

14)、修订（Revision）
表示代码的一个版本状态。Git通过用SHA1 hash算法表示的ID来标识不同的版本。

15)、标记（Tags）
标记指的是某个分支某个特定时间点的状态。通过标记，可以很方便的切换到标记时的状态。
```

# IO流

- 同步IO:读写IO时代码等待数据返回后才继续执行后续代码，代码编写简单，CPU执行效率地下。

- 异步IO:读写IO时仅发出请求，然后立刻执行后续代码，代码编写复杂，CPU执行效率高。

|抽象类接口 | 实现类 |
|--- | ---|
|InputStream | FileInputStream|
|OutputStream| FileOutputStream|
|Reader | FileReader|
|Writer| FileWriter|

- IO流是一种流式的数据输入/输出模型

- 二进制数据以byte为最小单位再InputStream/ OutputStream中单向流动

- 字符数据以char为最小单位在Reader/Writer中单向流动。

- JDK的java.io包提供了同步IO的功能。

- InputStream定义了所有输入流的超类

- FileInputStream实现了文件流输入。

- ByteArrayInputStream在内存中模拟一个字节流输入。

- 使用try(resource) 保证InputStream正确关闭。

```
File对象表示一个文件或者目录：
- 创建File对象本身不涉及IO操作。
- 获取路径：getPath() 。 绝对路径：getAbsolutePath() 规范路径：getCanonicalPath()
```

- 完整的读取一个InputStream所有字节：
public void readFile() throws IOExciption
{
  try (InputStream input = new FileInputStream("pathname")){
    int n;
    while ((n = input.read()) != -1){
      System.out.println(n);
    }
  } // 在此自动关闭InputStream 
}

- OutputStream定义了所有输出流的超类

- FileOutputStream实现了文件流输出

- ByteArrayOutputStream在内存中模拟一个字节流输出。

- 使用try(resource)保证了OutputStream正确关闭。

- read和write时都将阻塞，直至字节确实被读入或者写出。（线程阻塞）

## InputStream

### JDK提供的InputStream包括

- FileInputStram : 从文件读取数据，也是最终的数据源。 

- ServletInputStream : 从HTTP请求提供数据。

- Socket.getInputStream(): 从TCP连接读取数据。

- 直接提供数据的InputStream: FileInputStream, ByteArrayInputStream, ServletInputStream.

- 提供额外附加功能的InputStream: BufferedInputStream, DigestInputStream, CipherInputStream.

### Filter模式

- 组合而非继承的设计模式称为Filter模式（或者Decorator模式），通过少量的类实现了各种功能的组合。
```
InputStream input = new GZIPInputStream(  // 直接读取解压缩的内容
  new BufferedInputStream(  // 能够提供缓冲功能提高效率
    new FileInputStream("test.gz))); //数据来源自文件
```

- ZipInputStream可以读取Zip格式的流，ZipOutputStream可以把数据写入Zip.他们是FilterInputStream/FilterOutputStream.配合上面两个就可以读写Zip文件。

- 把资源存储在classpath中可以避免文件路径依赖，因为WIN和LINUX路径格式不同。

- Class对象的getResourceAsStream()可以从classpath读取资源。

- 需要检查返回的InputStream是否为null

### JAVA序列化

- 序列化是指把一个JAVA对象变成二进制内容（byte[]) 。序列化后可以把byte[]保存到文件中，也可以通过网络传输。

- 一个JAVA对象要能序列化，必须实现Serializable接口：这个接口没有定义任何方法，这种空接口被称为标记接口（Marker Interface).

- 反序列化是指把一个二进制内容（byte[]） 变成JAVA对象，反序列化后可以从文件和网络读取byte[] 并且变为JAVA对象。

- 反序列化由JVM直接构造出JAVA对象，不调用构造方法。

- java的序列化机制仅适用于JAVA,如果要与其他语言交换数据，必须使用通用的序列化方法，例如JSON.

```
完整的读取一个Reader所有字符
public void readFile() throws IOException{
  try (Reader reader = new FileReader("readme.txt")){
    int n ;
    while((n = reader.read()) != -1 ) {
      System.out.println((char)n);
    }
  } // 在此自动关闭Reader  称为try resource写法。
}

```

### Reader和InputStream

- Reader实际上是基于InputStream构造的，FileReader内部持有一个FileInputStream，Reader可以通过InputStream构造。

- Reader定义了所有字符输入流的超类，FileReader实现了文件字符流的输入。

- CharArrayReader在内存中模拟一个字符流输入。

```
InputStream input = new FileInputStream(filename);
Reader reader = new InputStreamReader(input, "UTF-8"){
  ...
}reader.close(); //不能调用input.close().
```

### Writer

```
向Writer写入字符：
public void writeFile() throws IOException{
  try (Writer writer = new FileWriter("readme.txt")) {
    writer.writer(.....);
  } // 在此自动关闭Writer （try, resource)
}
```

# 日期和时间

## java.util.Date

- 不足之处：不能转换时区，难以完成日期和时间的加减，难以计算两个日期差多少天，难计算某个月第一个星期一是几号。

- epoch time 是long的一个整型数。从1970年零点到现在经历的秒数。

```
LocalDate、LocalTime、LocalDateTime
都是不变类（类似String)
默认按照ISO 8601标准格式化和解析
使用DateTimeFormatter自定义格式化和解析
使用plusDays() / minusHours()等方法对日期和时间进行加减，返回新对象。
使用withDayOfMonth() / with() 等方法调整日期和时间，返回新对象。
使用isBefore() / isAfter() / equals()判断日期的时间的先后。
```

# 单元测试

- 好处：确保单个方法的运行正常，如果修改了方法代码，只需确保其对应的单元测试通过。测试代码本身可以作为示例代码，可以自动化运行所有测试并获得报告。

- JUnit特点：使用断言（Assertion）测试期望结果，可以方便的组织和运行测试，常用IDE都集成了Junit,也可以方便的集成到Maven.

- 一个TestCase包含一组相关的测试方法，每个测试方法必须完全独立，测试代码必须非常简单，不能为测试代码再编写测试，测试需要覆盖各种输入条件，特别是边界条件。

# Maven

- Maven是一个JAVA项目管理和构建工具，使用pom.xml定义项目内容，并且使用预设的目录结构。在Maven中声明一个依赖项可以自动下载并且导入classpath，Maven中使用groupId, artifactId, version可以唯一定位一个jar包。

- Maven维护了一个中央仓库（repo1.maven.org），第三方库将自身上传至中央仓库，Maven从中央仓库把所需依赖下载到本地，然后会自动缓存已下载过的jar包（~/.m2/repository/）

- 使用Maven构建项目就是执行Lifecycle（按顺序执行一系列的Phase），每执行一个Phase，都会执行该Phase绑定的若干Goal,goal是最小执行任务单元。常用的命令：mvn clean package(不会打包依赖的jar)


# Spring Boot

- 微服务是一种架构风格（微服务化），一个应用应该是一组小型服务；可以通过HTTP的方式进行互通；每一个功能最终都是一个可独立替换和独立升级的软件单元。