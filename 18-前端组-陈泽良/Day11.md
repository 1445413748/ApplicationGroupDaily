# HTML5+CSS3
## js-canvas用法
**1.canvas（画布）**   
<canvas>是HTML 5 新增的元素，可用于通过使用JavaScript中的脚本来绘制图形,默认宽高为300px*150px.   
**2.渲染上下文**    
<canvas>元素只是创造了一个固定大小的画布，要想在它上面绘制内容，我们需要找到它的渲染上下文
<canvas>元素有一个getContex（）方法，这个方法是用来获取渲染上下文和它的绘画功能
　　基本用法：
```
　  <canvas id="cav" width="300px" height="150px"></canvas>
    var canvas = document.querySelector("#cav")
　  if(canvas.getContext){    //  必须判断是否存在该方法，即判断浏览器是否支持canvas
    var ctx = canvas.getContext("2d");
　　　　                    }
```
 **3.画布api**
 ```
        oc.getContext("2d");
        oc.width
        oc.height
```
**4.上下文api** 
```
        ctx.fillRect(x,y,w,h)://填充矩形
        ctx.strokeRect(x,ymwmh)://带边框的矩形
        ctx.clearRect(0,0,oc.width,oc.height)://清除整个画布   注意原点的位置
        ctx.fillStyle
        ctx.strokeStyle
        ctx.lineWidth
        ctx.lineCap
        ctx.lineJoin
        ctx.moveTo(x,y)://将画笔抬起点到x，y处
        ctx.lineTo(x,y)://将画笔移到x，y处
        ctx.rect(x,y,w,h)
        ctx.arc(x,y,r,degS,degE,dir)
        ctx.arcTo(x1,y1,x2,y2,r)://2个坐标,一个半径
        //结合moveTo(x,y)方法使用，
                x,y://起始点
                x1,y1：//控制点
                x2,y2：//结束点
        ctx.quadraticCurveTo(x1,y1,x2,y2)        //创建二次贝塞尔曲线
                结合moveTo(x,y)方法使用，
                x,y://起始点
                x1,y1：//控制点
                x2,y2：//结束点
                必须经过起点和终点
        ctx.bezierCurveTo(x1, y1, x2, y2, x3, y3)     //   创建三次方贝塞尔曲线
                结合moveTo(x,y)//方法使用，
                x,y://起始点
                x1,y1：//控制点
                x2,y2：//控制点
                x3，y3：//结束点
                //必须经过起点和终点
        ctx.fill()
        ctx.stroke()
        ctx.beginpath()://清除路径容器
        ctx.closepath()://闭合路径
            fill//自动闭合
            stroke//需要手动闭合
        ctx.save()
            //将画布当前状态(样式相关 变换相关)压入到样式栈中
        ctx.restore()
            //将样式栈中栈顶的元素弹到样式容器中
            //图像最终渲染依赖于样式容器
        ctx.translate(x,y)://将原点按当前坐标轴位移x，y个单位
        ctx.rotate(弧度)://将坐标轴按顺时针方向进行旋转
        ctx.scale(因子):
```
放大：放大画布，画布中的一个css像素所占据的物理面积变大，画布中包含的css像素的个数变少画布中图像所包含的css像素的个数不变.    
缩小：缩小画布，画布中的一个css像素所占据的物理面积变小，画布中包含的css像素的个数变多 画布中图像所包含的css像素的个数不变.    
**5.绘制矩形**  
绘制矩形有几个函数  
clearRect(x, y, w, h) 清楚指定的矩形    
fillRect(x, y, w, h) 绘制一个实心矩形   
strokeRect(x, y, w, h) 绘制一个空心矩形 
示例代码:
```
            <script>
                var ctx = document.getElementById("canvas").getContext("2d");
                
                var offset = 10;
                var size = 50;
                var count = 5;
                for (var i = 0; i < count; i++) {
                    ctx.fillRect(i * (offset + size) + offset, offset, size, size);
                    ctx.strokeRect(i * (offset + size) + offset, (2 * offset) + size, size, size);
                }
                       
            </script>
```
**5. 使用渐变**
有两种渐变  
createLinearGradient(x0, y0, x1, y1);   
createLinearGradient(x0, y0, r0, x1, y1, r1);
```
         <script>
                var ctx = document.getElementById("canvas").getContext("2d");
                var grad = ctx.createLinearGradient(0, 0, 500, 140);
                grad.addColorStop(0, "red");
                grad.addColorStop(0.5, "white");
                grad.addColorStop(1, "black");
             
             ctx.fillStyle = grad;
             ctx.fillRect(0, 0, 500, 140);
            </script>
        </body>
```