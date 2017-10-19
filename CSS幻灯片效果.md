如何使用 css 实现幻灯片效果？
```
<!doctype html>
<html>
<head>
  <style>
  img {
    display: none;
    width: 100px;
    height: 100px;
  }
  input:checked + img {
    background-color: blue;
    display: block;
  }
  input {
    position: absolute;
    left: -9999px;
  }
  label {
    cursor: pointer;
  }
  </style>
</head>
<body>
  <div id="cont">
    <input id="img1" name="img" type="radio" checked="checked">
    <img src="a.png" alt="图片1">
    <input id="img2" name="img" type="radio">
    <img src="b.png" alt="图片2">
  </div>
  <div id="nav">
    <label for="img1">第一张</label>
    <label for="img2">第二张</label>
  </div>
</body>
</html>
```
使用 `label` 中的for 链接的是对应的表格 id
input:checked + img:  获取到被选中元素的相邻 img 元素
