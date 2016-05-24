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
 TypeScript中数组有两种表示方法：
 ```TypeScript
    let list: number[] = {1, 2, 3};
    let list: Array<number> = {1, 2, 3};
 ```
 对比JavaScript中数组的两种创建方式：
 ```JavaScript
    var array = new Array(1, 2, 3);
    var array = [1, 2, 3];
 ```
 
 ### 1.5 元组
 TypeScript的元组中可以存放一系列不同类型的值，并且值的数量也是固定的。
 ```TypeScript
   let tupleA: [string, numbr];
   tupleA = ['apple', 5];
 ```
 获取元组内值的方法与数组类似，都是通过方括号与下标的形式：
 ```TypeScript
   console.log(tupleA[0]); // print "apple"
 ```
 
  ### 1.6 枚举
  枚举是JavaScript中不存在的数据类型，通过枚举这种友好的方式，可以给一组数字名字。
  ```TypeScript
     enum Shape {Triangle, Square, Pentagon};
     let s = Shape.Square;
     console.log(s); // print 1
  ```
  枚举元素默认从0开始，不过也可以自定义起始数字的值：
  ```TypeScript
     enum Shape {Triangle=1, Square, Pentagon};
     let s = Shape.Square;
     console.log(s); // print 2
  ```
  进一步的，我们可以自定义每一个元素的值：
  ```TypeScript
     enum Shape {Triangle=4, Square=2, Pentagon=7};
     let s = Shape.Square;
     console.log(s); // print 2
  ```
  
  ### 1.7 any
  当一个变量的类型被定义为any时，变量的真正类型会在编译时确定。
  ```TypeScript
     let a: any = 4;
     a = 'a';
     a = true;
  ```
  
  ### 1.8 void
  在TypeScript中，void类型通常用来表示函数不返回任何值：
  ```TypeScript
    function doNothing(): void {}
  ```
  当使用void来声明一个变量时，变量只能被赋值'undefined'或者'null'.
  ```TypeScript
     let nothing: void = undefined;
     nothing = void;
     nothing = 3; // Error
  ```
  
  ### 1.9 类型断言
  在某些情况下，开发人员比编译器更加了解变量的实际类型，会想要让编译器将变量转换到它实际的类型，这个时候就需要用到类型断言。
  使用类型断言的方法有两种，一种是在变量前用尖括号包裹其实际的类型，另一种是用as关键字将它转换到实际的类型。
  ```TypeScript
    let someVal: any = 'this is a string';
    let strLength: number = (<string>someVal).length;
    let strLength: number = (someVal as string).length; 
  ```