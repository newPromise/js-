```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div class="block">
    <div class="ss">
        <div class="sss">
            <p>我得到了</p>
        </div>
    </div>
</div>
<script type="text/javascript">
    window.onload = function () {
        // 链式调用函数，用来调用元素
        function $(tag) {
           var tags = [];
           // 使用trim函数移除字符串两边的空格，对于存在浏览器不支持的情况，使用正则表达式进行替换
           tag = tag.trim();
           if (~tag.indexOf(' ')) {
               tags = tag.split(' ');
           } else {
               tags.push(tag);
           }
           // 使用 reduce 迭代数组，回调函数包含四个参数
           return  tags.reduce(posTag, tags[0]);
           // 用于定位 tag 标签，包含四个回调函数，
           // pre 上次迭代的值，cur 当前值 index, 执行回调函数的数组元素的 index 值 array,要进行回调的数组
           // 这一部分要进行判断，要寻找的class 有没有在里面
           function posTag(pre, cur, index, array) {
              var tagTip = ['.', '#'];
              if (~cur.indexOf('#')) {
                  return document.getElementById(cur.slice(1));
              }
              if (~cur.indexOf('.')) {
                  if (index === 0) {
                      var arr = [];
                      if (document.getElementsByClassName(cur.slice(1))) {
                          for (var i = 0; i < document.getElementsByClassName(cur.slice(1)).length; i++) {
                              arr.push(document.getElementsByClassName(cur.slice(1))[i]);
                          }
                          return arr;
                      } else {
                          return  console.log('没有找到相应的元素');
                      }
                  } else {
                      var newArr = [];
                      pre.map(function (item) {
                          var child = item.getElementsByClassName(cur.slice(1));
                          if (child.length !== 0 && child) {
                              for (var i =0; i<child.length; i++) {
                                  newArr.push(child[i]);
                              }
                          }
                      });
                     return  newArr;
                  }
              }
           }
        }
        $('.block .ss .sss')[0].style.backgroundColor = 'red';
    }
</script>
<style type="text/css">
    .sss {
        width: 200px;
        height: 200px;
    }
</style>
</body>
</html>
```
