Scala编程思想
=======

*这本书的读者应该是想要了解并使用scala的Java程序员*。

Scala是一门多范式语言，多范式体现在同时支持面向对象（OO）和函数式编程。在scala的世界里一切皆对象，同时函数又是一等公民。这听起来很不可思议，但是Martin做到了，他把这两种特性混合在了一起，互补所长，让程序员不再局限于预言的范式。据我自己使用和学习scala的体验来说，scala的确是一门现代语言，很多特性都经过语言创造者苦心的设计。其中一大特性是写出来的程序非常简洁，所有语法糖的设计初衷都是围绕怎样简化代码书写展开的，如果你很熟悉scala的语法，那么写scala的时候会感觉非常省事，所有步骤都已经最简化。这里举一个小例子，在Java里定义一个类：
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
如果你不想获取width和height，只需要下面这样定义这个类即可：
```
class Rectanle(width:Int,height:Int){
}
val r = new Rectangle
```
scala会自动生成构造函数待参数的构造函数，当然你也以重载构造函数，提供更丰富的构造特性。在实例时不需要重复写Rectangle这个类名，scala会做类型推断。同时在scala里分行的代码不需要';'，大部分情况下都可以省略'()'。这种小的改进在scala里随处可见，他们一般都是有规律的，只要你从*“如何少写代码，同时又能满足编译器的要求”*这个观点出发，就可以解释他们，然后感叹“太厉害了！”


这本书的前几章会先从OO的角度切入scala，让Java程序员意识到scala对Java生态圈的友好兼容。后面会逐步以函数式编程的角度来改写之前的代码，让你看到函数式编程的威力。
