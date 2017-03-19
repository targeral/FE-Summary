# CSS
This is CSS/overflow Page!
overflow默认属性：visible；
如果overflow-x或overflow-y一个值为visible，另一个不同的话，值为visible方向的值被强制设置为auto，即在此方向超出范围会有滚动条；
无论什么浏览器哦，滚动条默认来自<html>而不是<body>;
新建一个<html>的话,<body>默认有0.5em的margin值；
滚动高度： st = document.body.scrollTop || document.documentEvent.scrollTop;
除chrome浏览器以外，其他浏览器的overflow会导致padding-bottom缺失现象；
滚动条会占用浏览器的可用高度或是宽度；
除了visible外都会触发BFC；
当overflow在absolute和absolute的包含块之间的层时，overflow：hidden失效，解决方法是在overflow内的absolute块外包裹一层包含块或将自身设置为包含块，或者overflow元素设置transform属性（IE9+/FireFox）；