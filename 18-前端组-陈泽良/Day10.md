# HTML5+CSS3
## 常用元素 
**progress和meter元素**             
progress元素和meter元素的区别   
progress元素和meter元素经常会被混淆。它们之间的区别主要有以下两点：    
progress元素用于显示某个特定任务的时间进度。这个任务的时间上限是可以确定的值，如播放一段音乐的时间；或者是不可确定的值，如上传一个文件到服务器上。progress元素的最大值在元素显示时可能是不确定的。例如，完成一个表单提交所需要的进度条。meter元素的不同之处在于，它的最小值和最大值必须是确定的。  
另外一个区别是，progress元素的最小值可以是0。而meter元素的最小值必须是一个浮点数，包括负数，可以想象一下温度计的刻度。
示例代码:
```
<progress value="10" max="100"></progress>    
```
效果:<progress value="10" max="100"></progress>     

**footer元素**              
我们在html5开发使用footer标签时，把当作普通div标签对待即可，只不过一般用于网站底部布局。一般情况下一篇网页只有一个底部区，所以使用最好只使用一次footer即可。    
用例:   
```
    <footer> 
    　　© DIVCSS5.COM 版权所有<br /> 
    　　学习CSS，找DIV+CSS资源上DIVCSS5! 
    </footer> 
```
**addresee元素**    
address标签用来定义文档作者或拥有者的联系信息
address标签包含的文本通常显示为斜体。很多的浏览器都会在该元素的前后添加换行。    
提示：如果不是拥有者的联系信息，address元素不能用来描述邮政通讯地址。    
提示：address元素通常连同其他信息被包含在footer元素中。
示例代码:
```
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>我有答案(http://www.baidu.com/)</title> 
</head>
<body>
<address>
Written by <a href="123456@qq.com">Jon Doe</a>. 
Visit en at:
Example.com
Box 888, Disneyland
ZH
</address>
</body>
</html>
```
**figure和figcaption元素**  
figure标签规定独立的流内容（图像、图表、照片、代码等等）。  
figure元素的内容应该与主内容相关，但如果被删除，则不应对文档流产生影响。它是一种元素的组合，可带有标题（可选）。figure标签用来表示网页上一块独立的内容，将其从网页上移除后不会对网页上的其他内容产生影响。
figure有一个子标签：figcaption。
**figcaption**  
figcaption标签定义 figure 元素的标题（caption）。
"figcaption" 元素应该被置于 "figure" 元素的第一个或最后一个子元素的位置。
示例代码:
```
    <figure>
        <img alt="Web前端之家" src="logo.png"/>
        <figcaption>Web前端之家，专注Web前端，HTML5、CSS3、JavaScript、JQuery、移动开发、页面性能优化等开发前端技术的交流平台</figcaption>
    </figure>
```
**datials和summary元素** 
一般情况下，details用来对显示在页面的内容做进一步骤解释。首先是details标签，里面接着是标题summary，这里面的内容一般简短，具有总结性，会展示在页面。接着可以跟任意类型的HTML元素作为详情内容，这些内容需要在点击summary才会呈现。       
summary标签为details元素定义一个可见的标题。 当用户点击标题时会显示出详细信息。
示例代码:   
```
<details>
    <summary>Google Nexus 6</summary>
    <p>商品详情：</p>
    <dl>
        <dt>屏幕</dt>
        <dd>5.96” 2560x1440 QHD AMOLED display (493 ppi)</dd>
        <dt>电池</dt>
        <dd>3220 mAh</dd>
        <dt>相机</dt>
        <dd>13MP rear-facing with optical image stabilization 2MP front-facing</dd>
        <dt>处理器</dt>
        <dd>Qualcomm® Snapdragon™ 805 processor</dd>
    </dl>
</details>
```
**mark元素用法**    
mark元素是HTML 5中新增的元素，主要功能是在文本中高亮显示某个或某几个字符，旨在引起用户的特别注意。其使用方法与em和strong元素有相似之处，但相比而言，HTML5中新增的mark元素在突出显示时，更加随意与灵活。
示例代码:
```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>mark元素的使用</title>
<link href="Css/css3.css" rel="stylesheet" type="text/css">
</head>
<body>
<h5>优秀开发人员的<mark>素质</mark></h5>
<p>
一个优秀的Web页面开发人员，必须具有
<mark>过硬</mark>的技术与
<mark>务实</mark>的专业精神
</p>
</body>
</html>
```
    