对于任何的复杂逻辑，都要进行声明 `computed` 

computed: 计算属性 :
使用计算属性 `computed` 和 方法 `methods` 的不同在于，使用 computed 是基于依赖进行计算的方法，如果在 computed 中的依赖发生了，那么，两者之间的区别在于
使用 computed 的时候，只有 使用 computed 中的依赖发生改变的时候， 函数会进行重新计算
computed 是基于依赖进行缓存的。  

相比于 `watch` computed 的区别

> 注意， 不要滥用 watch

在官网上，给了这么一个的例子：
```
export default {
  name: 'demo',
  data () {
    firstName: 'ningning'，
    lastName:  'zhang',
    fullName: ''
  },
  // 这里使用  watch 使用的方法使用  watch 将lastName 和 firstName 进行组合成 fullName
  watch: {
    firstName: function (val) {
      this.fullName = val + ' ' + this.lastName
    },
    lastName: function (val) {
      this.fullName = this.firstName + ' ' + val
    }
  }
}
```
使用 computed 方法进行计算：

```
computed: {
  fullName: function () {
      return this.firstName + this.lastName;
  }
}
```
那么 

#### 使用 computed 的场景？

当一个对象是其他对象的组合的时候, 一个对象是有多个对象进行计算得来的， 当多个对象发生变化的时候，那个对象发生改变， 使用  watch 的方法，需要监听多个对象，
我么使用 computed 就可以实现 ；
我们只需要对于主对象进行监听就好啦！！！！
