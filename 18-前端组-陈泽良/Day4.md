# CSS基础入门   
## css基础选择器
html负责结构，css负责样式，js负责行为。css写在head标签里面，容器style标签。先写选择器，然后写大括号，大括号里面是样式。
```
1		<style type="text/css">
2			body{
3				background-color: pink;
4			}
5		</style>
```
常见属性：
```
1			h1{
2				color:blue;
3				font-size: 60px;
4				font-weight: normal;
5				text-decoration: underline;
6				font-style: italic;
7			}
```
**1,标签选择器**    
就是用标签名来当做选择器。  
1） 所有标签都能够当做选择器，比如body、h1、dl、ul、span等等    
2） 不管这个标签藏的多深，都能够被选择上。  
3） 选择的是所有的，而不是某一个。所以是共性，而不是特性。  

**2,id选择器**  
#表示选择id
```
1			#lj1{
2				font-size: 60px;
3				font-weight: bold;
4				color:black;
5			}
```
1）任何的标签都可以有id，id的命名要以字母开头，可以有数字、下划线。大小写严格区别，也就是说mm和MM是两个不同的id。  
2）同一个页面内id不能重复，即使不一样的标签，也不能是相同的id。
也就是说，如果有一个p的id叫做haha，这个页面内，其他所有的元素的id都不能叫做haha。  
**3,类选择器**  
.就是类的符号。类的英语叫做class。
所谓的类，就是class属性，class属性和id非常相似，任何的标签都可以携带class属性。class属性可以重复，比如，页面上可能有很多标签都有teshu这个类：
```
1		<h3>我是一个h3啊</h3>
2		<h3 class="teshu">我是一个h3啊</h3>
3		<h3>我是一个h3啊</h3>
4		<p>我是一个段落啊</p>
5		<p class="teshu">我是一个段落啊</p>
6		<p class="teshu">我是一个段落啊</p>
```
css里面用.来表示类：
```
1			.teshu{
2				color: red;
3			}
```
同一个标签，可能同时属于多个类，用空格隔开：       
```
<h3 class="teshu  zhongyao">我是一个h3啊</h3>
```
这样，这个h3就同时属于teshu类，也同时属于zhongyao类。  
总结两条：  
1） class可以重复，也就是说，同一个页面上可能有多个标签同时属于某一个类；  
2） 同一个标签可以同时携带多个类。
## css高级选择器
**1,后代选择器**    
```
1		<style type="text/css">
2			.div1 p{
3				color:red;
4			}
5		</style>
```
空格就表示后代，.div1 p 就是.div1的后代所有的p。
选择的是后代，不一定是儿子。
比如：  
```
1		<div class="div1">
2			<ul>
3				<li>
4					<p>段落</p>
5					<p>段落</p>
6					<p>段落</p>
7				</li>
8			</ul>
9		</div>
```
能够被下面的选择器选择上：
```
1			.div1 p{
2				color:red;
3			}
```
所以，看见这个选择器要知道是后代，而不是儿子。选择的是所有.div1“中的”p，就是后代p。
空格可以多次出现。
```
1		 	.div1 .li2 p{
2		 		color:red;
3		 	}
```
就是.div1里面的后代.li2里面的p。
后代选择器，就是一种平衡：共性、特性的平衡。当要把某一个部分的所有的什么，进行样式改变，就要想到后代选择器。后代选择器，描述的是祖先结构。  
**2,交集选择器**    
选择的元素是同时满足两个条件：必须是h3标签，然后必须是special标签。
交集选择器没有空格。所以有没有空格div.red  
**3,并集选择器（分组选择器）**  
```
1	h3,li{
2		color:red;3	}
```
用逗号就表示并集。  
##  CSS的继承性和层叠性
**1,继承性**    
有一些属性，当给自己设置的时候，自己的后代都继承上了，这个就是继承性。哪些属性能继承？color、 text-开头的、line-开头的、font-开头的。这些关于文字样式的，都能够继承； 所有关于盒子的、定位的、布局的属性都不能继承。  
**2,层叠性**    
层叠性：就是css处理冲突的能力。 所有的权重计算，没有任何兼容问题！  
**3,权重问题大总结：**    
1） 先看有没有选中，如果选中了，那么以（id数，类数，标签数）来计权重。谁大听谁的。如果都一样，听后写的为准。  
2） 如果没有选中，那么权重是0。如果大家都是0，就近原则。

# PLUS
# 侩子手游戏    
题目：

刽子手游戏其实是一款猜单词游    
游戏规则是这样的：计算机想一个单词让你猜一个字母。如果单词里有那个字母，所有字母会显示出来；如果没有那个字母，则计算机会在一幅“刽子手”画上填一笔。这幅画一共需要7笔就能完成，因此你最多只能错六次,另外猜一个已经猜过的字母也算错。

在本题中，你的任务是编写一个“裁判程序”，输入单词和玩家的猜测，判断玩家赢了（You win.）、输了（You lose.）还是放弃了（You chickened out.）。每组数据包含3行，第一行是游戏编号（-1为输入结束标记），第2行是计算机想的单词，第3行是玩家的猜测。后两行保证只包含小写字母。    
样例输入：

1

cheese

chese

2

cheese

abcdefg

3

cheese

abcdefgij

-1

样例输出：

Round 1

You win.

Round 2

You chickened out.

Round 3

You lose.       

分析:这道题需要注意的是已经猜过的字母再猜一次就算错,所以要把单词中已经猜过的字母标记一下,可以改成空格.
```
#include<iostream>
#include<cstdio>
#include<cstring>
using namespace std;
#define maxn 100
char s[maxn],s2[maxn];
int chance,many;
int win,lose;
void guess(char ch);
int main()
{
	int n,i;
	while(cin>>n>>s>>s2 && n!=-1)
	{
		cout<<"Round "<<n<<endl;
		win=lose=0;
		many = strlen(s);
		chance = 7;
		for(i=0;i<strlen(s2);i++)
		{
		guess(s2[i]);
		if(lose || win)break;
		}
		if(win)
		cout<<"You win."<<endl;
		else if(lose)
		cout<<"You lose."<<endl;
		else 
		cout<<"You chickened out."<<endl;
	}
	return 0;
}
void guess(char ch)
{
	int flag=1;
	for(int i=0;i<strlen(s);i++)
		if(s[i]==ch)
		{
			--many;
			s[i]=' ';
			flag=0;
		}
	if(flag)
	--chance;
	if(!chance)
	lose=1;
	if(!many)
	win=1;
}
```



