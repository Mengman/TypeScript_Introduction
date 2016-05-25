#二、变量声明

## 2.1 let
JavaScript中使用var关键字来声明变量，let关键字同样也是用来声明变量的，但是它能够避免使用var出现的一些不必要的麻烦，在TypeScript中如果可能都尽量使用var来声明变量，而避免使用var。

## 2.2 const
利用const声明的变量，一旦被赋值以后，就不能在被赋其他的值：
```TypeScript
   const unchangeNumb: number = 9;
   unchangeNumb = 10; // error
   const kitty = {
      name: 'cake',
      age: 1
   }
   
   kitty = {
     name: 'delta',
     age: 3
   }   // error, cannot be re-assiged
   
   kitty.age = 3;
   kitty.name = 'delta'; // is ok
```

## 2.3 Destructuring(解构赋值)
解构赋值表达式能够从数组或者对象中获得数据，并将它赋值给变量。

### 2.3.1 Array destructuring(数组解构赋值)

```TypeScript
 let input:number[] = [1, 2];
 let [first, second] = input;
 console.log(first); // print 1
 console.log(second); // print 2
 
 // 对于已经声明的变量也适用
 [second, first] = [first, second];
```
解构赋值表达式中可以将数组中的多个元素赋值给一个变量：
```TypeScript
  let [first, ...rest] = [1, 2, 3, 4];
  
  let [first] = [1, 2, 3, 4];
  let [,second] = [1, 2, 3, 4]; // second = 2
  let [, second, ,four] = [1, 2, 3, 4];
```
其中first的值为1， rest的值为[2, 3, 4].

### 2.3.2 Object desctructuring(对象解构赋值)
通过解构获取对象属性的值时，需要保持变量名称与对象属性名称一致。如果要修改名称需要在变量名后加冒号跟新的变量名。
```TypeScript
  let o = {
   a: 'foo',
   b: 'bar',
   c: 2000
  }
  
  let {a, b, c} = o;
  
  console.log(a); // print 'foo'
  console.log(b); // print 'bar'
  console.log(c); // print 2000
  
  let {a:first, b:second, c:third} = o;
  console.log(first);  // print 'foo'
  console.log(second); // print 'bar'
  console.log(third);  // print 2000
```
