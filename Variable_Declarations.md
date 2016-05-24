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
```TypeScript

```