### touch 事件
touch 事件用于移动端的触摸事件，因为使用click 事件会有 300ms的延迟，在移动端中使用touch事件：
touch:
#### touchstart:
touchstart 在用户触摸屏幕的时候触发  
touchend 在用户手指离开屏幕的时候触发  
touchmove 当我们手指滑动的时候触发

```
dom.addEventListener('touchstart', function (e) {
  console.log(event)
})
```
对于 touch event 事件，包含下面几个属性：这个是一个对象，包含下面的属性：
```
touches:

targetTouches:

changedTouches:

```
几个参数如下：
1.touches : 当前屏幕上所有触摸点的集合
通过console 打印出来的 touches 是一个touchList 的列表，这里面是所有触摸事件的集合，如果我们有两个手指触摸， touch.length = 2, 平常我们当使用一个
手指的时候，我们通过使用 touches[0] 来获得这个触摸事件的详细信息
TouchList {0: Touch, length: 1}length: 10: TouchclientX: 133.33334350585938clientY: 89.33333587646484force: 1identifier: 0pageX: 133.33334350585938pageY: 89.33333587646484radiusX: 15.333333969116211radiusY: 15.333333969116211rotationAngle: 0screenX: 599screenY: 210target: a.active__proto__: Touch__proto__: TouchList
2.targetTouches: 当前对象上所有触摸点的列表，获得的touch列表是和 使用touches获得的触摸列表是相同的  
3.changedTouches: 表示自上次以来发生了什么变化的 Touch对象的数组:
```
dom.addEventListener('touchmove', function (e) {
    console.log(e.changedTouches)
})
```
这个属性会当我们触摸点发生变化的时候返回新的触摸数组，

#### touch列表内的属性:

当我们通过使用 touches targetTouches 获得的当前对象的的

```
length
:
1
0
:
Touch
clientX
:
212.00534057617188
clientY
:
71.41200256347656
force
:
1
identifier
:
0
pageX
:
212.00534057617188
pageY
:
71.41200256347656
radiusX
:
25.663801193237305
radiusY
:
25.663801193237305
rotationAngle
:
0
screenX
:
589
screenY
:
176
target
:
div#tou1
__proto__
:
Touch
__proto__
:
TouchList
```
