# 像视频流一样来展示图片

1. 后端用websocket推送图片流
2. 前端用webgl展示

容器大小
```css
    canvas {
        width: 1200px;
        height: 600px;
        display: block;
    }
```

```js
  // 设置图片100%显示,和容器大小一致。
  // setRectangle(gl, 0, 0, 1200, 600);
  setRectangle(gl, 0, 0, gl.canvas.width, gl.canvas.height);

  function setRectangle(gl, x, y, width, height) {
    var x1 = x;
    var x2 = x + width;
    var y1 = y;
    var y2 = y + height;
    gl.bufferData(gl.ARRAY_BUFFER, new Float32Array([
        x1, y1,
        x2, y1,
        x1, y2,
        x1, y2,
        x2, y1,
        x2, y2,
    ]), gl.STATIC_DRAW);
    }
```

A Pen created at CodePen.io. You can find this one at https://codepen.io/YvanYang/pen/GGmoEP.

 from: https://webgl2fundamentals.org/webgl/webgl-2d-image.html