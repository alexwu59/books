
本书主旨就是帮助你更有效的使用java语言和他自己的基础库，这些基础库包括java.lang, java.util,和java.io,以及这些库的字库比如  java.util.concurrent and java.util.function。其他的一些库我们也会有所提及。
本书由90个条款组成，每个条款都阐述了一种规则。这些规则都应该在实践中得到，最优秀最有经验的程序员都认为这些规则是非常有用的。这些规则松散的被分成了11章，每章都涵盖软件设计的一个宽的范围。本书不推荐从头按顺阅读，因为每项或多或少都可以独立存在的。这些规则被高度穿插引用因此你可以很方便来规划自己正本书的阅读的进程。
自从本书发行的上一个版本之后，java平台增加了许多新的特性。本书的大部分规则将一些方式去运用这些特性。下面的表展示了这些关键特性的主要内容都分布在哪些规则中，以及支持这些特性的java平台。
大部分规则通过程序示例进行阐明。本书的一个关键特性就是代码示例包含有许多设计模式和惯用条款。在合适的地方，他们进行交叉引用，可以在标准的Gamma95中找到标准的引用。
   Many items contain one or more program examples illustrating some practice to be avoided. Such examples, sometimes known as antipatterns, are clearly labeled with a comment such as // Never do this!. In each case, the item explains why the example is bad and suggests an alternative approach.
   许多规则包含了一个或者多个程序代码，这些程序代码是应该避免出现的。例如有些例子，有时候作为反模式被熟知，这些例子的被清楚的以一个注释锁标明：永远不用这么做。每个例子，这些规则项解释为什么这个例子是错误的，并且给出一个代替的方式。
   This book is not for beginners: it assumes that you are already comfortable
with Java. If you are not, consider one of the many fine introductory texts, such as Peter Sestoft’s Java Precisely [Sestoft16]. While Effective Java is designed to be accessible to anyone with a working knowledge of the language, it should provide
food for thought even for advanced programmers.
   这本书不适合初学者：它会假设读者已经非常熟悉java。如果你不符合要求，参考许多优秀的引导性内容，比如peter的java精粹。而effectjava是提供给任何一个以java语言为工作内容的读者，他可以提供思考上的帮助，甚至是对于一些高级程序员。
   Most of the rules in this book derive from a few fundamental principles.Clarity and simplicity are of paramount importance. The user of a component should never be surprised by its behavior. Components should be as small as possible but no smaller. (As used in this book, the term component refers to any reusable software element, from an individual method to a complex framework consisting of multiple packages.) Code should be reused rather than copied. The dependencies between components should be kept to a minimum. Errors should be detected as soon as possible after they are made, ideally at compile time.
   本书的大部分规则都是衍生与一少部分基础原则.清晰简单是至关重要的。组件的使用者不应该被他行为感到惊奇，组件应该尽可能小但是不能太小。本书中使用的术语"组件"是指任可以重用的软件对象，从一个独立的方法到一个包括多个包的复杂的框架。代码应该被重用而不是复制。组件之间的依赖应该保持最小。错误在他们产生之后应该尽可能快的被检测出来,理想状态是在编译器就能被发现。

   While the rules in this book do not apply 100 percent of the time, they do
characterize best programming practices in the great majority of cases. You
should not slavishly follow these rules, but violate them only occasionally and
with good reason. Learning the art of programming, like most other disciplines,
consists of first learning the rules and then learning when to break them.
   本书中这些规则不适合所以的情况，然后，他们在大部分示例中表现为最好的编程实践。你不应该完成顺从这些规则，但是如果违背这些规则应该是很偶然并且需要合适的理由。学习编程的艺术（适用于大部分原则），包括第一次学习使用规则，然后学习打破规则。
   For the most part, this book is not about performance. It is about writing
programs that are clear, correct, usable, robust, flexible, and maintainable. If you can do that, it’s usually a relatively simple matter to get the performance you need(Item 67). Some items do discuss performance concerns, and a few of these items provide performance numbers. These numbers, which are introduced with the
phrase “On my machine,” should be regarded as approximate at best.
   本书大部分章节，不是关于性能的。本书是提供编写清晰，正确，可用，健壮，可扩展和可维护代码的指南。如果你能做到这些，那么提升你需要的性能通常就是一件很简单的事情了。有些条款讨论了性能的问题，但是很少的条款提供了性能指标。这些指标是使用在“On my machine”机器上，被考虑是接近最好的选择。
   For what it’s worth, my machine is an aging homebuilt 3.5GHz quad-core
Intel Core i7-4770K with 16 gigabytes of DDR3-1866 CL9 RAM, running Azul’s
Zulu 9.0.0.15 release of OpenJDK, atop Microsoft Windows 7 Professional SP1
(64-bit).
   下面是值得参考，我个人机器是一个自组装的老机器:3.5GH 四核 16G内存，openjdk，win7
When discussing features of the Java programming language and its libraries,
it is sometimes necessary to refer to specific releases. For convenience, this book
uses nicknames in preference to official release names. This table shows the mapping between release names and nicknames:
   在讨论java程序设计语言的特性和他函数库的时候，是非常有必要明确一下发型版本。为了方便，本书使用别名而不是官方的版本名称。下面的表展示了发行版本及其对应的别名。
   The examples are reasonably complete, but favor readability over completeness.
They freely use classes from packages java.util and java.io. In order to
compile examples, you may have to add one or more import declarations, or other
such boilerplate. The book’s website, http://joshbloch.com/effectivejava,
contains an expanded version of each example, which you can compile and run.
   书中的例子是适度完整，可读性超过了完整性，他们自由使用来自util和io包中的类。为了去编译这些例子，需要自己添加一个或者多个import声明，或者其他引用。本书的官网包括了每个例子的扩展版本，这些版本的例子，可以直接编译和执行。
    For the most part, this book uses technical terms as they are defined in The
Java Language Specification, Java SE 8 Edition [JLS]. A few terms deserve
special mention. The language supports four kinds of types: interfaces (including
annotations), classes (including enums), arrays, and primitives. The first three are known as reference types. Class instances and arrays are objects; primitive values are not. A class’s members consist of its fields, methods, member classes, and member interfaces. A method’s signature consists of its name and the types of its formal parameters; the signature does not include the method’s return type.
   大部情况下，本书使用的技术术语来自语音java8的语言规范上的术语。很少的术语会有特殊的说明。java语音支持四种类型：接口(包括注解),类（包括枚举），数组和原生态类型。前三种是引用类型。类的示例和数组都是对象，原生态数据类型不是。一个类的成员包括：属性字段，方法，成员类，成员接口。一个方法签名签名包括它的名称，形式参数，方法签名不包括方法返回类型。
This book uses a few terms differently from The Java Language Specification.
Unlike The Java Language Specification, this book uses inheritance as a synonym
for subclassing. Instead of using the term inheritance for interfaces, this book simply states that a class implements an interface or that one interface extends
another. To describe the access level that applies when none is specified, this book uses the traditional package-private instead of the technically correct package access [JLS, 6.6.1].

  本书使用了一些术语与java规范不太一样。与java规范相比不同的是，本书使用继承作为子类化的同义词。为了替代术语“接口继承”，本书简单的把类实现接口和接口继承接口通称为继承。为描述没有指定访问级别，本书使用了传统的包私有替代专业上正确的包访问。

This book uses a few technical terms that are not defined in The Java Language
Specification. The term exported API, or simply API, refers to the classes,
interfaces, constructors, members, and serialized forms by which a programmer
accesses a class, interface, or package. (The term API, which is short for application programming interface, is used in preference to the otherwise preferable term interface to avoid confusion with the language construct of that name.) A programmer who writes a program that uses an API is referred to as a user of the API. A class whose implementation uses an API is a client of the API.
本书还使用了一些java规范中没有定义的专业术语。对API(或者是指普通的API)术语进行扩展，扩展的术语API指接口，构造函数，成员变量，和程序员可以访问类，接口或者包的可序列化的形式。（API是应用程序接口的缩写，他比其他可取的术语---“接口”更优先使用，因为可以避免与java语言本身结构中的接口术语相混淆）

Classes, interfaces, constructors, members, and serialized forms are collectively known as API elements. An exported API consists of the API elements that are accessible outside of the package that defines the API. These are the API elements that any client can use and the author of the API commits to support. Not coincidentally, they are also the elements for which the Javadoc utility generates documentation in its default mode of operation. Loosely speaking, the exported API of a package consists of the public and protected members and constructors of every public class or interface in the package.
类，接口，构造函数按的序列化形式都的被以API元素的形式所知晓。一个扩展的API包括的API元素，可以访问包以为定义的API。这里的API可以被人任何客户端使用并且API提供者会对它提供支持。无独有偶，这些API就是JAVADOC工具以默认形式产生的文档。笼统说，扩展AIP是包括了包中每个类的公共构造函数，公共和保护成员以及接口。
In Java 9, a module system was added to the platform. If a library makes use of the module system, its exported API is the union of the exported APIs of all the packages exported by the library’s module declaration.
在java9中，一个模块化的系统被加到平台中，如果一个库函数使用模块化系统，他的扩展API是一个并集，这个集合中包括所有的扩展包的所以扩展API，这些扩展包都是通过库的模块化声明进行扩展。
Creating and Destroying Objects
对象的创建和销毁
This chapter concerns creating and destroying objects: when and how to create
them, when and how to avoid creating them, how to ensure they are destroyed in a
timely manner, and how to manage any cleanup actions that must precede their
destruction.
本章关注的是对象的创建和销毁:何时怎样创建对象，什么时间以及怎样避免创建对象，如何确保他们及时进行销毁，最后怎样管理对象的清理工作，这些清理工作必须在他们销毁执行进行。
Item 1: Consider static factory methods instead of constructors
第1款:考虑用静态工厂方法替代构造函数
The traditional way for a class to allow a client to obtain an instance is to provide a public constructor. There is another technique that should be a part of every programmer’s toolkit. A class can provide a public static factory method, which is simply a static method that returns an instance of the class. Here’s a simple example from Boolean (the boxed primitive class for boolean). This method translates a boolean primitive value into a Boolean object reference:
public static Boolean valueOf(boolean b) {
return b ? Boolean.TRUE : Boolean.FALSE;
}
Note that a static factory method is not the same as the Factory Method pattern from Design Patterns [Gamma95]. The static factory method described in this item has no direct equivalent in Design Patterns.
传统的获取类实例的方法是运行客户端访问类提供的公共构造函数。还有另外一种技术，应该作为每个程序员的工具包里的一部分：一个类应该提供一个静态工厂方法，这个方法是普通的静态方法，它返回一个类的实例对象。这里有一个来自Boolean（原始数据类型boolean的包装类）的简单示例。该方法把boolean的原始值转变为Boolean类的引用类型：
   public static Boolean valueOf(boolean b) {
return b ? Boolean.TRUE : Boolean.FALSE;
}
注意，这静态工厂方法与设计模式中的静态工厂方法不一样。这本条款中的静态工厂方法与设计模式不是直接等效。
A class can provide its clients with static factory methods instead of, or in addition to, public constructors. Providing a static factory method instead of a public constructor has both advantages and disadvantages.
一个类为客户端除了公共构造方法之前，还应该提供静态工厂方法。利用静态构造方法来代替公共构造函数优缺点并存。
One advantage of static factory methods is that, unlike constructors, they have names. If the parameters to a constructor do not, in and of themselves, describe the object being returned, a static factory with a well-chosen name is easier to use and the resulting client code easier to read. For example, the constructor BigInteger(int, int, Random), which returns a BigInteger that is probably prime, would have been better expressed as a static factory method
named BigInteger.probablePrime. (This method was added in Java 4.)
第一个优点，与构造方法不同，静态工厂方法有自己名字。如果通过构造函数的参数本身不能够描述该构造方法将要返回的对象，此时，静态工厂方法可使用一个描述准确的名字的是非常容易，并且客户端代码易读性也强。例如，构造函数BigInteger(int, int, Random)可能返回BigInteger对象是一个素数，但如果使用静态工厂方法BigInteger.probablePrime，那么描述的就更清晰。
A class can have only a single constructor with a given signature. Programmers have been known to get around this restriction by providing two constructors whose parameter lists differ only in the order of their parameter types. This is a really bad idea. The user of such an API will never be able to remember which constructor is which and will end up calling the wrong one by mistake. People reading code that uses these constructors will not know what the code does without referring to the class documentation.
一个类的一个函数签名只能定义一个构造函数。大家都知道程序员



