1. toUppercase () 用于将小写字母转化为大写的字母
2. toLowercase () 用于将大写字母转化为小写的字母
### 使用 `indexOf` 的正确姿势  
我们经常会使用 `indexOf` 来查找元素是否存在，这个方法在数组中和字符串中经常这样使用：

```
var str = 'string';
if (str.indexOf('f') === -1) {
    console.log('the code is not have')
}
```
当数组或者字符串中没有包含我们要进行查找的字符串的时候，使用indexOf 返回 -1
> 实际上 我们使用 indexOf 的目的应该是用于查找字符或者数组中的元素在字符串和数组中的位置 >

```
var str = 'string';
console.log(str.indexOf('r')); // 2
```
对于使用 `indexOf` 我们可以使用 `~indexOf() ` 来实现
> `~` 这个字符可以用于按位取反 >

```
console.log(~ -1)
```
因此我们可以这样计算:  

```
if (!~str.indexOf('d')) {
}
```
使用  `~str.indexOf()` 如果 没有找到返回 0 , 在js 中 0 会被强制类型转换为 false ,使用这种操作就不用判断是否找到， 如果没有找到就返回 -1 了
### 使用 `call` 改变 this 的指向，要注意要使用作用域安全的构造函数

```
function person(name,age) {
    if (this instanceOf person) {
         this.name = name;
         this.age = age;
    } else {
         return new peron(name, age)
    }
}
```

上面这种方法是为了 调用构造函数的是时候 因为 粗心导致的调用构造函数的时候忘记加 `new` 操作符  

###  `instanceOf ` 和  `typeOf` 的区别  
`typeOf` 用来判断变量属于哪一种类型，通过使用这种方法判断出来的几种基本类型分别是： `number` `boolean` `string` `object`  `function` `undefined` 这五种基本类型  
~~`instanceOf` 用来判断 变量是否属于某种基本类型~~， 这种方法返回的是布尔值， 使用 `instanceOf` 只能判断 对象和函数，不能判断字符串或者数字 
> `instanceOf ` 这个检测方法，左边是待检测类的对象，右边是类的构造函数，实际上，使用 `instanceOf` 实现的应该是判断继承关系，我们使用 new 操作符进行继承构造函数的时候，使用的也是继承的用法

问题:

关于使用 position: fixed 的时候，如果仅仅设置 top: 0 出现元素在水平方向上不能水平居中的情况？？
