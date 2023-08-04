按钮大小		`font-size:数值px`
圆角设置		`border-radius:数值px`
设置字体		`font-family：字体`
元素靠右/左	`text-align：right/left` 		/  	` float: right/left`




a标签：
```css
<style type = “text/css”> 
<!-- 
a {font-size:16px} 
a:link {color: blue; text-decoration:none;} //未访问：蓝色、无下划线 
a:active:{color: red; } //激活：红色 
a:visited {color:purple;text-decoration:none;} //已访问：紫色、无下划线 
a:hover {color: red; text-decoration:underline;} //鼠标移近：红色、下划线 
--> 
</style>
```


div并排的方法：

1. `float:left;`
```css
#div1{
  width:50%;
  height:300px;
  background:blue;
  float:left;
}
#div2{
  width:50%;
  height:300px;
  background:green;
  float:left;
}
```

2. `display:table-cell`
```css
#parent{
	width:100%;
	display:table;
}
#div1{
	width:50%;
	height:300px;
	background:blue;
	display:table-cell;
}
#div2{
	width:50%;
	height:300px;
	background:green;
	display:table-cell;
}
```

3. `flex布局`
```css
#parent{
	display:flex;
}
#div1{
	width:50%;
	height:300px;
	background:blue;
	flex:1;
}
#div2{
	width:50%;
	height:300px;
	background:green;
	flex:1;
}
```
