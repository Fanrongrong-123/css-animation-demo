# CSS 知识总结

## 浏览器的渲染原理：

    1. 根据HTML构建html（DOM）
    2. 根据css构建css树（CSSOM）
    3. 将两棵树合并成一棵树（render tree）
    4. layout布局（文档流、盒模型、计算大小和位置）
    5. paint绘制（把边框颜色、文字颜色、阴影等画出来）
    6. composite合成（根据层叠关系展示画面）

## CSS 动画的两种做法

一、transition（过渡）

作用：添加、补充中间帧

     语法：
     transition：属性名、时长、过渡方式、延迟
     例：transition：all 3s linear 2s;(一一对应)
     all:代表所有属性
     height:代表只作用于高度的过渡
     时长可以是S秒或者ms毫秒

     可以用逗号分隔两个不同的属性
     例：transition：height 3s, width 2s
     代表高度的过渡用3秒，宽度的过渡用两秒

     过渡方式：linear(匀速)|ease(默认)|ease-in(淡入)|ease-out(淡出)|ease-in-out(淡入淡出)等

     color颜色(背景色、字体颜色)和opacity(透明度)可以过渡
     
     注意：不能过渡的属性
     display:none=>block(一般用:visibility:hidden=>visible)

     display和visibility的区别：前者设置元素的浮动特征，后者隐藏元素但保持元素的浮动特征

二、animation（实现多次动画）

作用：声明关键帧、添加动画（与@keyframes xxx配合使用）

    语法：
    animation:时长、过渡方式、延迟、次数、方向、填充模式、是否暂停动画、动画名
    例:animation: 2s linear 3s infinite（无限） alternate（交替） xxx（动画名）;

    时长可以是S秒或者ms毫秒

    过渡方式与transition的取值一样，如：linear

    方向：reverse|alternate|alter-reverse

    填充模式：none|forwards|backwards|both

    是否暂停：paused|running

@keyframes 用法

    例：
    @keyframes xxx{
        0{transform:none;}
        50%{transform:translateX(40px);}
        100%{transform:translate(40px,50px);}
    }

    例：
    @keyframes xxx{
        from {(transform:none;)}
        to{transform:translateX(40px);}
    }


绝对居中的写法
 
     left:50%;
     right:50%;
     transform:translate(-50%,-50%);






