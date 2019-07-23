# HTML5+CSS3
## HTML5拖放
**1、draggable 属性**   
通过 draggable告诉浏览器哪些元素需要实现拖拽功能。有三个可选值：  
true： 元素可以被拖拽   
false：元素不能被拖拽   
auto：浏览器自己判断元素是否能被拖拽 ( 默认 )   
**2、对象拖放事件**     
dragstart：按下鼠标键并开始移动时触发   
drag：在元素拖拽过程中持续触发----相似与mousemove   
dragend：元素拖拽停止时触发 

**3,拖动事件**  
当按住鼠标拖动draggable元素的时候会按照如下顺序依次触发  
dragstart -> drag -> dragend    
dragstart:在按住鼠标开始拖动时候触发（触发一次）          

drag:在按住鼠标拖动的过程触发（持续触发）

dragend:在释放鼠标后触发（无论是把元素放到了有效的放置目标，还是放置到了无效的放置目标上）  

**4,放置事件**  
当将draggable元素元素拖动到容器中将会按照如下顺序依次触发    
dragenter -> dragover -> drop
    dragenter
    只要有元素被拖动到放置目标上，就会触发dragenter事件       
    
dragover:
    dragenter紧随其后的就是dragover事件，而且在被拖动的元素还在放置目标的范围内移动时，就会持续触发该事件。
    
dragleave:元素被拖出了放置目标，会触发dragleave

drop:将拖动元素放置到目标元素上的时候会激发

**5, 完整事件流**   
从开始拖动元素到放置元素到目标区域，将会按照如下顺序依次触发

dragstart->drag->dragenter->dragover->dragleave->drop->dragend

**6. 解决firefox对拖拽不支持的问题**

如果我们直接给一个元素添加draggable属性，在chrome，opera中是可以直接进行拖拽（没有可以释放的操作（比如箭头变+号）），但是在firefox却没有反应
```
    <ul class="canDrog">
        <li draggable="true" id="1">优</li>
        <li draggable="true" id="2">良</li>
        <li draggable="true" id="3">中</li>
        <li draggable="true" id="4">差</li>
    </ul>
    <script>
        //没有任何JS代码
    </script>
```
要解决这个问题必须为拖拽元素绑定dragstart事件处理函数，并且在该函数中调用event.dataTransfer.setData函数
```
<script>
     <ul class="canDrog">
        <li draggable="true" id="1">优</li>
        <li draggable="true" id="2">良</li>
        <li draggable="true" id="3">中</li>
        <li draggable="true" id="4">差</li>
    </ul>
    $('.canDrog > li').bind('dragstart',function(event){
        //firefox 必须访问用于拖拽通信的dataTransfer对象
        event.dataTransfer.setData("Text",'1');
    });
</script>
```
**7、text-shadow属性的使用方法**    
简介：在css3我们可以使用text-shadow属性给页面上的文字添加阴影效果    
text-shadow:length length length color  
第一个length表示的是阴影离开文字的横方向距离    
第二个length表示的是阴影离开文字的纵方向距离    
第三个length表示的是阴影模糊半径    
**7.1位移距离**     
text-shadow所使用的参数中，前两个参数是阴影离开文字的横方向和纵方向的位移距离，使用的时候必须指定这两个参    
**7.2阴影的模糊半径**   
text-shadow属性的第三个参数就是阴影模糊半径，代表阴影向外模糊时的模糊范围  
**7.3阴影的颜色**   
text-shadow属性的第四个参数就是绘制阴影时所使用的颜色，可以放在三个参数之前，也可以放在之后。当没有指定颜色值的时候，会使用colo色值。    
**7.4指定多个阴影**     
我们可以使用text-shadow属性来给文字指定多个阴影，并且针对每个阴影使用不同的颜色，指定多个阴影的时候使用逗号，将多个阴影进行分割
例子：
```
  h1{
             
             text-shadow:10px 15px 3px red;
         }
        h2{
           
            text-shadow:10px 15px 3px;
        }
        h3{
           
            text-shadow:10px 15px 3px,20px 25px 3px red;
        }
```
**8、word-break属性的使用方法**     

简介：在css3中可以使用word-break属性来设置自动换行的处理方法。  
word-break：normal 使用浏览器默认的规则  适用IE5 safari chrome   
word-break：keep-all     只能在半角空格或连字符处理换行 适用IE5  
word-break：break-all    允许在单词内换行适用IE5  safari chrome  
**9、word-wrap属性的使用方法**  
简介：在css3中，使用word-wrap属性来实现长单词和URL的自动换行。   
word-wrap：normal    浏览器保持默认处理方式，只在半角空格或者是连字符的地方换行  
word-wrap：break-word    浏览器可以在长单词或URL地址内部进行换行