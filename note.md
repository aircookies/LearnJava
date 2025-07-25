# Java学习笔记

# 使用IDEA开发第一个java程序的步骤

1. 创建该工程 new Project(空工程)
2. 创建模块 new Module
3. 创建包 new Package
4. 创建类
5. 编写代码,并启动

# IDEA常用快捷键

- 组合几个键快速完成某件事,可以提高开发效率

| 快捷键                            | 作用                      |
| --------------------------------- | ------------------------- |
| main/psvm,sout,...                | 快速键入相关代码          |
| Ctrl + D                          | 复制当前行数据到下一行    |
| Ctrl + Y                          | 删除所在行,建议用Ctrl + X |
| Ctrl + X                          | 剪切当前行                |
| Ctrl + Alt + L                    | 格式化当前代码            |
| Alt + Shift + ↑ , Alt + Shift + ↓ | 上下移动当前代码          |
| Ctrl + / , Ctrl + Shift + /       | 对代码进行注释            |

# java基础语法

## 注释

![alt text](./images/image.png)

### 注释的特点

- 注释不影响程序的执行

## 字面量

字面量就是程序中能直接书写的数据

### 字面量的分类

| 常用数据       | 生活中的写法 | 程序中的写法              | 说明                                    |
| -------------- | ------------ | ------------------------- | --------------------------------------- |
| 整数           | 666, -88     | 666, -88                  | 写法一致                                |
| 小数           | 13.14, -5.21 | 13.14, -5.21              | 写法一致                                |
| 字符           | A, 0, 我     | 'A', '0', '我'            | 程序中必须使用单引号,有且仅能有一个字符 |
| 字符串         | 你好世界     | "hello world", "你好世界" | 程序中必须使用双引号,内容可有可无       |
| 布尔值         | 真, 假       | true, false               | 只有两个值:true代表真, false代表假      |
| 空值           | -            | NULL                      | 一个特殊的值,空值                       |
| 特殊字符字面量 | -            | \t \n                     | 转义字符                                |

## 变量

变量就是内存中的一块区域,可以理解成一个盒子

- 定义格式: 数据类型 变量名称 = 数据;
- 使用变量记住要处理的数据,编写的代码更灵活,管理代码方便

## 数据类型

### 基本数据类型的分类

基本数据类型:**4大类8种**

| 数据类型     | 内存占用(字节数) | 数据范围 |
| ------------ | ---------------- | -------- |
| 整形         | byte             | 1        | -128~127                                         |
|              | short            | 2        | -32768~32767                                     |
|              | int(默认)        | 4        | -2147483648~2147483647(10位数,大约21亿)          |
|              | long             | 8        | -9223372036854775808~9223372036854775807(19位数) |
| 浮点型(小数) | float            | 4        | 1.401298E-45到3.4028235E+38                      |
|              | double(默认)     | 8        | 4.9000000E-324到1.797693E+308                    |
| 字符型       | char             | 2        | 0~65535                                          |
| 布尔型       | boolean          | 1        | true, false                                      |

## 方法

方法是执行特定任务或操作的代码块,代表一个功能,它可以接受数据进行处理,并返回一个处理后的结果

### 方法的定义格式

修饰符 返回值类型 方法名(形参列表) {
    方法体(需要执行的功能代码)

    return 返回值;
}

![alt text](./images/image2.png)

### 方法的注意事项

1. 方法可以重载
    - **一个类中**,出现**多个方法的名称相同**,但是它们的**形参列表是不同的**,那么这些方法就称为**方法重载**.
    - 方法重载只关心方法名称相同,形参列表不同(类型不同,个数不同,顺序不同).

2. 无返回值的方法中可以直接通过单独的return立即结束当前方法的执行

## 类型转换


- **类型范围小**的变量,可以**直接赋值**给**类型范围大**的变量
- **类型范围大**的变量,不可以**直接赋值**给**类型范围小**的变量,会报错,需要强制类型转换

![alt text](./images/image3.png)

强制类型转换格式: 类型 变量2 = (类型)变量1;

注意:强制类型转换**可能会造成数据(丢失)溢出**;浮点型强转为整形,**会直接丢掉小数部分,保留整数部分返回**

总结:

为什么需要进行类型转换?

- 存在不同类型的变量赋值给其他类型的变量

什么是自动类型转换?

- **类型范围小**的变量,可以**直接赋值**给**类型范围大**的变量

什么是强制类型转换?

- 默认情况下,大范围类型的变量直接赋值给小范围类型的

## 输入输出

- 输出:把程序中的数据展示出来.`System.out.println("Hello World");`
- 输入:程序读取用户键盘输入的数据.`通过java提供的Scanner程序来实现`

Scanner是java提供好的API,程序员可以直接调用

![alt text](./images/image4.png)

``` java
package com.learning.scanner;
import java.util.Scanner;
public class Test {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("请输入您的年龄:");
        int age = sc.nextInt();
        System.out.println("年龄是:" + age);

        System.out.println("请输入您的名称:");
        String name = sc.next();
        System.out.println("欢迎: " + name);
    }
}
```

## 运算符

### 基本的算术运算符

| 符号 | 作用 | 说明                             |
| ---- | ---- | -------------------------------- |
| +    | 加   | -                                |
| -    | 减   | -                                |
| *    | 乘   | -                                |
| /    | 除   | 在java中两个整数相除结果还是整数 |
| %    | 取余 | 获取的是两个数据做除法的余数     |

#### +符号在java中的特殊用途

- "+" 符号在有些情况下可以用作连接符
- "+" 符号与**字符串运算**的时候是用作**连接符**的,其结果依然是一个字符串

### 自增自减运算符

| 符号    | 作用                                       |
| ------- | ------------------------------------------ |
| 自增:++ | 放在某个变量前面或者后面,对变量自身的值加1 |
| 自减:-- | 放在某个变量前面或者后面,对变量自身的值减1 |

注意:

- ++, -- 如果在变量前后单独使用是没有区别的
- ++, -- 如果不是单独使用(如在表达式中,或同时有其他操作),放在变量前后会存在明显区别
  - 在变量的前面,先对变量+1, -1, 再拿变量的值运算
  - 在变量的后面,先拿变量的值运算,再对变量的值+1, -1

### 赋值运算符

#### 基本赋值运算符

- "=" ,赋值顺序从右往左

#### 扩展赋值运算符

| 符号 | 用法   | 作用       | 底层代码形式          |
| ---- | ------ | ---------- | --------------------- |
| +=   | a += b | 加后赋值   | a = (a的类型)(a + b); |
| -=   | a -= b | 减后赋值   | a = (a的类型)(a - b); |
| *=   | a *= b | 乘后赋值   | a + (a的类型)(a * b); |
| /+   | a /= b | 除后赋值   | a = (a的类型)(a / b); |
| %=   | a %= b | 取余后赋值 | a = (a的类型)(a % b); |

注意:扩展的赋值运算符隐含了强制类型转换

### 关系运算符,三元运算符

#### 关系运算符

 | 符号 | 例子                 | 作用                          | 结果                          |
 | ---- | -------------------- | ----------------------------- | ----------------------------- |
 | >    | a > b                | 判断a是否大于b                | 成立返回true, 不成立返回false |
 | >=   | a >= b               | 判断a是否大于或等于b          | 成立返回true, 不成立返回false |
 | <    | a < b                | 判断a是否小于b                | 成立返回true, 不成立返回false |
 | <=   | 判断a是否小于或等于b | 成立返回true, 不成立返回false |
 | ==   | a == b               | 判断a是否等于b                | 成立返回true, 不成立返回false |
 | !=   | a != b               | 判断a是否不等于b              | 成立返回true, 不成立返回false |
 
#### 三元运算符

- 格式: `条件表达式 ? 值1 : 值2;`
- 执行流程:首先计算**关系表达式的值**,如果值为true,返回值1, 如果为false,返回值2

### 逻辑运算符

把多个条件放在一起运算,最终返回布尔类型的值: true, false

| 符号   | 叫法     | 例子             | 运算逻辑                                                             |
| ------ | -------- | ---------------- | -------------------------------------------------------------------- |
| `&`    | 逻辑与   | 2 > 1 & 3 > 2    | 多个条件必须都是true, 结果才是true; 有一个是false, 结果就是false     |
| `\|`   | 逻辑或   | 2 > 1 \| 3 < 5   | 多个条件中只要有一个是true, 结果就是true                             |
| `!`    | 逻辑非   | !(2 > 1)         | 取反, 你真我假, 你假我真                                             |
| `^`    | 逻辑异或 | 2 > 1 ^ 3 > 1    | 前后条件的结果相同, 就直接返回false, 前后条件的结果不同, 才返回false |
| `&&`   | 短路与   | 2 > 10 && 3 > 2  | 判断结果与 "&" 一样, 过程不同, 左边为false, 右边不执行               |
| `\|\|` | 短路或   | 2 > 1 \|\| 3 < 5 | 判断结果与 "\|" 一样, 过程不同, 左边为true, 右边不执行               |

## 程序流程控制

### 分支结构

#### if分支结构

根据条件的真或假,来决定执行某段代码

![alt text](./images/image5.png)

#### switch分支结构

通过比较具体的值是否相等,来决定执行哪条分支

![alt text](./images/image6.png)

注意:

1. 表达式类型只能是**byte, short, int, char**, JDK5开始支持枚举,JDK7开始支持String, **不支持double, float, long**
2. case给出的值不允许重复, 且只能是字面量, 不能是变量
3. 正常使用switch的时候,不要忘记写break, 否则会出现穿透现象
4. 当存在多个case分支的代码相同时, 可以把相同的代码放到一个case块中, 其它的case块都通过穿透性穿透到该case块执行代码即可, 这样可以简化代码

### 循环结构

#### for循环

控制一段代码反复执行很多次

![alt text](./images/image7.png)

#### while循环

![alt text](./images/image8.png)

#### do-while循环

![alt text](./images/image9.png)

#### 死循环

可以一致执行下去的一种循环,如果没有干预不会停下来

![alt text](./images/image10.png)

#### 循环嵌套

循环中又包含循环

![alt text](./images/image11.png)

#### break, continue

- break: 跳出并结束当前所在循环的执行
- continue: 用于跳出当前循环的当次执行, 直接进入循环的下一次执行

注意:

- break: 只能用于结束所在循环, 或者结束所在switch分支的执行
- continue: 只能在循环中进行使用

## 数组

数组是一个数据容器,可用来存储一批同类型的数据

### 数组的定义方式

![alt text](./images/image12.png)

注意:`数据类型[] 数组名`也可以写成`数据类型 数组名[]`

### 动态初始化数组

定义数组时先不存入具体的元素值,只确定数组存储的数据类型和数组的长度

![alt text](./images/image13.png)

动态初始化数组元素默认值规则:

![alt text](./images/image14.png)

### 二维数组

数组中的每个元素都是一个一维数组, 这个数组就是二维数组

![alt text](./images/image15.png)

![alt text](./images/image16.png)

# java面向对象编程

对象是一种特殊的数据结构, 可以用来记住一个事物的数据, 从而代表该事物

1. 先设计对象的模板, 也就是对象的设计图: 类
2. 通过new关键字实例化对象, 每new一次类就得到一个新的对象

## 构造器

构造器是一种特殊方法, 不能写返回值类型, 名称必须和类名相同

``` java
public class Student {
    // 无参构造器
    public Student() {}

    //有参构造器
    public Student(String name, int age) {
        ...
    }
}
```

注意:

- 类默认就自带了一个无参构造器
- 如果为类定义了有参构造,类默认的无参构造器就没有了

## this关键字

- this就是一个变量, 可以用在方法中来拿到当前对象
- this主要用来解决变量名称冲突的问题

## 封装

### 什么是封装

- 就是用类设计对象处理某一个事物的数据时, 应该把要处理的数据, 以及处理这些数据的方法, 涉及到同一个对象中去
- 面向对象三大特征: 封装, 继承, 多态

### 封装的设计规范是什么样的

- 合理隐藏, 合理暴露

### 代码层面如何控制对象的成员公开或隐藏

- 公开成员, 可以使用`public`进行修饰
- 隐藏成员, 使用`private`进行修饰

## 实体类

是一种特殊类, 类中要满足如下需求:

1. 类中的成员变量全部私有, 并提供public修饰的getter/setter方法
2. 类中需要提供一个无参数构造器, 有参数构造器可选

## static

static叫静态, 可以修饰成员变量, 成员方法

成员变量按照有误static修饰, 分为两种:

- 静态变量(类变量): 有static修饰, 属于类, 在计算机里只有一份, 会被类的全部对象共享
- 实例变量(对象的变量): 无static修饰, 属于每个对象的

成员方法的分类:

- 静态方法: 有static修饰的成员方法, 属于类
- 实例方法: 无static修饰的成员方法, 属于对象

工具类不需要创建对象, 建议将工具类的构造器私有化

### 静态方法, 实例方法相关的注意事项

- 静态方法中可以直接访问静态成员, 不可以直接访问实例成员
- 实例方法中既可以直接访问静态成员, 也可以直接访问实例成员
- 实例方法中可以出现this关键字, 静态方法中不可以出现this关键字

## 继承

- java中提供了一个关键字extends, 用这个关键字, 可以让一个类和另一个类建立起父子关系
- 子类能继承父类的非私有成员(成员变量, 成员方法)
- 子类的对象创建是由子类, 父类共同完成的

### 权限修饰符

用来限制类中的成员(成员变量, 成员方法, 构造器)能够被访问的范围

- private 只能本类
- 缺省(default) 本类, 同一个包中的类
- protected 本类, 同一个包中的类, 子孙类
- public 任意位置

![alt text](./images/image17.png)

### 继承的特点

- 单继承: java是单继承模式, 一个类只能直接继承一个父类
- 多层继承: java不支持多继承, 但支持多层继承
- 祖宗类: java中所有的类都是Object类的子类
- 就近原则: 优先访问自己类中的成员(成员变量, 成员方法), 自己类中的没有才会访问父类

### 继承后子类访问成员的特点: 就近原则

1. 在子类方法中访问其他成员(成员变量, 成员方法), 是依照就近原则的
    - 先在子类局部范围找, 然后在子类成员范围找, 然后在父类成员范围找, 如果父类范围还没有找到就报错
2. 如果子父类中, 出现了重名的成员, 会优先使用子类的
    - 如果要在子类中访问父类成员可以通过`super`关键字, 指定访问父类的成员

### 方法重写

当子类觉得父类中的某个方法不好用, 或者无法满足自己的需求时, 子类可以重写一个方法名称, 参数列表一样的方法来覆盖父类的方法, 这就是方法重写

``` java
class Cat extends Animal {
    //方法重写: 方法名称, 形参列表必须一样
    @Override //方法重写的校验注解(标志): 要求方法名称和形参列表必须与被重写的方法一致, 否则报错
    public void cry() {
        System.out.println("喵喵喵");
    }
}

class Animal {
    public void cry() {
        System.out.println("咕咕嘎嘎");
    }
}
```

注意:

- 使用`Override`注解可以指定java编译器检查方法重写是否正确
- 子类重写父类方法时, 访问权限必须大于或者等于父类方法的权限(public>protected>默认)
- 重写的方法返回值类型, 必须与被重写方法的返回值类型一致, 或者范围更小
- 私有方法, 静态方法不能被重写

#### 方法重写的常见场景

- 子类重写`Object`类的`toString()`方法, 以便返回对象的内容

### 子类构造器

- 子类的全部构造器, 都会先调用父类的构造器, 再执行自己
- 默认情况下, 子类全部构造器的第一行代码都是`super()`(写不写都有), 它会调用父类的无参数构造器

### this(...)调用兄弟构造器

任意类的构造器中, 可以通过this(...)来调用该类的其他构造器

注意: super(...) this(...) 必须写在构造器的第一行, 且两者不能同时出现

## 多态

多态是在继承/实现情况下的一种现象, 表现为: 对象多态, 行为多态

![alt text](./images/image18.png)

### 多态的前提

有继承/实现关系; 存在父类引用子类对象; 存在方法重写

注意: 多态是对象, 行为的多态, java中的属性(成员变量)不具备多态

### 多态的好处

- 在多态形式下, 右值对象是解耦合的, 更便于扩展和维护

![alt text](./images/image19.png)

- 定义方法时, 使用父类类型的形参, 可以接受一切子类对象, 扩展性更强, 更便利

注意: 多态下不能使用子类的独有功能

### 多态下的类型转换问题

- 自动类型转换: 父类 变量名 = new 子类();
- 强制类型转换: 子类 变量名 = (子类) 父类变量;

注意:

- 存在继承/实现关系就可以在编译阶段进行强制类型转换, 编译阶段不会报错
- 运行时, 如果发现对象的真实类型与强转后的类型不同, 就会报类型转换异常(ClassCastException)的错误

强转前, java建议: 使用`instanceof`关键字, 判断当前对象的真实类型, 再进行强转

`p instanceof Student`

## final关键字

final关键字是最终的意思, 可以修饰: 类, 方法, 变量

- 修饰类: 该类被称为最终类, 特点是不能被继承了
- 修饰方法: 该方法被称为最终方法, 特点是不能被重写了
- 修饰变量: 该变量仅能被赋值一次

注意:

- final修饰基本类型的变量, 变量存储的数据不能被改变
- final修饰引用类型的变量, 变量存储的地址不能被改变, 但地址所指向对象的内容是可以被改变的

## 常量

- 使用了`static final`修饰的成员变量就被成为常量
- 作用: 常用于记录系统的配置信息

注意: 
- 常量名的命名建议使用大写英文单词, 多个单词使用下划线连接起来
- 程序编译后, 常量会被"宏替换": 出现常量的地方全部会被替换成字面量

## 枚举类

枚举是一种特殊类

![alt text](./images/image20.png)

特点:

- 枚举类中的第一行, 只能写枚举类的对象名称, 且要用逗号隔开
- 这些名称, 本质是常量, 每个常量都记住了枚举类的一个对象
- 枚举都是最终类, 不可以被继承, 枚举类都是继承java.lang.Enum类的
- 枚举类的构造器都是私有的, 因此, 枚举类对外不能创建对象

### 枚举类的常见应用场景

枚举类很适合做信息分类标志

## 抽象类

在java中有一个关键字叫: `abstract`, 意思是抽象, 可以用它来修饰类, 成员方法

- `abstract`修饰类, 这个类就是抽象类
- `abstract`修饰方法, 这个方法就是抽象方法

``` java
public abstract class A {
    //抽象方法: 必须abstract修饰, 只有方法签名, 不能有方法体
    public abstract void test();
}
```

注意:

- 抽象类中不一定要有抽象方法, 有抽象方法的类必须是抽象类
- 类有的成员: 成员变量, 方法, 构造器, 抽象类都可以有
- 抽象类不能创建对象, 仅作为一种特殊的父类, 让子类继承并实现
- 一个类继承抽象类, 必须重写完抽象类的全部抽象方法, 否则这个类也必须定义成抽象类

### 使用抽象类的好处

- 父类知道每个子类都要做某个行为, 但每个子类要做的情况不一样, 父类就定义成抽象方法, 交给子类去重写实现, 设计这样的抽象类, 就是为了更好地支持多态

## 接口

java提供了`interface`关键字用于定义接口

``` java
public interface 接口名 {
    // 成员变量(常量)
    // 成员方法(抽象方法)
}
```

注意: 

- 接口不能创建对象
- 接口是用来被类实现(implements)的, 实现接口的类成为实现类, 一个类可以同时实现多个接口
- 接口与接口可以多继承: 一个接口可以同时继承多个接口
- 一个接口继承多个接口, 如果多个接口中存在方法签名冲突, 则此时不支持多继承, 也不支持多实现
- 一个类继承了父类, 又同时实现了接口, 如果父类中和接口中有同名的方法, 实现类会优先用父类的
- 一个类实现了多个接口, 如果多个接口中存在同名的默认方法, 可以不冲突, 这个类重写该方法即可

``` java
修饰符 class 实现类类名 implements 接口1, 接口2, 接口3, ... {
    // 实现类实现多个接口, 必须重写完接口的全部抽象方法, 否则实现类需要定义为抽象类
}
```

### 接口的好处

- 弥补了类单继承的不足, 一个类同时可以实现多个接口, 使类的角色更多, 功能更强大
- 让程序可以面向接口编程, 这样程序员就可以灵活方便的切换各种业务实现(更利于程序的解耦合)

### 接口新增的三种方法

![alt text](./images/image21.png)

### 抽象类, 接口的区别

相同点:

1. 都是抽象形式, 都可以有抽象方法, 都不能创建对象
2. 都是派生子类形式: 抽象类是被子类继承使用, 接口是被实现类实现
3. 一个类继承抽象类, 或者实现接口, 都必须重写完他们的抽象方法, 否则自己要成为抽象类或者报错
4. 都支持多态, 都能够实现解耦合

不同点:

1. 抽象类中可以定义类的全部普通成员, 接口只能定义常量, 抽象方法(JDK8新增的三种形式)
2. 抽象类只能被类单继承, 接口可以被类多实现
3. 一个类继承抽象类就不能再继承其他类, 一个类实现了接口(还可以继承其他类或者实现其它接口)
4. 抽象类体现模板思想, 跟利于做父类实现代码的复用性
5. 接口更适合做功能的解耦合, 解耦合性更强更灵活