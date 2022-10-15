##Java学习笔记

[java]([Java常量：Java常量的定义和分类 (biancheng.net)](http://m.biancheng.net/view/763.html))

``` bash
Java学习笔记
```

Java JDK的使用：

> JDK 是一种用于构建在 Java 平台上发布的应用程序、Applet 和组件的开发环境，即编写 Java 程序必须使用 JDK，它提供了编译和运行 Java 程序的环境。
>
> > JDK 安装包被集成在 Java SE 中，因此下载 Java SE 即可
> >
> > 安装完成以后重要目录和文件的说明：
> >
> > > - `bin`：提供 JDK 工具程序，包括 javac、java、javadoc、appletviewer 等可执行程序。
> > > - `include`：存放用于本地访问的文件。
> > > - `jre`：存放 Java 运行环境文件。
> > > - `lib`：存放 Java 的类库文件，工具程序实际上使用的是 Java 类库。JDK 中的工具程序，大多也由 Java 编写而成。
> > > - `src.zip`：Java 提供的 API 类的源代码压缩文件。如果需要查看 API 的某些功能是如何实现的，可以査看这个文件中的源代码内容。
> >
> > JDK安装和配置完成后，测试：
> >
> > 在运行窗口使用 "java -version"输出 JDK 版本信息，说明 jdk 配置成功。
> >
> > <font color =red>这里需要配置"环境变量"。</font>
> >
> > > 新建系统变量，在“变量名”文本框中输入 JAVA_HOME，在“变量值”文本框中输入 JDK 的安装路径，最后单击“确定”按钮，保存 JAVA_HOME 变量。
> > >
> > > “系统变量”列表框中双击 Path 变量，进入“编辑系统变量”对话框。在“变量值”文本框的最前端添加`.;％JAVA__HOME%\bin;`内容
> > >
> > > 具体如下：————

---

java 环境变量

这里介绍的是Windows的环境变量配置方法：

> windows 电脑，“高级系统设置”，选择“高级”选项卡，“环境变量”中设置3项属性：
>
> > JAVA_HOME、PATH、CLASSPATH（如果版本在JDK的1.5以上就不用设置CLASSPATH）
> >
> > 变量设置的参数如下：
> >
> > - 变量名：**JAVA_HOME**
> > - 变量值：**C:\Program Files (x86)\Java\jdk1.8.0_91**     // 要根据自己的实际路径配置
> >
> > - 变量名：**CLASSPATH**
> > - 变量值：**.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;**     //记得前面有个"."
> >
> > - 变量名：**Path**
> > - 变量值：**%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;**
>
> 同样的配置结束后，使用" **java -version**"用来查看版本信息，查看是否成功运行

---

####Java基础介绍：

---



Java中的JVM、JRE、JDK的区别：

- JDK（Java Development Kid，Java 开发开源工具包），是针对 Java 开发人员的产品，是整个 Java 的核心，包括了 Java 运行环境 JRE、Java 工具和 Java 基础类库。
- JRE（Java Runtime Environment，Java 运行环境）是运行 JAVA 程序所必须的环境的集合，包含 JVM 标准实现及 Java 核心类库。
- JVM（Java Virtual Machine，Java 虚拟机）是整个 Java 实现跨平台的最核心的部分，能够运行以 Java 语言写作的软件程序。

---

源代码的组成：

> - 关键字 public 表示访问说明符，表明该类是一个公共类，可以控制其他对象对类成员的访问。
> - 关键字 class 用于声明一个类，其后所跟的字符串是类的名称。
> - 关键字 static 表示该方法是一个静态方法，允许调用 main() 方法，无须创建类的实例。
> - 关键字 void 表示 main() 方法没有返回值。
> - main() 方法是所有程序的入口，最先开始执行。
> - “/*”“*/”之间的内容和以“//”开始的内容为 Java 程序的注释。

---

Java程序运行过程：

1. 编写：是指在 Java 开发环境中进行程序代码的输入，最终形成后缀名为 .java 的 Java 源文件。
2. 编译：是指使用 Java 编译器对源文件进行错误排査的过程，编译后将生成后缀名为 .class 的字节码文件，不像C语言那样生成可执行文件。
3. 运行：是指使用 Java 解释器将字节码文件翻译成机器代码，执行并显示结果。

---

Java基础语法原理：一个 Java 程序可以认为是一系列对象的集合，而这些对象通过调用彼此的方法来协同工作。

> - **对象**：对象是类的一个实例，有状态和行为。例如，一条狗是一个对象，它的状态有：颜色、名字、品种；行为有：摇尾巴、叫、吃等。
> - **类**：类是一个模板，它描述一类对象的行为和状态。
> - **方法**：方法就是行为，一个类可以有很多方法。逻辑运算、数据修改以及所有动作都是在方法中完成的。
> - **实例变量**：每个对象都有独特的实例变量，对象的状态由这些实例变量的值决定。

---



####<输出hello,world!>

---

Hello world

在<font color = blue>vim</font>下编译：

> 使用vim hello.java
>
> ```java
> public class hello{
> public static void main(String[] args){
>   System.out.print("Hello,world!");
> }
> }
> ```
>
> 使用 :w 保存
>
> 退出到vim
>
> 使用 javac hello.java（这是编译）这里会生成一个class文件。
>
> 使用 Java hello （这里会直接输出程序）"hello,world!"
>
> **这里可能遇到的问题：**
>
> 1、单词的问题（字母的大小写，可能会对程序产生根本影响）
>
> 2、”文件“名和”类“名，这里必须一致，否则程序会出错无法使用。
>
> <保存的文件名字和程序的声明应该一致>
>
> 3、符号中可能会有中文符号。非输出部分如果有中文符号（比如 ”;“和”;"这两个分号就有中英文的区别）就会出错。程序无法访问。
>
> 4、如果遇到编码问题，（中文编码报错）我们可以使用**-encoding** 选项设置 **utf-8** 来编译：
>
> ```bash
> javac -encoding UTF-8 HelloWorld.java 
> java HelloWorld 
> ```
>
> 
>
> > <font color = blue>在Windows中编译</font>
> >
> > 1. 选择“开始”|“运行”命令，打开“运行”对话框后输入 cmd 命令，按 Enter 键进入到 DOS 环境。
> > 2. 输入 d: 按 Enter 键，切换到 Java 源程序所在的 D 盘。
> > 3. 输入 cd myJava 命令，进入 Java 源程序所在的目录，即 d:\myJava。
> > 4. 输入" javac HelloJava.java" 命令进行编译，此时如果没有任何其他信息，表示该源程序通过了编译；反之便说明程序中存在错误，必须在记事本中打开 HelloJava.java 文件进行修改，再次保存此文件后回到命令提示符窗口重新编译（可能要反复几次），直到编译通过为止。
> > 5. 输入 "java HelloJava" 命令执行程序，如果出现“Hello Java”字符，说明程序执行成功。
> >
> > > 常见的错误：在使用 javac 编译器编译源代码文件时，可能会出现下面几个常见问题。
> > >
> > > (1) Error:cannot read:HelloJava.java javac。
> > > 工具程序找不到指定的 java 文件，需要检查文件是否存储在当前目录中，或文件名是否错误。
> > >
> > > (2) HelloJava.java:4:class HelloJava is public,should be declared in a file named MyApplication.java。
> > > 源文件中类的名称和源文件名称不符，需要确定源文件名称和类名称是否相同。
> > >
> > > (3) HelloJava.java:6:cannot find symbol。
> > > 源程序文件中某些代码部分输入错了，最常产生的原因可能是没有注意到字母的大小写。
> > >
> > > (4) Javac 不是内部或外部命令、可执行程序或批量文件。
> > > path 设置有误或没有在 path 系统变量中加入 JDK 的 bin 目录。
> > >
> > > 如果没有出现上述所列问题，即成功编译了该 Java 文件。在解释执行 .class 文件时，可能会出现下面几个常见问题。
> > >
> > > (1) Exception in thread “main” java.lang.NoClassDe£FoundError。
> > > Java 工具程序找不到所指定的 .class 类，需要确定指定的类是否存储在当前目录中，名称是否正确。
> > >
> > > (2) Exception in thread “main” java.lang.NoSuchMetliodError:main。
> > > 没有指定 Java 程序的入口。Java 工具程序指定的类必须有一个程序入口，也就是必须包括 main(String args[]) 这个方法。

---

#### Java基础语法解释：

```java
public class HelloWorld {
    /* 第一个程序"hello，world"
     * 它将输出字符串 Hello World
     */
    public static void main(String[] args) {
        System.out.println("Hello World"); // 输出 Hello World
    }
}
```

> public : 访问修饰符
>
> static ： 关键字
>
> void : 返回类型
>
> main : 方法名
>
> String : 类 --（这里注意  " S "是大写的）
>
> args : 字符串数组

---



####JAVA规则：

**首先要求程序中的各个要素都遵守命名规则，然后在编码中严格按照编码格式编写代码。命名规则包括以下几点。**

- 包的名称由一个小写字母序列组成。
- 类的名称由大写字母开头，其他字母都由小写的单词组成。
- 类的实例的名称由一个小写字母开头，后面的单词由大写字母开头。
- 常量的名称都大写，并且指出完整含义。
- 参数的名称无其他具体规定。
- 数组的命名使用“类型[] 数组名”的形式。


另外，编码格式规定如下。

- 程序最开始编写导入包和类语句，即 import 语句。import 语句可以有多行，编写完 import 语句后空一行。
- 定义 public 类，顶格书写。类的主体左括号“{”不换行书写，右括号“}”顶格书写。
- 定义 public 类中的变量，缩进书写。
- 定义方法用缩进书写，方法的左括号“{”不换行书写，右括号“}”和方法首行第一个字符对齐。方法体要再次缩进书写，最后一个变量定义和第一个方法定义之间、方法和方法之间最好空一行。

提示：在单一的语句后有“;”，在一对括号“{}“之外无“;”。方法调用名和紧跟在其后的左括号“(”无空格，该左括号和其后的标识符之间无空格。多个参数之间的逗号和前一个参数紧靠，与后一个参数空一格。

> ###编写 Java 程序时，应注意以下几点：
>
> - **大小写敏感**：Java 是大小写敏感的，这就意味着标识符 Hello 与 hello 是不同的。
> - **类名**：对于所有的类来说，类名的首字母应该大写。如果类名由若干单词组成，那么每个单词的首字母应该大写，例如 **MyFirstJavaClass** 。
> - **方法名**：所有的方法名都应该以小写字母开头。如果方法名含有若干单词，则后面的每个单词首字母大写。
> - **源文件名**：源文件名必须和类名相同。当保存文件的时候，你应该使用类名作为文件名保存（切记 Java 是大小写敏感的），文件名的后缀为 **.java**。（如果文件名和类名不相同则会导致编译错误）。
> - **主方法入口**：所有的 Java 程序由 **public static void main(String[] args)** 方法开始执行。

---

#### //注释

> 1、单行注释	//
>
> 2、多行注释	/*	*/
>
> 3、 文档注释  /**	*/
>
> 单行注释和多行注释，注释了的内容不参与编译，换句话说，编译之后生成的.class结尾的字节码文件中不包含注释掉的信息。多行注释不可以嵌套使用。
>
> 文档注释：注释内容可以被JDK提供的工具javadoc所解析，生成一套以网页文件形式体现的该程序的说明文档。
>
> > ```txt
> > 在 Java 中，一行注释以双斜杠“//”标识；多行注释包含在“/*”和“*/”之间；文档注释包含在“/**”和“*/”之间。当编译器执行到“//”时，就会忽略该行“//”之后的所有文本；当执行到“/*”时，会扫描下一个“*/”并忽略“/*”和“*/”之间的任何文本；当执行到“/**”时，也会扫描下一个“*/”并忽略“/**”和“*/”之间的任何文本内容。
> > ```
> >
> > Javadoce标签：可以通过 Javadoc 生成 API 帮助文档，Java 帮助文档主要用来说明类、成员变量和方法的功能。
> >
> > 可以从程序源代码中抽取类、方法、成员等注释，然后形成一个和源代码配套的 API 帮助文档。
> >
> > API 帮助文档相当于产品说明书，而说明书只需要介绍那些供用户使用的部分，所以 Javadoc 默认只提取 public、protected 修饰的部分。如果要提取 private 修饰的部分，需要使用 -private。
> >
> > > Javadoc 工具可以识别文档注释中的一些特殊标签，这些标签一般以`@`开头，后跟一个指定的名字，有的也以`{@`开头，以`}`结束。Javadoc 可以识别的标签如下表所示：
> > >
> > > 
> > >
> > > | 标签          | 描述                                                   | 示例                                                         |
> > > | ------------- | ------------------------------------------------------ | ------------------------------------------------------------ |
> > > | @author       | 标识一个类的作者，一般用于类注释                       | @author description                                          |
> > > | @deprecated   | 指名一个过期的类或成员，表明该类或方法不建议使用       | @deprecated description                                      |
> > > | {@docRoot}    | 指明当前文档根目录的路径                               | Directory Path                                               |
> > > | @exception    | 可能抛出异常的说明，一般用于方法注释                   | @exception exception-name explanation                        |
> > > | {@inheritDoc} | 从直接父类继承的注释                                   | Inherits a comment from the immediate surperclass.           |
> > > | {@link}       | 插入一个到另一个主题的链接                             | {@link name text}                                            |
> > > | {@linkplain}  | 插入一个到另一个主题的链接，但是该链接显示纯文本字体   | Inserts an in-line link to another topic.                    |
> > > | @param        | 说明一个方法的参数，一般用于方法注释                   | @param parameter-name explanation                            |
> > > | @return       | 说明返回值类型，一般用于方法注释，不能出现再构造方法中 | @return explanation                                          |
> > > | @see          | 指定一个到另一个主题的链接                             | @see anchor                                                  |
> > > | @serial       | 说明一个序列化属性                                     | @serial description                                          |
> > > | @serialData   | 说明通过 writeObject() 和 writeExternal() 方法写的数据 | @serialData description                                      |
> > > | @serialField  | 说明一个 ObjectStreamField 组件                        | @serialField name type description                           |
> > > | @since        | 说明从哪个版本起开始有了这个函数                       | @since release                                               |
> > > | @throws       | 和 @exception 标签一样.                                | The @throws tag has the same meaning as the @exception tag.  |
> > > | {@value}      | 显示常量的值，该常量必须是 static 属性。               | Displays the value of a constant, which must be a static field. |
> > > | @version      | 指定类的版本，一般用于类注释                           | @version info                                                |
> > >
> > > 对两种标签格式的说明：
> > >
> > > - @tag 格式的标签（不被`{ }`包围的标签）为块标签，只能在主要描述（类注释中对该类的详细说明为主要描述）后面的标签部分（如果块标签放在主要描述的前面，则生成 API 帮助文档时会检测不到主要描述）。
> > > - {@tag} 格式的标签（由`{ }`包围的标签）为内联标签，可以放在主要描述中的任何位置或块标签的注释中。
> > >
> > > 
> > > Javadoc 标签注意事项：
> > >
> > > - Javadoc 标签必须从一行的开头开始，否则将被视为普通文本。
> > > - 一般具有相同名称的标签放在一起。
> > > - Javadoc 标签区分大小写，代码中对于大小写错误的标签不会发生编译错误，但是在生成 API 帮助文档时会检测不到该注释内容。
> > >
> > > Javadoc 用法格式如下：
> > >
> > > javadoc [options] [packagenames] [sourcefiles]
> > >
> > > 对格式的说明：
> > >
> > > - options 表示 Javadoc 命令的选项；
> > > - packagenames 表示包名；
> > > - sourcefiles 表示源文件名。
> > >
> > > 
> > > 在 cmd（命令提示符）中输入`javadoc -help`就可以看到 Javadoc 的用法和选项（前提是安装配置了JDK），下面列举 Javadoc 命令的常用选项：
> > >
> > > 
> > >
> > > | 名称                | 说明                                     |
> > > | ------------------- | ---------------------------------------- |
> > > | -public             | 仅显示 public 类和成员                   |
> > > | -protected          | 显示 protected/public 类和成员（默认值） |
> > > | -package            | 显示 package/protected/public 类和成员   |
> > > | -private            | 显示所有类和成员                         |
> > > | -d <directory>      | 输出文件的目标目录                       |
> > > | -version            | 包含 @version 段                         |
> > > | -author             | 包含 @author 段                          |
> > > | -splitindex         | 将索引分为每个字母对应一个文件           |
> > > | -windowtitle <text> | 文档的浏览器窗口标题                     |
> > >
> > > ## DOS命令生成API帮助文档 
> > >
> > > 新建一个空白记事本，输入下列代码： 
> > >
> > > ```java 
> > > public class Test{
> > >     /**
> > >      * 求输入两个参数范围以内整数的和
> > >      * @param n 接收的第一个参数，范围起点
> > >      * @param m 接收的第二个参数，范围终点
> > >      * @return 两个参数范围以内整数的和
> > >      */
> > >     public int add(int n, int m) {
> > >         int sum = 0;
> > >         for (int i = n; i <= m; i++) {
> > >             sum = sum + i;
> > >         }
> > >         return sum;
> > >     }
> > > } 
> > > ```
> > >
> > > 将文件命名为 Test.java，打开 cmd 窗口，输入`javadoc -author -version Test.java`命令。
> > >
> > > 打开 Test.java 文件存储的位置，会发现多出了一个 Test.html 文档。打开文档，文档页面会生成相关信息。
> > >
> > > 如果没有考虑编码格式的问题，注释中有汉字可能会乱码。使用`javadoc -encoding UTF-8 -charset UTF-8 Test.java`会解决编码问题。
> >
> > 
>
> 

---



#### IDEA

> 基础操作：
>
> psvm 直接自动输入
>
> ```java
> public static void main(String[] args){
>     
>  }
> ```
>
> sout直接自动输入
>
> ```java 
> 
>      System.out.print("Hello,world!");
> 
> ```
>
> 这两个操作配合使用，会更加方便
>
> ```java
> public static void main(String[] args){
>      System.out.print(" ");
>  }
> ```
>

---



####基本语法：

> ### 标识符
>
> Java中标识符是为方法、变量或其它用户定义项所定义的名称。标识符可以有一个或多个字符。
>
> 简单点解释就是：Java所有的组成部分都需要名字。类名、变量名、方法名都被称为标识符
>
> **标识符的构成规则**：标识符由数字、字母、特殊符号、下划线等这些符号组成。（各个符号之间不能由空格）
>
> <font color =red>标识符的组成不能以数字开头，也不能使用任何Java关键字作为标识符，也不能赋予标识符任何标准的方法名。</font>
>
> 标识符分为两类，分别为关键字和用户自定义标识符。
>
> 1、关键字是特殊含义的标识符，如true、false表示逻辑的真假
>
> 2、用户自定义标识符是由用户按标识符构成规则生成的非保留字的标识符，比如 ‘abc’ 就是一个用户自定义的标识符。
>
> 规则如下：
>
> > - 所有的标识符都应该以字母（A-Z 或者 a-z）,美元符（$）、或者下划线（_）开始
> > - 首字符之后可以是字母（A-Z 或者 a-z）,美元符（$）、下划线（_）或数字的任何字符组合
> > - 关键字不能用作标识符
> > - 标识符是大小写敏感的
> > - 合法标识符举例：age、$salary、_value、__1_value
> > - 非法标识符举例：123abc、-salary
>
> <font color =red>标识符绝对不能与关键字重名</font>
>
> > 个人：一个良好的标识符，应赋予它一个有意义或有用途的名字。这会更加方便代码的编写和查阅。
> >
> > 标识符的用途：用来命名常量、变量、类和类的对象等。
>
> ---
>
> 
>
> ###关键字
>
> 关键字：这是对编译器有着特殊意义的固定单词，不能在程序中做其它目的使用。具有专门的意义和用途，和自定义的标识符不同，不能当作一般的标识符来使用。例如class就是一个关键字，它用来声明一个类。public，它用来表示公共类。static和void也是关键字
>
> <font color = red>Java区分大小写，为了程序的逻辑和可读性，要尽量避免使用关键字的其它形式来命名。</font>
>
> 下面列出了 Java 关键字。这些保留字不能用于常量、变量、和任何标识符的名称。
>
> | 类别                 | 关键字                         | 说明                 |
> | :------------------- | :----------------------------- | :------------------- |
> | 访问控制             | private                        | 私有的               |
> | protected            | 受保护的                       |                      |
> | public               | 公共的                         |                      |
> | default              | 默认                           |                      |
> | 类、方法和变量修饰符 | abstract                       | 声明抽象             |
> | class                | 类                             |                      |
> | extends              | 扩充,继承                      |                      |
> | final                | 最终值,不可改变的              |                      |
> | implements           | 实现（接口）                   |                      |
> | interface            | 接口                           |                      |
> | native               | 本地，原生方法（非 Java 实现） |                      |
> | new                  | 新,创建                        |                      |
> | static               | 静态                           |                      |
> | strictfp             | 严格,精准                      |                      |
> | synchronized         | 线程,同步                      |                      |
> | transient            | 短暂                           |                      |
> | volatile             | 易失                           |                      |
> | 程序控制语句         | break                          | 跳出循环             |
> | case                 | 定义一个值以供 switch 选择     |                      |
> | continue             | 继续                           |                      |
> | do                   | 运行                           |                      |
> | else                 | 否则                           |                      |
> | for                  | 循环                           |                      |
> | if                   | 如果                           |                      |
> | instanceof           | 实例                           |                      |
> | return               | 返回                           |                      |
> | switch               | 根据值选择执行                 |                      |
> | while                | 循环                           |                      |
> | 错误处理             | assert                         | 断言表达式是否为真   |
> | catch                | 捕捉异常                       |                      |
> | finally              | 有没有异常都执行               |                      |
> | throw                | 抛出一个异常对象               |                      |
> | throws               | 声明一个异常可能被抛出         |                      |
> | try                  | 捕获异常                       |                      |
> | 包相关               | import                         | 引入                 |
> | package              | 包                             |                      |
> | 基本类型             | boolean                        | 布尔型               |
> | byte                 | 字节型                         |                      |
> | char                 | 字符型                         |                      |
> | double               | 双精度浮点                     |                      |
> | float                | 单精度浮点                     |                      |
> | int                  | 整型                           |                      |
> | long                 | 长整型                         |                      |
> | short                | 短整型                         |                      |
> | 变量引用             | super                          | 父类,超类            |
> | this                 | 本类                           |                      |
> | void                 | 无返回值                       |                      |
> | 保留关键字           | goto                           | 是关键字，但不能使用 |
> | const                | 是关键字，但不能使用           |                      |
>
> **注意：**Java 的 null 不是关键字，类似于 true 和 false，它是一个字面常量，不允许作为标识符使用。
>
> ---
>
> 
>
> ### Java修饰符
>
> Java可以使用修饰符来修饰类中方法和属性。主要有两类修饰符：
>
> - 访问控制修饰符 : default, public , protected, private
>
> - 非访问控制修饰符 : final, abstract, static, synchronized
>
> - > - 访问修饰符
>   > - 非访问修饰符
>   >
>   > 修饰符用来定义类、方法或者变量，通常放在语句的最前端
>   >
>   > > 在Java中访问修饰符可以用来保护对类、变量、方法和构造方法的访问。
>   > >
>   > > 非访问修饰符用来实现一些其它功能比如：
>   > >
>   > > > static 修饰符，用来修饰类方法和类变量。
>   > > >
>   > > > final 修饰符，用来修饰类、方法和变量，final 修饰的类不能够被继承，修饰的方法不能被继承类重新定义，修饰的变量为常量，是不可修改的。
>   > > >
>   > > > abstract 修饰符，用来创建抽象类和抽象方法。
>   > > >
>   > > > synchronized 和 volatile 修饰符，主要用于线程的编程。
>   > >
>   > > ####Java修饰符的说明与例子：
>   > >
>   > > [java修饰符]([Java 修饰符 | 菜鸟教程 (runoob.com)](https://www.runoob.com/java/java-modifier-types.html))
>
> ---
>
> ### Java变量
>
> Java 中主要有这几种类型的变量
>
> - 局部变量
> - 类变量（静态变量）
> - 成员变量（非静态变量）
>
> ---
>
> ###Java数组
>
> 数组是储存在堆上的对象，可以保存多个同类型变量。
>
> ---
>
> ### Java枚举
>
> Java 5.0引入了枚举，枚举限制变量只能是预先设定好的值。使用枚举可以减少代码中的 bug。
>
> 例如，我们为果汁店设计一个程序，它将限制果汁为小杯、中杯、大杯。这就意味着它不允许顾客点除了这三种尺寸外的果汁。
>
> ```java
> class FreshJuice {
>    enum FreshJuiceSize{ SMALL, MEDIUM , LARGE }
>    FreshJuiceSize size;
> }
>  
> public class FreshJuiceTest {
>    public static void main(String[] args){
>       FreshJuice juice = new FreshJuice();
>       juice.size = FreshJuice.FreshJuiceSize.MEDIUM  ;
>    }
> }
> ```
>
> 

