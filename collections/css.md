### calc, @supports, @media各自的含义及用法？  
@supports 用来检测浏览器是否支持css中某个属性，当支持时，使用@supports的{}括号中的样式，@supports相当于IF语句

calc函数用来动态计算css的属性值，只能使用加减乘除，可以使用小括号改变计算顺序，也可以使用不同单位的值进行运算

@media媒体查询，当且仅当指定的条件与正在使用内容的设备匹配时，@media的{}括号中的css样式才生效

### css水平、垂直居中的写法，请至少写出4种？  
#### 水平居中
text-align: center;

position: absolute;left: 50%;transform: translateX(-50%);

margin: 0 auto;

display: flex;justify-content: center;

也可以用栅格布局,display: grid;justify-items: center;

#### 垂直居中  
line-height: 盒子高度

position: absolute;top: 50%;transform: translateY(-50%);

display: flex;align-items: center;

display: grid;align-items: center;

另一种(不推荐)，display: table-cell;vertical-align: middle;

### 1rem、1em、1vh、1px各自代表的含义？
1rem等于在html中设置的font-size大小

字体的1em等于其父元素设置的字体大小，而width、height、padding、margin的1em等于当前元素设置的字体大小

1vh等于当前视口高度的1%，1vw等于当前视口宽度的1%

1px其值等于当前显示器分辨率的1px

### 说一下盒模型？
> 盒模型包括：content、padding、border、margin

盒子模型分为2类：
1. 标准盒子模型：遵循w3c规范，盒子实际宽高 = content + padding + border
2. 怪异盒子模型：遵循ie规范，盒子实际宽高 = content，而padding和border的大小包含在content中

box-sizing改变盒子模型：

标准盒子模型(默认)：box-sizing: content-box;

怪异盒子模型：box-sizing: border-box;

### 画一个三角形？
按border为0的条数分三类画法

#### border为0的条数：1(可画等边三角形)
```html:5
<style>
/*等边三角形*/
div{
    width: 0;
    border: solid 100px transparent;
    border-top: 0;
    border-bottom: solid 141.5px red;
}
</style>
<body>
<div></div>
</body>
```

#### border为0的条数：2(可画直角三角形，注意这时，border为0的边必须相邻)
```html:5
<style>
/*直角三角形*/
div{
    width: 0;
    border: 0;
    border-top: solid 50px transparent;
    border-left: solid 50px red;
}
</style>
<body>
<div></div>
</body>
```

#### border为0的条数：0(这个最浪费空间,可画等边三角形和直角三角形)
```html:5
<style>
/*直角三角形*/
div{
    width: 0;
    border: solid 50px transparent;
    border-left-color: red;
    border-bottom-color: red;
}
/*等边三角形*/
div{
    width: 0;
    border-left: solid 25px transparent;
    border-right: solid 25px transparent;
    border-top: solid 35.35px transparent;
    border-bottom: solid 35.35px red;

}
</style>
<body>
<div></div>
</body>
```


