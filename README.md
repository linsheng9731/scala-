Scala编程思想
=======

*这本书的读者应该是想要了解并使用scala的Java程序员*。

Scala是一门多范式语言，多范式体现在同时支持面向对象（OO）和函数式编程（FP）。在scala的世界里一切皆对象，同时函数又是一等公民。这听起来很不可思议，但是Martin做到了，他把这两种特性混合在了一起，互补所长，让程序员不再局限于语言的范式。据我自己使用和学习scala的体验来说，scala的确是一门现代语言，很多特性都经过语言创造者苦心的设计。其中一大特性是写出来的程序非常简洁，所有语法糖的设计初衷都是围绕怎样简化代码书写展开的，如果你很熟悉scala的语法，那么写scala的时候会感觉非常省事，所有步骤都已经最简化。这里举一个小例子，在Java里定义一个类：
```
class Rectangle{
      int width;
      int height;
      public Rectangle(int w,int h){
         width = w;
         height = h;
      }
}
Rectangle r = new Rectangle();
```
如果你不想获取width和height，(默认构造参数为val不可变型，因为在scala里面不提倡使用中间状态即var可变型)只需要下面这样定义这个类即可：
```
class Rectangle(width:Int,height:Int){
}
val r = new Rectangle
```
scala会自动生成构造函数待参数的构造函数，当然你也以重载构造函数，提供更丰富的构造特性。在实例时不需要重复写Rectangle这个类名，scala会做类型推断。同时在scala里分行的代码不需要';'，大部分情况下都可以省略'()'，函数的最后一行就是返回函数的返回值，这种情况下可以省略return。这种小的改进在scala里随处可见，他们一般都是有规律的，只要你从 *“如何少写代码，同时又能满足编译器的要求”* 这个观点出发，就可以解释他们，然后感叹 “太厉害了！”


这本书的前几章会先从OO的角度切入scala，在scala的世界里一切皆对象，熟悉java的程序员可能都知道java里有基本数据类型，这让java变成一门不是那么纯粹的OO语言。虽然提供了包装类和自动拆装箱机制来弥补这点的不足，不过还是让人觉得很别扭。scala不同，在scala的世界里，基本的数据类型包括Int,Float,Double,Boolean都是对象。下面这个例子可以说明这个问题：
```
scala> 2.+(2)
scala> Int = 4
```
你没有看错，就是2这个整型对象调用了+(x:Int)这个函数，返回了一个Int型的对象。这里还有一个概念：所有的符号都是函数，这点我们后续会继续探讨。当然平时我们不太可能这样来写，一般是下面的写法，但是两者效果完全一致：
```
scala> 2+2
scala> Int = 4
```
总体来说scala的OO部分和java相差不大，有些看上去是scala才有的概念其实可以用java现有的思想来解释，比如trait，我们称之为特质的一种概念。其实是interface接口的改进。由于scala是运行在JVM上的语言所以他天生就可以和java本身数目庞大的类库进行协作，你可以引用任意的java类库来为你所用，这让Java程序员意识到scala对Java生态圈的友好兼容。

本书的后面一些的章节会逐步以函数式编程的角度来改写之前的代码，让你看到函数式编程的威力。在函数式编程的世界里(以下简称FP)，函数是一等公民，函数可以作为一个参数传递给另一个函数，一个函数又可以产生一个函数（这被称为柯里化即currying）。甚至一段代码文本也可以作为一个函数，总而言之，在FP的世界里不区分代码还是数据，同时FP也提倡函数不应该产生副作用，也就是说他不应该修改输入也不应该产生中间状态，所有的操作都是推算。这和数学里的公式的概念很像，但是这样的坏处是说代码变得很难读，虽然相比lisp或者haskell而言要简单很多，不过长了还是很难看懂。它的优点当然也非常多，函数可以作为参数，函数可以返回函数，可以有lambda表达式，这些特性都极大的带给了我们便利，同时也让scala非常适合作为一名DSL语言。

当然scala还有很多其他特性，比如说集成了xpath语法，使得scala自带对xml的解析功能。借鉴erlang的actor的并发模型，可以使scala轻松编写出并发的服务器。这所有的一切都使得scala值得大家花时间去学习!
