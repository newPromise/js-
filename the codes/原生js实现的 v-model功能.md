使用原生js 实现Vue 中的 v-model 功能：
```
<div>
  <input type="text" id="a">
  <span id="b"></span>
<div>
<script type = "text/script">
  window.onload = function () {
    var object = {};
    Object.defineProperty(object, 'hello', {
      get () {
        console.log('我被调用了啦啦啦')
      }，
      set (newVal) {
        document.getElementById('a').innerHTML = newVal;
        document.getElementById('b').innerHTML = newVal;
      }
     }
    )
    document.addEventListener('keyup', function (e) {
      object.hello = e.target.value
    })
  }
</script>
```
实现实时改变的原因是使用 definePorperty 的 set 和 get方法来实现的
