#TypeScript入门教程
  TypeScript作为JavaScript的超集，不仅完全兼容JavaScript语法。而且在语言设计的风格上非常接近Java、C#等语言。TypeScript语言最终由编译器编译成JavaScript语言。
  
## 一、数据类型
  TypeScript提供了三种基本数据类型：Number、String和Boolean，而JavaScript中还提供了额外的两种数据类型：Undefined和Null，由于TypeScript是JavaScript大的一个超集，所以Typescript总共的基本类型包含了以上5种。
  
### 1.1 Boolean
  TypeScript中的Boolean类型与JavaScript中的Boolean类型一样，都是true/false的字面常量。声明一个Boolean变量的格式如下：
```TypeScript
   let isDone:Boolean = true;
```

### 1.2 Number
  与JavaScript相同，TypeScript中的Number类型都是浮点数。TypeScript支持ECMAScript 2015中对于二进制数和八进制数的表示。
```TypeScript
  let decimal: number = 6;
  let hex: number = 0xf00d;
  let binary: number = 0b1010;
  let octal: number = 0o744;
```
  在ECMAScript 2015之前，JavaScript中表示八进制的方式与TypeScript是不同的。
```JavaScript
   var octal1 = 070; // decimal 56
   var decimal1 = 079; // decimal 79
```
### 1.3 String
  TypeScript与JavaScript一直，在表示String数据时用单引号(')或(")括起来。
  TypeScript中引入了模板字符串(template strings)的概念,
  字符串被括在反单引号(`)中（数字键1左边的那个按键），模板字符串可以跨越多行,并且可以在模板字符串中通过 ${ exp } 引用其它变量。
```TypeScript
   let color_1:string = "blue"; 
       color_2 = 'red';
   let sentence: string = `
                            Finn love color ${color_1}, 
                            Fiona love color ${color_2}.
   `
```

### 1.4 Array
 