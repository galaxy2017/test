<!--# CSS-->

## 一、CSS3 浏览器支持情况

​		网址查询：caniuse.com



## 二、CSS3的伪类选择器

### 2.1 动态伪类选器 

​	      

```css
a:link{}
a:visited{}
a:hover{}
a:active{}
```



### 2.2 UI元素状态伪类选择器

​		html部分：

​				

```html
<input type="text">

<input type="text" disable>     // disable 是状态
```

​		CSS部分：（根据状态确定样式）

​				

```css
input :enable{}
input:disable{}
```



### 2.3 结构伪类选择器

​			html部分：

```html
				<ul>
                    <li a href=""></li>
                    <li a href=""></li>
                    <li a href=""></li>
                    <li a href=""></li>
                    <li a href=""></li>
                    <li a href=""></li>
                    <li a href=""></li>
                    
				</ul>
```
​		

​			css部分

```css
			li:fist-child{}    元素的第一个子元素选中
			li:last-child{}		元素的最后一个子元素选中
			li:nth-child(****){}    选中顺序从左往右
				li:nth-child(2n){}  元素的第偶数个子元素选中
				li:nth-child(2n+1){}  元素的第奇数个子元素选中
				li:nth-child(n+5){}  元素从第5个子元素开始选中
				li:nth-child(4n+1){}  元素每4个元素选中

			li:nth-last-child(){}     选中顺序从右往左
			li:nth-of-type(){}     限定是li标签的子元素 从前往后
			li:nth-last-of-type{}    从后往前
			li:fist-of-type{}    限定是第一个li标签子元素
			li:last-of-type{}    限定是最后一个li标签子元素
			li:only-child{}      选择的元素是它父元素只有一个子元素
			li:only-of-type{}    选择的元素是它父元素只有一个子元素，但是限制子元素的标签类型为li
			li:empty{} 				选中的li标签父元素是空的

```





## 三、伪元素

html:

```html
<div class="demo">
    <p></p>
</div>
```

css:   

```css
.demo::first-letter{}   文本段落首字
.demo::first-line{}    文本段落首行


.demo::before{   //demo之前
    content:;     //伪元素的content属性必须要有，不设置也要有，留空
}   


.demo::after{   //demo之后
     content:;
}		
```



## 四、border-radius案例

html:

```html
<div class="demo">
    
</div>
```

css:

```css
.demo{
    width:200px;
    heigth:200px;
    border:1px solid #ccc;
    background-color:#f66;
    margin:50px auto;
    border-radius:50%;     //   border-radius: 50%  50%  50%  50%;
}


画一个半圆
.demo{
    width:200px;
    heigth:200px;
    border:1px solid #ccc;
    background-color:#f66;
    margin:50px auto;
    border-radius:100px 0 0 100px;
}


```



## 五、各种画画案例



### 5.1 画三角形和对话框案例

html

```html
<div class="sanjiao">
    
</div>
```

css

```css
.sanjiao{
    border-top:50px solid #ccc;
    border-top:50px solid #f00;
    border-top:50px solid #0f0;
    border-top:50px solid #00f;
    
    
    border:50px solid #ccc;
    width:0px;
    heigth:0;
    margin:50px auto;
}
```

![image-20220127104147813](https://img.cdn.luomoe.com/typora-user-images/image-20220127104147813.png)





```css
.sanjiao{
    border-left:50px solid #ccc;
    border-top:50px solid transparent;
    border-bottom:50px solid transparent;
    border-right:50px solid transparent;
    
    
    border:50px solid #ccc;
    width:0px;
    heigth:0;
    margin:50px auto;
}
```

![image-20220127104429084](https://img.cdn.luomoe.com/typora-user-images/image-20220127104429084.png)



做一个对话框：

```html
<div class="dialog">
    hello word
</div>
```

```css
.dialog{
    background-color: #6a6;
    margin:50px auto;
    width:300px;
    heigth:25px;
    line-heigth:25px;
    padding:10px;
    boder-radius:6px;
    color:#fff;   
    
}

.dialog::before{
    content:'';
    border-left:0px solid #6a6;
    border-top:50px solid transparent;
    border-bottom:50px solid transparent;
    border-right:50px solid #6a6;
    position:absolute;   //绝对定位
    left:-10px;
    top:14px;
}
```





### 5.2 画菱形和平行四边形

```html
<div class="diamond">

</div>


<div class="parallel">

</div>
```

```css
.diamond{
    background-color: #6a6;
    margin:50px auto;
    width:300px;
    heigth:25px;
    transform:rotate(45deg);
}

.parallel{
    background-color: #6a6;
    margin:50px auto;
    width:300px;
    heigth:25px;
    transform:skew(20edg;0);    x轴倾斜，y轴倾斜，可以只X轴或者只y轴倾斜
}
```





### 5.3 画五角星、六角星

```html
<div id="start">
    
</div>>

<div id="start2">
    
</div>>
```

```css
#start{
    width:0;
    height:0;
    border-bottom:70px solid red;
    border-left:100px solid transparent;
    order-right:100px solid transparent;
    margin:150px auto;
    transfrom: rotoute(35deg);
    position:relative;
}

#start::before{
    content:'';
    width:0;
    height:0;
    border-bottom:80px solid red;
    border-left:30px solid transparent;
    order-right:30px solid transparent;
    margin:150px auto;
    transfrom: rotoute(-35deg);
    position:absolute;
    top:-45px;
    left:-65px;
}

#start::after{
    content:'';
    border-bottom:70px solid red;
    border-left:100px solid transparent;
    order-right:100px solid transparent;
    margin:150px auto;
    position:absolute;
    transfrom: rotoute(-70deg);
     top:3px;
    left:-105px;
}



#start2{
    width:0;
    height:0;
    border-bottom:100px solid red;
    border-left:50px solid transparent;
    order-right:50px solid transparent;
    margin:100px auto;
    position:relative;
}

#start2::after{
    content:'';
    width:0;
    height:0;
    border-top:100px solid red;
    border-left:50px solid transparent;
    order-right:50px solid transparent;
    margin:100px auto;
    position:absolute;
     top:30px;
    left:-50px;
    
}
```





### 5.4 画五边形和六边形

```html
<div id="zheng">   //画一个梯形
    
</div>


<div id="wubian">   //画一个五边形   一个三角形+一个梯形
    
</div>



<div id="six">   //画一个六边形   一个长方形+2个三角形
    
</div>
```

```css
#zheng{
    width:50px;
    height:50px;
    border-top:100px solid red;
    border-left:50px solid green;
    order-right:50px solid blue;
    order-bottom:50px solid yellow;
}


#wubian{
    width:54px;
    height:0;
    border-top:50px solid red;
    border-left:18px solid transparent;
    order-right:18px solid transparent;
    margin:100px auto;
    position:relative;
}

#wubian::after{
	content:'';
    width:0;
    height:0;
    border-bottom:35px solid red;
    border-left:45px solid transparent;
    order-right:45px solid transparent;
    position:absolute;
    top:-85px;
    left:-18px
}

#six{
    margin:100px auto;
    width:100px;
    height:55px;
    background-color:red;
    position:relative;
}

#six::before{
    content:'';
    width:0;
    height:0;
    border-bottom:25px solid red;
    border-left:50px solid transparent;
    order-right:50px solid transparent;
    position:absolute;
    top:-25px;
    left:-18px
}

#six::after{
    content:'';
    width:0;
    height:0;
    border-top:25px solid red;
    border-left:50px solid transparent;
    order-right:50px solid transparent;
    position:absolute;
    top:55px;
    left:-18px
}
```



### 5.5 画心形和蛋形

画心

```html
<div id="heart"></div>
```

```css
#heart{
    width:100px;
    height:90px;
    position:relative;
    margin:100px auto;
    background-color:#FF0;
}
#heart::before{
    content:'';
    position:absolute;
    width:50px;
    height:80px;
    background-color:red;
    border-radius:50px 40px 0 0;
    transform-origin:0 100%;    /* 设置旋转原点，定位*/
    teansform:rotate(-45deg);
    left:50px;
}
#heart::before{
    content:'';
    position:absolute;
    width:50px;
    height:80px;
    background-color:red;
    border-radius:50px 40px 0 0;
    transform-origin:100% 100%;    /* 设置旋转原点，定位*/
    teansform:rotate(45deg);    
}
```

画蛋形：

```
<div id="heart"></div>
```

```css
#egg{
    width:126px;
    height:180px;
    background-color:#FA3;
    border-radius:50% 50% 50% 50% / 60% 60% 40% 40%;
}
```





### 5.6 画太极阴阳图

```html
<div id="taiji"></div>
```

```css
body{
    background-color:#ccc;
}
#taiji{
    width:150px;
    height:300px;
    margin:100px;
    border-radius:50%;
    background-color:white;
    border-left:150px solid black;
}
#taiji::before{
    content:'';
    position:absolute;
    width:0px;
    height:0px;
    padding:25px;
    border-radius:50%;
    border:50px solid black;
    background-color:white;
    left:-75px;
    top:0;
}
#taiji::after{
    content:'';
    position:absolute;
    width:0px;
    height:0px;
    padding:25px;
    border-radius:50%;
    border:50px solid white;
    background-color:black;
    left:-75px;
    bottom:0px;
}
```



## 六、CSS3制作透明背景层

（背景半透明、圆角、阴影）

```html
<div id="background" >
    <div id="content"></div>
</div>
```

```css
#background{
    margin:100px auto;
    width:800px;
    height:291px;
    background-imge:url(./back_img.jpg)
}

#content{
    position:absolute;
    width:400px;
    height:200px;
    background-color: #fff;
    opacity: 0.8;       /*透明度 只用在背景设置上，色块用rgba设置的更多*/
    top:45px;
    left:200px;
    border-radius:10px;
    padding:10px;
    text-aligin:center;
    box-shadow:3px 3px 5px #888;
}
```



## 七、CSS3的颜色模式

1. rgba(R,G,B,A)      其中的A是透明度
2. hsla(H,S,L,A)  少用





仿天猫商品展示

```html
<div class="main">
        <ul>
            <li>
                <div class="img">
                    <img src="./goods.jpg" alt="新品九阳不用手洗破壁机静音料理全自动">
                </div>
                <div class="goods_title">新品九阳不用手洗破壁机静音料理全自动</div>
                <div class="price">3599.0</div>
            </li>
            <li>
                <div class="img">
                    <img src="./goods.jpg" alt="新品九阳不用手洗破壁机静音料理全自动">
                </div>
                <div class="goods_title">新品九阳不用手洗破壁机静音料理全自动</div>
                <div class="price">3599.0</div>
            </li>
        </ul>
    </div>
```

```css
body {
    background: #ddd
}

.main {
    width: 900px;
    height: auto;
    margin: 90px auto;
}

.main ul {
    clear: both;
}

.main li {
    list-style: none;
    float: left;
    margin-right: 10px;
    width: 240px;
    padding: 1px;
    border: 1px solid rgba(255, 0, 0, 0);
    background: #fff
}

.main li:hover {
    border: 1px solid rgba(255, 0, 0, 1);
}

.img img {
    width: 240px;
    transition: all .6s;     /*过渡 */
}

.main li:hover img{
    opacity: .7;      /*半透明程度 */
}

.goods_title {
    font-size: 14px;
    color: #666;
    line-height: 18px;
    margin: 10px;
    height: 35px;
    overflow: hidden;
}

.price {
    font-size: 18px;
    color: #ff0036;
}

.price::before {
    content: '￥'
}
```



## 八、渐变

### 8.1 线性渐变：linear-gradient

linear-gradient(  <point> ||  <angle> ,]?  <stop>, <stop>[,<stop>]*    )

<angle>:用角度指定渐变方向或者角度

to left

to right

to top

to bottom

```html
<div class='ceng'>
    
</div>
```

```css
.ceng{
    width:260px;
    height:200px;
    border:1px solid black;
    
    
    background-image:linear-gradient(orange,green);    /*从橘红色向绿色渐变，从上到下*/
    background-image:linear-gradient(to top,orange,green);    /*从橘红色向绿色渐变，从下到上*/
    background-image:linear-gradient(to left,orange 30%,green 60%, red 100%);    /*从橘红色向绿色渐变，从左到右 30% 、60%、100%渐变，也可以变为30px,60px,100px这些类似的数字 */
    background-image:linear-gradient(180edg,orange,green);    /*从橘红色向绿色渐变，角度旋转*/
    

    
}
```



### 8.2 径向渐变

![image-20220505171000830](https://img.cdn.luomoe.com/typora-user-images/image-20220505171000830.png)

radio

```html
<div class="ceng circle">    </div>

<div class="ceng ellipse">    </div>
```

```css
.ceng{
    width:100px;
    height:100px;
    border:1px solid black;
    border-radius: 50%;
    margin:10px;
    margin:left;
}
.circle{
    background-image: radial-gradient(circle at center orange,green);      //默认circle at center，也就是不用写
	background-image: radial-gradient(20px circle at center,orange,green);    //从中间渐变20px,百分数不行
    background-image: radial-gradient(circle at center,orange,green，red);  //多色彩渐变，也可以加上方向和长度
}

.ellipse{
    background-image: radial-gradient(ellipse at center,orange,green);
    background-image: radial-gradient(ellipse at right,orange,green);     //右渐变
    background-image: radial-gradient(ellipse at top,orange,green);       //从顶渐变
    background-image: radial-gradient(ellipse at top right,orange,green);    //从右上渐变
    background-image: radial-gradient(50px 20px ellipse at center,orange,green);    //从x方向渐变50px,y方向20px,百分数不行

    background-image: radial-gradient(ellipse at center,orange,green，red);  //多色彩渐变，也可以加上方向和长度

}
```



### 8.3 重复性渐变

![image-20220507165857769](https://img.cdn.luomoe.com/typora-user-images/image-20220507165857769.png)

```html
<div class="linear">   
</div>
<div class="circle">
    
</div>
```

```css
.linear{
    width:300px;
    height:300px;
    margin:20px auto;
    background-image:repeating-linear-gradient(red 0px,green 40px,orange 80px)    //重复渐变,要设置色标值
}

.circle{
    width:300px;
    height:300px;
    margin:20px auto;
    border-radius:50%;
    background-image:repeating-linear-gradient(red 0px,green 30px,orange 40px)
}
```





## 九、盒子阴影效果box-shadow

box-shadow: h-shadow v-shadow blur spread color inset

h-shadow 必须。水平阴影半径的位置，允许负值

v-shadow 必须。垂直半径阴影

blur 可选，模糊半径设置

color 可选，阴影颜色

inset  可选，内阴影

```html
<div class="ceng  rotate_left">
    <img src='yjx.jpg' alt=''>
    <p>
        上海鲜花港的郁金香，花名未闻
    </p>
</div>

<div class="ceng rotate_right">
    <img src='zgg.png' alt=''>
    <p>
        2010年世博会，中国馆
    </p>
</div>
```

```css
body{
    background-color:#e9e9e9
}
.ceng{
    width:294px;
    padding:10px 10px 20px 10px;
    border:1px solid #BFBFBF;
    background-color:white;
    box-shadow: 2px 2px 20px #aaa;
}

.rotate_left{
    flat:left;
    transform:rote(7deg)
}


.rotate_right{
    flat:left;
    transform:rote(-8deg)
}
```



## 十、制作缓慢变长的长方形（transition特效）

transition-property  过渡属性，默认值为all

transition-duration  过渡持续时间，默认时间为0s

transition-timing-function  过渡函数，默认ease函数，还有ease-out（先快后慢）、ease-in（先慢后快）、linear（匀速）等等函数

transition-delay    过渡延迟时间，默认0s

```html
<div class="ceng">
    
</div>
```

```css
.ceng{
    width:100px;
    height:100px;
    background-color:pink;
    cursor:pointer;
    transition-duration:2s;
    transition-property:height;      //指定方向，默认all，即所有方向都变化
    transition-delay:.1s;
    transition-timing-function:ease;
    transition:all 2s .1s ease;    //transition 的复合写法
}
.ceng:hover{
    width:300px;
    height:150px;
    background-color:red;
/*    border-radius:50%;*/    //圆形也可以变化，正方形变成圆形
        
}
```



### 10.1 仿天猫专题过渡效果实例

```html
<div class="main">
    <ul>
        <li>
            <div class="m_title">
                手机馆
            </div>
            <div class='m_content'>
                R9s Plus最新上线
            </div>
            <div class="m_img">
                <img src="./r9s,jpg" alt="手机">
            </div>
        </li>
    </ul>
    
</div>
```

```css
*{
    padding:0px;
    margin:0px;
    front-family:'Microshoft YaHei';
}
.main{
    margin:10px auto;
    width:230px;
    border:1px solid #ccc;
    text-align:center;
}
.main li{
    list-style:none;
    cursor:pointer;   //鼠标三角形状变成手形
}
.m_title{
    front-size:20px;
    font-weight:bold;
    margin:5px;
}
m.content{
    color:#666;
    margin-bottom:15px;
}
.m_img{
    position:relative;
    padding:30px;
}
.m_img::before{     //伪元素
    content:"";
    position:absolute;
    width:160px;
    height:160px;
    background-color:#eee;
    border-radius:50%;
    z-index:-1;
    left:35px;
    top:10px;
}
.m_img img{
    transform:scale(1);
    transition:all .5s; 
}
.main li:hover .m_img img{
    transform:scale(1);
}
```





### 10.2 仿天猫首页类别展示的效果

```html
<div class="main">
    <div class="m_title">
        好车特卖一口价
    </div>
    <div class="m_content">
        新车 新年 开回家
    </div>
    <div class="m_img">
        <img src="./car.jpg" alt="新车特卖">
    </div>
</div>
```

```css
.main{
    width:260px;
    height:270px;
    border:1px; solid #ccc;
    margin:50px auto;
    front-family:'Microshoft YaHei';
    cursor:pointer;
}
.m_title{
    text-align:left;
    font-size:20px;
    padding:20px 10px 10px 10px;
}
.m_content{
    color:#11ccaa;
    padding:0 10px 10px 10px;
}
.m_img{
    text-align:right;
    position:relative;   //相对定位
}
.m_img img{
        position:absolute;   //绝对定位
		width:180px;
    	top:0px;
    	right:0px;
        teansition:right 0.3s;
}
.mail:hover img{
    right:10px;
}
```





## 十一、css3动画

### 11.1    @keyframes关键帧

```html
<div class="rect">
    
</div>
```

```css
.rect{
    width:100px;
    height:100px;
    background-color:red;
    position:flexde;
    animation: mymove 2s infinite;
}
@keyframes mymove{      //方法一   首帧和尾帧
    from{
        top:0;
        left:20%;
    }
    to{
        top:0;
        left:80%;
    }
}

@keyframes mymove{      //方法二   动画的不同阶段
    0%{
        top:0;
        left:20%;
        background-color:blue;
    }
    25%{
        top:0;
        left:80%;
        background-colorr:green;
    }
    50%{
        top:80%;
        left:80%;
        background-color:black;
    }
    75%{
        top:80%;
        left:20%;
        background-color:yello;
    }
    100%{
        top:0;
        left:20%;
        background-color:red;
    }
}
```



### 11.2 animation符合属性



animation-name:    指定使用哪一个动画

animation-duration:    动画运行的时间

animation-timing-function:      linear; 匀速

​														ease ;  两头快，中间慢

​														ease-in-out、ease-in、ease-out

animation-delay:    延迟

animation-iteration-count:     循环次数；infinite  无限循环

animation-direction:            normal 默认；alternate 动画反方向播放



复合写：

animation：mymove 3s 3;



## 十二、 综合实例

![image-20220507200952799](https://img.cdn.luomoe.com/typora-user-images/image-20220507200952799.png)

![image-20220507201004746](https://img.cdn.luomoe.com/typora-user-images/image-20220507201004746.png)

### 12.1 Loading动画效果实例(一)

```html
<div class="spinner">
    <div>   </div>
    <div>   </div>
    <div>   </div>
    <div>   </div>
    <div>   </div>
</div>
```

```css
.spinner{
    margin:100px auto;
    width:50px;
    height:60px;
    text-align:center;
    font-size: 10px;
}
.spinner > div{
    background-color:#67CF22;
    height:100%;
    width:6px;
    display:inline-block;
    animation: mymove 1.2 infinite ease-out
}
.spinner >div:nth-child(2){
    animation-delay: -1.1s;
}
.spinner >div:nth-child(3){
    animation-delay: -1.0s;
}
.spinner >div:nth-child(4){
    animation-delay: -0.9s;
}
.spinner >div:nth-child(5){
    animation-delay: -0.8s;
}

@keyframes mymove{
    0%,40%,100%{
        transform:scaleY(0.4);
    }
    20%{
        transform:scaleY(1)
    }
}
```





### 12.2 Loading动画效果实例(二)

![image-20220507202332002](https://img.cdn.luomoe.com/typora-user-images/image-20220507202332002.png)



![image-20220507202346830](https://img.cdn.luomoe.com/typora-user-images/image-20220507202346830.png)

```html
<div class="spinner">
    <div>   </div>
    <div>   </div>    
</div>
```

```css
.spinner{
    width:60px;
    height:60px;
    position:relative;
    margin:100px auto;
}

.spinner > div{
    width:100%;
    height:100%;
    background-color:#67CF22;
    border-radius:50%;
    opacity:0.6;
    position:absolute;
    top:0;
    left:0;
    animation:mya 2s infinite ease-out;
}

.spinner > div:nth-child(2){
    animation-delay:-1s;      //尽量用负值，打开的时候不会出现卡顿
}

@keyframes mya{
    0%,100%{
        transform:scale(0.0);
    }
    50%{
        transform:scale(1.0);
    }
}
```





### 12.3制作发光字、立体字、苹果字体

text-shadow:  h-shadow   v-shadow blur color;



![image-20220507203440745](https://img.cdn.luomoe.com/typora-user-images/image-20220507203440745.png)

```html
<div>
    <div class="font1">
        Pandar
    </div>
    <div class="font2">
        APPLE STYLE
    </div>
    <div class="font3">
        3D TEXT EFFECT
    </div>
    
</div>
```

```css
.body{
    background-color:#666;
    text-align:center;
    font:bild 55px "Microsoft YaHei";
}
.font1{
    color:#fff;
    text-shadow:0px 0px 20px red;
}
.font2{
    color:#000;
    text-shadow:0px 1px 1px #fff;
}
.font3{
    color:#fff;
    text-shadow:1px 1px rgba(197,223,248,0.8),
        		2px 2px rgba(197,223,248,0.8),
       			3px 3px rgba(197,223,248,0.8),
        		4px 4px rgba(197,223,248,0.8),
        		5px 5px rgba(197,223,248,0.8),
        		6px 6px rgba(197,223,248,0.8);
}
```



### 12.4 用text-overflow解决文字排版

当文本超过一定的范围变为    ...

text-overflow: clip    ellipsis    string

常用ellipsis    

```html
<div class="demo">
稳字当头稳中求进 全力以赴实现“平安高考”,2022年全国普通高校招生考试安全工作电视电话会议召开。
</div>
<div class="demo1">
稳字当头稳中求进 全力以赴实现“平安高考”,2022年全国普通高校招生考试安全工作电视电话会议召开。
</div>
```

```css
.demo{
    margin:30px auto;
    width:100px;
    padding:10px;
    border:1px solid #ccc;
    height:50px;
    text-overflow:clip;
    overflow:hidden;
}
.demo1{
    margin:0px auto;
    width:100px;
    padding:10px;
    border:1px solid #ccc;
    text-overflow:ellisis;
    overflow:hidden;		//搭配使用，才能出现效果
    white-space:nowrap;   //强制不换行，搭配使用
}
```



## 十三、新的字体单位：rem

px:像素

em: 父级的字体的缩放，跟终端有关

rem:更具根的单位进行换算

```html
<div>Hello world</div>
<h1>Hello world</h1>
```

```css
html{
    font-size:10px;     //定义根单位
    font-size:62.5%;    //这个定义会更加常用
}
body{
    font-size:1.4rem;   //  10*1.4=14px
}
```

