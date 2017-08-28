数组的 `filter` 在字面意义上是过滤，这个方法用在数组中，用来过滤数组的操作
用法：
注意： 使用 filter 不会改变原始数组的值
filter 不会对空数组进行检测

接收的参数：

currentVlaue: 当前的值

index : 当前值在数组中的索引

arr:应用到这个方法的数组

thisValue : 回调函数的 this 值
array.filter(function (currentValue, index, arr) {
  // some juge
}, thisValue)


```
var arr = [1,2,5,6,10];
var newArr = arr.filter(function (item， index, arr) {
  return item > 1
});

console.log(newArr) // [2,5,6,10] 
```

#### filter 的应用

1.数组去重：


```
var arr = [1,2,2,4,6,8];
var newArr = arr.filter(function (item, index, arr) {
    return arr.indexOf(item) === index;
});
console.log(newArr);
```

关于数组去重，还有几种方法，下面的是 使用 map 方法：

```
var arr =[...];
arr.map(function (item,index) {
  arr.indexOf(item) !== arr.lastIndexOf(item)  arr.splice(index, 1) : '';
})
使用 splice 用来删除数组
```

### 订阅模式之 观察者模式

