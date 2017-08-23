```

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<canvas id="canvas">

</canvas>
<script type="text/ecmascript">
    window.onload = function () {
        var canvas = document.getElementById('canvas');
        var can = canvas.getContext('2d');
        var isMouse = false;
        can.beginPath();
        canvas.addEventListener('mousedown', function (event) {
            can.moveTo(event.pageX, event.pageY);
            isMouse = true
        });
            canvas.addEventListener('mousemove', function (event) {
                if (isMouse) {
                    console.log('前距离', event.pageX);
                    console.log('被作用到的距离', getCanvasPos('canvas').x);
                    event.pageX = event.pageX - getCanvasPos('canvas').x;
                    event.pageY = event.pageY - getCanvasPos('canvas').y;
                    can.lineTo(event.pageX,event.pageY);
                    console.log('后距离', event.pageX);
                    can.stroke();
                    can.moveTo(event.pageX, event.pageY);
                }
            });
        canvas.addEventListener('mouseup', function () {
             isMouse = false;
             console.log('goooooooooood');
        });
        console.log('canvas的距离', getCanvasPos('canvas').y);
        function getCanvasPos (canvasId) {
            var ca = document.getElementById(canvasId);
            var pos = {
                x: 0,
                y: 0
            };
            pos.x = ca.getBoundingClientRect().left;
            pos.y = ca.getBoundingClientRect().top;
            return pos;
        }

    }
</script>
<style type="text/css">
    #canvas {
        width: 500px;
        height: 500px;
        border: 1px solid black;
    }
</style>
</body>
</html>
```
