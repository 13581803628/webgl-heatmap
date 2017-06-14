WebGL 热力图
=============

webgl-heatmap.js 是一个高性能的热力图显示 JavaScript 库。

演示
----

在线演示地址: [codeflow.org](http://codeflow.org/entries/2013/feb/04/high-performance-js-heatmaps) http://codeflow.org/entries/2013/feb/04/high-performance-js-heatmaps

怎么使用它
-------------

实例化一个新的热力图，可能会遇到以下异常情况:

 * 不支持 Webgl
 * 不支持浮点纹理
 * 不支持浮点渲染指针
 * 着色器编译异常: ...
 * 着色器链接异常: ...

```javascript
try{
    var heatmap = createWebGLHeatmap({canvas: yourCanvas});
}
catch(error){
    // 处理异常
}
```

构造参数

 * canvas: 你想要绘制热力图的 canvas 画布
 * width: 显示宽度
 * height: 显示高度
 * intensityToAlpha: 默认值为 true
 * gradientTexture: 纹理使用而不是颜色计算，可以是路径或图像

添加一个数据点

 * x、y:  像素位置，相对于 canvas 画布的 x 和 y 像素值
 * size: 像素尺寸（半径）
 * intensity: 0 到 1 之间的透明度

```javascript
heatmap.addPoint(x, y, size, intensity);
```

添加一列数据点

 * x、y: 数据点相对于 canvas 画布的像素位置
 * size: 数据点辐射区域大小（半径）
 * intensity: 0 到 1 之间的透明度

```javascript
heatmap.addPoints([{x:x, y:y, size:size, intensity:intensity}]);
```

绘制数据点堆栈:

```javascript
heatmap.update()
```

显示热力图:

```javascript
heatmap.display()
```

将热力图中的所有值乘以一个数字(对衰变有用):

```javascript
heatmap.multiply(0.995)
```

将热图中的所有值夹在两个值之间:

```javascript
heatmap.clamp(0.0, 1.0)
```

对热力图进行轻微模糊处理:

```javascript
heatmap.blur()
```

许可
-------

Copyright (c) 2013, Florian Boesch <pyalot@gmail.com> http://codeflow.org/

WebGL 热力图在以下许可下:

 * MIT: 详见 mit-license
 * GPL: 详见 gplv*-license
 * BSD: 详见 bsd-license
