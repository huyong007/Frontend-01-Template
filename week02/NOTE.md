
### [乔姆斯基谱系](https://zh.wikipedia.org/wiki/%E4%B9%94%E5%A7%86%E6%96%AF%E5%9F%BA%E8%B0%B1%E7%B3%BB)
![乔姆斯基谱系](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdz4wfm4pjj30en0g1tev.jpg)


### [BNF](https://zh.wikipedia.org/wiki/%E5%B7%B4%E7%A7%91%E6%96%AF%E8%8C%83%E5%BC%8F)(Backus Normal Form:上下文无关文法，js中一般都是上下文无关文法)


\<Number\> ="0" | "1" | "2" | ..... | "9"

\<DecimalNumber\> = "0" | (("1" | "2" | ..... | "9") \<Number\>*)

\<DecimalNumber\> = /0|[1-9][0-9]*/(用正则写一下这些文法)

\<MultiplicativeExpression\> ::= \<DecimalNumber\> | 
    \<MultiplicativeExpression\> "*" \<DecimalNumber\> |
    \<MultiplicativeExpression\> "/" \<DecimalNumber\>

\<AdditiveExpression\> ::= \<MultiplicativeExpression\> | 
    \<AdditiveExpression\> "+" \<MultiplicativeExpression\> |
    \<AdditiveExpression\> "-" \<MultiplicativeExpression\>


\<LogicalExpression\> ::= \<AdditiveExpression\> | 
    \<LogicalExpression\> "||" \<DecimalNumber\> | 
    \<LogicalExpression\> &&" \<DecimalNumber\>


\<PrimaryExpressiong\> ::= \<DecimalNumber\> |
    "(" \<LogicalExpression\> ")"

### 上下文无关文法在js中的特例
- js中的特例：上下文相关文法

```js
{
    get a{return 1}
    get:1
}
```
- js表达式部分：一般都是正则文法
1. js表达式部分一般都是正则文法，左结合
2. 特例（右结合）
```js
2**1**2；
```

### 编程语言的理解结构

语法->语义->运行时

- Atom
  + Identifier
  + Literal


- Expression
  + Atom
  + Operator
  + Punctuator
  
- Statement
  + Expression
  + Keyword
  + Punctuator

- Structure
  + Function
  + Class
  + Process
  + Namespace
  + ....

- Program
  + Program
  + Module
  + Package
  + Library