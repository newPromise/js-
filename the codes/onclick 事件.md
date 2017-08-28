存在代码如下：

html:
```
<div>
  <button  onclick = 'fn()'></button>
</div>

<script type= 'text/javascript'>
// 方案可行

function fn() {
  console.log('yes')
}

// 方案不可行
window.onload = function () {
  function fn() {
    console.log('yes')
  }
}
</script>
```
上面的这段代码是不能访问到  `fn()` 函数的，原因是因为 使用 `onclick` 访问到的函数应该位于 全局 `window` 中才能被访问到，这里面使用了一个函数，
使用 `window.onload()` 来定义的当所有的 `dom` 元素被加载之后调用函数， 这里面是作用域的问题， 这里面 fn 函数位于  `window.onload` 函数下的作用域中，
构建了函数作用域的时候，外部是无法访问到函数内部的。


因此， 不要在 html 元素上定义  onclick 事件， 如果要定义 onclick 事件，需要在将 onclick 事件调用之后的函数放到  `window.onload` 的外面

在window.onload 中给指定元素定义  `onclick`  事件， 或者使用 addEventListener 事件监听

使用 addEventListener 

node.addEventListener(type,  callback,  isBubble );

// type 声明要监听的事件类型
// callback 监听事件发生之后的回调函数
// isBubble 判断事件是否冒泡
```


```
