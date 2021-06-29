## **Web 基础客户端编程（frameset标签搭配DIV+CSS）**
<hr style=" border:solid; width:100px; height:1px;" color=#000000 size=1">

<font size=5>编程内容：使用HTML超文本标记语言制作简单页面，验证并掌握HTML超文本标记语言的文本、图像、超链接、表格、表单等标记的使用，通过实验掌握层叠样式表CSS的创建及应用，掌握在网页中插入层叠样式表CSS的常用方法，掌握层叠样式表CSS的主要基本属性的使用。
<hr style=" border:solid; width:100px; height:1px;" color=#000000 size=1">

<font size=5>编程环境：Eclipse+Tomcat
<hr style=" border:solid; width:100px; height:1px;" color=#000000 size=1">

**（以下源码放在同一文件夹下运行）**
**简单使用jsp页面进行frameset框架进行页面布局（垂直+水平进行页面布局）**
```html
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
    <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<frameset rows=13%,15%,62%,10%>

<frameset>
<frame src="head.html"/>
</frameset>

<frameset cols="20%,20%,20%,20%,20%" frameborder="yes" framespacing="1">
   <frame src="a.html" name="ahtml"/>
   <frame src="b.html" name="bhtml"/>
   <frame src="c.html" name="chtml"/>
   <frame src="d.html" name="dhtml"/>
   <frame src="e.html" name="ehtml"/>
</frameset>

<frameset frameborder="yes" framespacing="1">
<frame src="main.html" name="mainht"/>
</frameset>

<frameset frameborder="yes" framespacing="1">
<frame src="foot.html"/>
</frameset>

</frameset>	
</html>
```

a.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>理工大学</title>
<style type="text/css">

body {background-color:WhiteSmoke;}
a:link{text-decoration:none;}
#x{
font-size:30px;
font-weight:bold;
text-align:center;
}
</style>
</head>
<body>
<p id="x"><a href="https://www.mit.edu/" target="mainht" title="理工大学">理工大学</a></p>
</body>
</html>
```

b.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>支付跑注册</title>
<style type="text/css">

body {background-color:WhiteSmoke;}
a:link{text-decoration:none;}
#x{
font-size:30px;
font-weight:bold;
text-align:center;
}
</style>
</head>
<body>
<p id="x"><a href="register.html" target="mainht" title="支付跑注册">支付跑注册</a></p>
</body>
</html>
```

c.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>支付宝注册</title>
<style type="text/css">

body {background-color:WhiteSmoke;}
a:link{text-decoration:none;}
#x{
font-size:30px;
font-weight:bold;
text-align:center;
}
</style>
</head>
<body>
<p id="x"><a href="https://memberprod.alipay.com/account/reg/index.htm" target="mainht" title="支付宝注册">支付宝注册</a></p>
</body>
</html>
```

d.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>博客推荐</title>
<style type="text/css">

body {background-color:WhiteSmoke;}
a:link{text-decoration:none;}
#x{
font-size:30px;
font-weight:bold;
text-align:center;
}
</style>
</head>
<body>
<p id="x"><a href="https://me.csdn.net/qq_44770793" target="mainht" title="博客推荐">博客推荐</a></p>
</body>
</html>
```

e.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>find cow</title>
<style type="text/css">

body {background-color:WhiteSmoke;}
a:link{text-decoration:none;}
#x{
font-size:30px;
font-weight:bold;
text-align:center;
}
</style>
</head>
<body>
<p id="x"><a href="https://findtheinvisiblecow.com/" target="mainht" title="find cow">find cow</a></p>
</body>
</html>
```

foot.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>foot</title>
<style type="text/css">

body {background-color:WhiteSmoke;}
a:link{text-decoration:none;}
#x{
font-size:13px;
font-weight:bold;
text-align:center;
}
</style>
</head>
<body>
<p id="x">关于注册|服务条款|使用规范|客服中心|版权所有：YUHAO</p>
<p id="x">© 2000 - 2200 yuhao Inc. All Rights Reserved</p>
</body>
</html>
```

head.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
</head>
<body background="https://www.mit.edu/files/images/202010/MIT-Expecting-Robots-SL2.gif">
<img src="http://picnew8.photophoto.cn/20131221/mashengligongxueyuanbiaozhitupian-11439091_1.jpg">
</body>
</html>
```

register.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<script type="text/javascript">
function sname(form){
	if(form.xingming.value.length == 0)
		{alert("姓名不能为空！");return false;}
	if((form.xingming.value.length < 6)||(form.xingming.value.length>18))
		{alert("姓名格式不正确");return false;}
	return true;
}
function smima(form){
	if(form.mima.value.length==0)
		{alert("密码不能为空");return false;}
	else
		return true;
}
function siphone(form){
	var testt=/^[1][3,4,5,7,8,9][0-9]{9}$/;
	if(form.iphone.value.length==0)
		{alert("手机号码不能为空");return false;}
	if(!testt.test(form.iphone.value))
		{alert("请填写格式正确的手机号码");return false;}
	return true;
}
</script>
<style type="text/css">
body {background-color:WhiteSmoke;}
form {
font-size:30px;
font-weight:bold;
text-align:center;
}
</style>
</head>
<body>
<p align="center"><font size=20px>支付跑官网</font></p>
<form action="">
姓名:<input type="text" value="" name="xingming" >6~18位<br>
密码:<input type="password" name="mima"><br>
手机号码:<input type="number" name="iphone"><br>
E-mail:<input type="email" name="mail"><br>
<input type="submit" value="提交" onclick="sname(this.form);smima(this.form);siphone(this.form) ">
<input type="reset" value="重置"> 
<input type="button" value="关闭" onclick="window.close()"/>
</form>
</body>
</html>
```

