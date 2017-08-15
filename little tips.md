1. toUppercase () 用于将小写字母转化为大写的字母
2. toLowercase () 用于将大写字母转化为小写的字母
> 使用 `indexOf` 的正确姿势
>  
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
> `~` 这个字符可以用于按位取反
```
console.log(~ -1) // 0
```  
因此我们可以这样计算:  

```
if (!~str.indexOf('d')) {

}
```
