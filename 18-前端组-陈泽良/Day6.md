# CSS基础入门
## 一、复习
盒模型box model，什么是盒子？所有的标签都是盒子。无论是div、span、a都是盒子。图片、表单元素一律看做文本。  
盒模型有哪些组成：width、height、padding、border、margin。  
width、height是内容的宽度、高度，想起来丈量包子的比喻、丈量稿纸的比喻。       
padding，内边距，边框和文字内容之间的距离。padding有颜色。表示方法，能够用padding综合写，4个值“上、右、下、左”，3个值“上、左右、下”，2个值“上下，左右”。还能按方向拆开，padding-left、padding-top、padding-right、padding-bottom。    
border，边框，3要素，4条边。3要素：border-width、border-style、border-color；4条边：border-top、border-right、border-bottom、border-left。  
## 二、浮动性质的复习
浮动的性质：脱标、贴边、字围、收缩。    
收缩：一个浮动的元素，如果没有设置width，那么将自动收缩为文字的宽度（这点非常像行内元素）。
比如：
```
1		<style type="text/css">
2			div{
3				float: left;
4				background-color: gold;
5			}
6		</style>
```
这个div浮动了，且没有设置宽度，那么将自动缩紧为内容的宽.
## 三、浮动的清除
**3.1 清除浮动方法1：给浮动的元素的祖先元素加高度。**  
如果一个元素要浮动，那么它的祖先元素一定要有高度。高度的盒子，才能关住浮动。    
**3.2 清除浮动方法2：clear:both;**  
clear就是清除，both指的是左浮动、右浮动都要清除。意思就是：清除别人对我的影响。    
这种方法有一个非常大的、致命的问题，margin失效了。  
**3.3 清除浮动方法3：隔墙法**   
**3.4 清除浮动方法4：overflow:hidden**  
overflow就是“溢出”的意思， hidden就是“隐藏”的意思。    
overflow:hidden;    表示“溢出隐藏”。所有溢出边框的内容，都要隐藏掉。    
**3.5 浏览器兼容问题**  
上述知识点遇见的浏览器兼容问题
第一，IE6，不支持小于12px的盒子，任何小于12px的盒子，在IE6中看都大
解决办法很简单，就是将盒子的字号，设置小（小于盒子的高），比如0px。 
## 四、margin
**4.1 margin的塌陷现象**    
标准文档流中，竖直方向的margin不叠加，以较大的为准.     
**4.2 盒子居中margin:0 auto;**  
margin的值可以为auto，表示自动。当left、right两个方向，都是auto的时候，盒子居中了：
```
1	margin-left: auto;
2	margin-right: auto;

简写为
1	margin:0 auto;
``` 
**注意**    
1） 使用margin:0 auto; 的盒子，必须有width，有明确的width  
2） 只有标准流的盒子，才能使用margin:0 auto; 居中。 
也就是说，当一个盒子浮动了、绝对定位了、固定定位了，都不能使用margin:0 auto;   
3） margin:0 auto;是在居中盒子，不是居中文本。
文本的居中，要使用text-align:center;     
**4.3 善于使用父亲的padding，而不是儿子的margin**  
margin这个属性，本质上描述的是兄弟和兄弟之间的距离；最好不要用这个marign表达父子之间的距离。所以，我们一定要善于使用父亲的padding，而不是儿子的margin。  
**4.4 关于margin的IE6兼容问题**         
IE6双倍margin bug   
当出现连续浮动的元素，携带和浮动方向相同的margin时，队首的元素，会双倍marign。




