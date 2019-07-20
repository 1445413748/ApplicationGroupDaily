# CSS基础入门
## 一、复习`
a标签的伪类4个：    
a:link	没有被点击过的链接  
a:visited	访问过的链接    
a:hover	悬停    
a:active	按下鼠标不松手  
顺序就是“love hate”准则。
可以简写：
```
1	a{
2		
3	}
4	a:hover{
5		
6	}
```
background系列属性，CSS2.1层面  
1	background-color    
2	background-image    
3	background-repeat   
4	background-position 
5	background-attachment   
```
background-color:red;
```
颜色表示法：red、rgb(255,0,0)、#ff0000、#f00,rgb和十六进制颜色是一样多的，是一一对应的。有换算关系。
```
background-image:url(images/1.jpg);
```
默认是平铺的。
```
background-repeat:no-repeat;
```
重复横向： repeat-x;    
重复纵向： repeat-y;    
不重复：	no-repeat;  

```
background-position:100px 200px;
```
背景图在盒子中右边移动100px，向下移动200px。       
可以是负数，background-position:-100px -200px;向左边100px，向上边200px。    
英语单词来表示
background-position:right bottom; 右下角  
background-position:center bottom; 下边居中    
## 二、相对定位
定位有三种，分别是相对定位、绝对定位、固定定位。
```
//相对定位：  
1	position:relative;
//绝对定位：  
1	position:absolute;
//固定定位：  
1	position:fixed; 
``` 
**2.1 认识相对定位**    
相对定位，就是微调元素位置的。让元素相对自己原来的位置，进行位置调整。  
也就是说，如果一个盒子想进行位置调整，那么就要使用相对定位  
```
1	position:relative;   //→ 必须先声明，自己要相对定位了，
2	left:100px;       //→ 然后进行调整。
3	top:150px;       //→ 然后进行调整。
``` 
**2.2 不脱标，老家留坑，形影分离**
相对定位不脱标，真实位置是在老家，只不过影子出去了，可以到处飘。    
**2.3 相对定位用途**    
相对定位有坑，所以一般不用于做“压盖”效果。页面中，效果极小。就两个作用：    
1） 微调元素    
2） 做绝对定位的参考，子绝父相  
**2.4 相对定位的定位值**    
可以用left、right来描述盒子右、左的移动；可以用top、bottom来描述盒子的下、上的移动。
```
1	position: relative;
2	top: 10px;
3	left: 40px;
``` 
## 三、绝对定位
**3.1 绝对定位脱标**
绝对定位的盒子，是脱离标准文档流的。所以，所有的标准文档流的性质，绝对定位之后都不遵守了。  
绝对定位之后，标签就不区分所谓的行内元素、块级元素了，不需要display:block;就可以设置宽、高了：  
```
1			span{
2				position: absolute;
3				top: 100px;
4				left: 100px;
5				width: 100px;
6				height: 100px;
7				background-color: pink;
8			}
```
**3.2绝对定位的盒子居中**   

绝对定位之后，所有标准流的规则，都不适用了。所以margin:0 auto;失效。  
## 四、固定定位
固定定位，就是相对浏览器窗口定位。页面如何滚动，这个盒子显示的位置不变。固定定位脱标！  
## 五、z-index
● z-index值表示谁压着谁。数值大的压盖住数值小的。  
● 只有定位了的元素，才能有z-index值。也就是说，不管相对定位、绝对定位、固定定位，都可以使用z-index值。而浮动的东西不能用。  
● z-index值没有单位，就是一个正整数。默认的z-index值是0。  
● 如果大家都没有z-index值，或者z-index值一样，那么谁写在HTML后面，谁在上面能压住别人。定位了的元素，永远能够压住没有定位的元素。    
● 从父现象：父亲怂了，儿子再牛逼也没用。  









