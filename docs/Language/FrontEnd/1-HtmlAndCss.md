---
layout: post
title: "ยท HTML / CSS ๊ธฐ์ด"
nav_order: 1
parent : FrontEnd
grand_parent: ๐ฉ๐ปโ๐ปLanguage
permalink: docs/Language/FrontEnd/HtmlAndCss
---

# HTML / CSS ๊ธฐ์ด
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---



## html ๊ธฐ๋ณธ ํ์

<br>

html์ ๋ฌธ์๋

{% capture some_var %}
```html
<!DOCTYPE html>
<html>

</html>
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


์์ ๊ฐ์ ์ ์ผ ํฐ ํ์ ๋จผ์  ์์ฑํ ํ ์์ ๋ด์ฉ๋ค์ ๋ฃ๋๋ค.



๊ทธ๋ฆฌ๊ณ  ํ๊ตญ์ด๋ฅผ ์ธ์ํ  ์ ์๊ฒ, `<meta charset = "UTF-8">` ์ฝ๋๋ฅผ ํ๊ทธ์ ์ถ๊ฐํด์ฃผ์ด์ผ ํ๋ค.



---



## html์ ๊ฐ๋จํ ๊ตฌ์กฐ


<br>

{% capture some_var %}
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset = "UTF-8">
		<title> ํ์ดํ ์ ๋ชฉ์๋๋ค.</title>
	</head>
	<body>
		<h1> ๊ฒ์๊ธ ํฐ ์ ๋ชฉ์๋๋ค.</h1>
		<p> ๋ด์ฉ์๋๋ค. </p>
        <footer>๋ฐ๊ฐ์ต๋๋ค..</footer>
	</body>
</html>
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


์์ ๊ฐ์ด ์ฝ๋๋ฅผ ์๋ ฅํ๋ฉด

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017160724358.png" alt="image-20221017160724358" style="zoom: 67%;" />
</p>



์ด๋ฌํ ๊ฒฐ๊ณผ๋ฅผ ์ป์ ์ ์๋ค.

<br>

`<body></body>` ํ๊ทธ ์์ ์๋ ๋ด์ฉ๋ค์ html ๋ฌธ์์ ์ง์ ์ ์ผ๋ก ํํ๋๋ ๋ด์ฉ์ ๋ฃ๋ ํ๊ทธ์ด๋ค.



`<footer></footer>` ํ๊ทธ๋, html ๋ฌธ์ ์ ์ผ ์๋์ ์ํ๋ ๋ด์ฉ์ ํ์ํ๋ ํ๊ทธ์ด๋ค.



---



## CSS ์ ์ฉ

<br>

html ์ ๊ฐ๋จํ๊ฒ ๋งํ๋ฉด, ๊ณจ๊ฒฉ๊ณผ ๊ตฌ์กฐ๋ฅผ ๊ฒฐ์ ํ๋ ์ฝ๋์ด๊ณ , ๊ทธ ์ธ์ ๋ด์ฉ์ ์์ด๋, ํฌ๊ธฐ ๋ฑ ์คํ์ผ์ ์ค์ ํ๊ธฐ ์ํด์๋ css ์ฝ๋๋ฅผ ์์ฑํด์ผ ํ๋ค.



css๋ฅผ ์ ์ฉํ๊ธฐ ์ํด์๋ css ์ฝ๋๊ฐ ์์ฑ๋ css ํ์ผ์ ์ฐ๊ฒฐ์์ผ์ฃผ์ด์ผ ํ๋๋ฐ, head ํ๊ทธ ์์ `<link rel="stlyesheet" href="cssํ์ผ์ด๋ฆ.css">` ์ ๋ฃ์ด์ฃผ๋ฉด๋๋ค.



์๋ฅผ ๋ค์ด, `codelion.css` ํ์ผ์ด ์๋ค๊ณ  ํ  ๋,
{% capture some_var %}
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset = "UTF-8">
		<title> ํ์ดํ ์ ๋ชฉ์๋๋ค.</title>
        <link rel = "stylesheet" href="codelion.css">
	</head>
	<body>
		<h1> ๊ฒ์๊ธ ํฐ ์ ๋ชฉ์๋๋ค.</h1>
		<p> ๋ด์ฉ์๋๋ค. </p>
        <footer>๋ฐ๊ฐ์ต๋๋ค..</footer>
	</body>
</html>
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


html ํ์ผ์ ์์ ๊ฐ์ด ์์ฑํ๊ณ 


{% capture some_var %}
```css
footer{
    text-align : center;
    background-color:black;
    color:white;
}
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}

์์ ๊ฐ์ด css ํ์ผ์ ์ ์ฉํ๋ค๋ฉด,


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017161514131.png" alt="image-20221017161514131" style="zoom:67%;" />
</p>

์์ ๊ฐ์ด, footer ๋ถ๋ถ์ ์คํ์ผ์ด ๊ฒ์์ ๋ฐฐ๊ฒฝ์ ํ์์ ๊ธ์, ๊ทธ๋ฆฌ๊ณ  ๊ฐ์ด๋ฐ ์ ๋ ฌ์ด ๋ ๊ฒ์ ํ์ธํ  ์ ์๋ค.

์ฆ, ํน์  ํ๊ทธ์ ์คํ์ผ์ ๊ฒฐ์ ํ๋ ๊ฒ์ด css ํ์ผ์ด๋ผ๊ณ  ๋ณผ ์ ์๋ค.

์ด ์ธ์๋, ์๋์ ๊ฐ์ ์ค์ ๋ค์ด ์๋ค.

<br>

`font-size : ()px;` : ํฐํธ ์ฌ์ด์ฆ ์กฐ์ 

`color : ();` : ํฐํธ ์ ์ค์  (black,red ๋ฑ๋ฑ)

`font-weight : ();`  : ํฐํธ ๋๊ป ์ค์  (bold, or ์ซ์ ๋ฑ๋ฑ)

`line-height : ()px; ` : ํฐํธ ๊ฐ๊ฒฉ ์ค์ ( ๐ก ์ผ๋ฐ์ ์ผ๋ก ํฐํธ ํฌ๊ธฐ์ 160%๋ก ์ค์ ํ๋ค)

---



## style๋ฅผ ๊ตฌ๋ถํด์ ์ ์ฉํ๊ธฐ

<br>

์์ ๊ฐ์ ๋ฐฉ๋ฒ์ผ๋ก๋, ์คํ์ผ์ด ์ ์ฉ๋ ๋ชจ๋  ํ๊ทธ๊ฐ ์คํ์ผ์ด ๊ฒฐ์ ๋๋ฏ๋ก, ์ํ๋ ๋ถ๋ถ๋ง ์คํ์ผ์ ์ ์ฉํ  ์ ์๋ค.



์ด๋, class๋ฅผ ์ ์ฉ์์ผ, ์ ์ฉํ๊ธธ ์ํ๋ ์คํ์ผ์ ๋๋ ์ ์ ์ฉํ  ์ ์๋ค.


{% capture some_var %}
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset = "UTF-8">
		<title> ํ์ดํ ์ ๋ชฉ์๋๋ค.</title>
        <link rel = "stylesheet" href="codelion.css">
	</head>
	<body>
		<h1> ๊ฒ์๊ธ ํฐ ์ ๋ชฉ์๋๋ค.</h1>
		<p class = "ex1"> ์ฒซ๋ฒ์งธ ๋ด์ฉ์๋๋ค. </p>
        <p class = "ex2"> ๋๋ฒ์งธ ๋ด์ฉ์๋๋ค. </p>
        <p class = "ex3"> ์ธ๋ฒ์งธ ๋ด์ฉ์๋๋ค. </p>
        <footer>๋ฐ๊ฐ์ต๋๋ค..</footer>
	</body>
</html>
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


์์ ๊ฐ์ด ํ๊ทธ์ class๋ฅผ ์ฌ์ฉํด์ ์ด๋ฆ์ ๋ถ์ฌ์ฃผ๊ณ 


{% capture some_var %}
```css
footer{
    text-align : center; 
    background-color:black; 
    color:white;
}

.ex1{
    font-size : 30px;
}

.ex2{
    font-size : 40px;
}

.ex3{
    font-size : 10px;
}
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


์์ ๊ฐ์ด, ์ ํด์ค ์ด๋ฆ ์์ `.` ์ ๋ถ์ฌ์ฃผ๊ณ  ์คํ์ผ์ ์ ์ฉ์์ผ์ฃผ๋ฉด


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017162536519.png" alt="image-20221017162536519" style="zoom:67%;" />
</p>

์์ ๊ฐ์ด ๊ฐ <p> ํ๊ทธ๋ง๋ค ์คํ์ผ์ด ์ ์ฉ๋ ๊ฒ์ ๋ณผ ์ ์๋ค.



https://htmlcolorcodes.com/

๐ก TIP : ์ ์ฌ์ดํธ์์ color ์ฝ๋๋ฅผ ์ป๊ณ , ๋ค์ํ ์์ ํํํ  ์ ์๋ค.



---



## div ํ๊ทธ ์ ์ฉ

<br>

์ฌ๋ฌ ํ๊ทธ์ ์คํ์ผ์ ํ๋ฒ์ ์ ์ฉํ๊ธฐ ์ํด์๋ `<div></div>` ํ๊ทธ๋ก ๊ฐ์ธ์ฃผ๊ณ  ์คํ์ผ์ ์ ์ฉ์ํค๋ฉด ๋๋ค.



`border : ๋๊ป ๋ฐฉ์ ์๊น ;` ๋ก ๋ฐ์ค๋ฅผ ๋ง๋ค ์ ์๋ค.

`width : ๋๋น;` ๋ก ๋ฐ์ค์ ๋๋น๋ฅผ ์ค์ ํ  ์ ์๋ค.

`margin-left : auto; margin-right : auto;` ๋ฅผ ์ฌ์ฉํ๋ฉด ๋ฐ์ค๋ฅผ ๊ฐ์ด๋ ์ ๋ ฌ์ํฌ ์ ์๋ค.


{% capture some_var %}
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset = "UTF-8">
		<title> ํ์ดํ ์ ๋ชฉ์๋๋ค.</title>
        <link rel = "stylesheet" href="codelion.css">
	</head>
	<body>
		<h1> ๊ฒ์๊ธ ํฐ ์ ๋ชฉ์๋๋ค.</h1>
        <div class = "div1">
        	<p class = "ex1"> ์ฒซ๋ฒ์งธ ๋ด์ฉ์๋๋ค. </p>   
        </div>
        
        <div class = "div2">
		    <p class = "ex2"> ๋๋ฒ์งธ ๋ด์ฉ์๋๋ค. </p>
            <p class = "ex3"> ์ธ๋ฒ์งธ ๋ด์ฉ์๋๋ค. </p>
            <footer>๋ฐ๊ฐ์ต๋๋ค..</footer>
        </div>
	</body>
</html>
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


์์ ๊ฐ์ด 2๊ฐ์ div ๋ฐ์ค๋ฅผ ๋ง๋ค์๋ค.


{% capture some_var %}
```css
footer{
    text-align : center; 
    background-color:black; 
    color:white;
}

.ex1{
    font-size : 30px;
}

.ex2{
    font-size : 40px;
}

.ex3{
    font-size : 10px;
}
.div1{
    border : 3px solid blue;
    width : 610px;
    margin-left : auto;
    margin-right : auto;
}
.div2{
    border : 5px solid red;
    width : 500px;
    margin-left : auto;
    margin-right : auto;
}
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


๊ทธ๋ฆฌ๊ณ  ์์ ๊ฐ์ css ํ์ผ์ ์ ์ฉ์์ผฐ์ ๋


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017164442667.png" alt="image-20221017164442667" style="zoom:67%;" />
</p>

์์ ๊ฐ์ ๊ฒฐ๊ณผ๋ฅผ ์ป์ ์ ์๋ค.



`div` ๋ฟ๋ง ์๋๋ผ `section` `article` ๋ฑ์ผ๋ก ์ฝํ์ธ ๋ฅผ ๋ถ๋ฆฌํ  ์ ๋ ์๋ค. 

๋ค์ํ ํ๊ทธ๋ฅผ ์ ์ ํ ๊ณณ์ ํ์ฉํ์๋, ๊ฐ๋์ฑ์ ๋์ผ ์ ์๋ค.



---



## ๋ฐ์ค ๊พธ๋ฏธ๊ธฐ

<br>

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017170033588.png" alt="image-20221017170033588" style="zoom: 67%;" />
</p>



๋ฐ์ค๋ margin + border + padding + contents(width & height) ๋ฐ์ค๋ก ์ด๋ฃจ์ด์ ธ์๊ณ , ๊ฐ ์ฌ์ด์ฆ๋ฅผ ์กฐ์ ํด์ ์ํ๋ ํํ์ ๋ฐ์ค๋ฅผ ๋ง๋ค ์ ์๋ค.

{% capture some_var %}
```css
footer{
    text-align : center; 
    background-color:black; 
    color:white;
}

.ex1{
    font-size : 5px;
}

.ex2{
    font-size : 5px;
}

.ex3{
    font-size : 5px;
}
.div1{
    height : 100px;
    width : 100px;
    margin : 20px;
    border : 20px solid black;
    padding: 20px;
}
.div2{
    height : 100px;
    width : 100px;
    border : 20px solid red;
}
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


cssํ์ผ์ ์์ ๊ฐ์ด ์ ์ฉํด๋ณด๋ฉด


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017171220159.png" alt="image-20221017171220159" style="zoom: 50%;" />
</p>



์์ ๊ฐ์ ๊ฒฐ๊ณผ๋ฅผ ์ป์ ์ ์๊ณ , ๋ ๋ฐ์ค์ contents ๋ฐ์ค์ ํฌ๊ธฐ๋ฅผ ๊ฒฐ์ ํ๋ height ์ width์ border ์ฌ์ด์ฆ๋ ๋์ผํ๋ค.



ํ์ง๋ง ์ฒซ๋ฒ์งธ ๋ฐ์ค์ ๊ฒฝ์ฐ margin ์ฌ์ด์ฆ์ padding ์ฌ์ด์ฆ๋ ์กด์ฌํ์ฌ ์์ ๊ฐ์ ๊ฒฐ๊ณผ๊ฐ ๋์จ๋ค.



`(margin/border/padding)-(top/bottom/right/left)` ์ ๊ฐ์ด ์ํ๋ ๋ฐฉํฅ๋ง ๊ณต๊ฐ์ ์์ฑํ  ์๋ ์๋ค.



---

๋ฐ์ค์ ๊ทธ๋ฆผ์๋ฅผ ์ค์ ํ์ฌ ๋ฃ์ ์๋ ์๋ค.



`box-shadow : (๊ทธ๋ฆผ์ ๊ฐ๋ก๋ฐฉํฅ ์๋์์น) (๊ทธ๋ฆผ์ ์ธ๋ก๋ฐฉํฅ ์๋์์น) (๊ทธ๋ฆผ์ ํ๋ฆฌ๊ฒ) (๊ทธ๋ฆผ์ ํฌ๊ธฐ) (๊ทธ๋ฆผ์ ์)`

<br>

์ฒซ๋ฒ์งธ ์ธ์๋, ์์๊ฐ์ ๊ทธ๋ฆผ์๊ฐ ์ค๋ฅธ์ชฝ์ผ๋ก, ์์ ๊ฐ์ ๊ทธ๋ฆผ์๊ฐ ์ผ์ชฝ์ผ๋ก ์๊ธด๋ค

๋๋ฒ์งธ ์ธ์๋, ์์๊ฐ์ ๊ทธ๋ฆผ์๊ฐ ์๋์ชฝ์ผ๋ก, ์์ ๊ฐ์ ๊ทธ๋ฆผ์๊ฐ ์๋ก ์๊ธด๋ค.

์ธ๋ฒ์งธ ์ธ์๋, ๊ฐ์ด ํด์๋ก ๊ทธ๋ฆผ์๋ฅผ ํ๋ฆฌ๊ฒ ๋ง๋ ๋ค.

๋ค๋ฒ์งธ ์ธ์๋, ๋ฐ์ค์ ํฌ๊ธฐ๋ณด๋ค ๊ทธ๋ฆผ์์ ํฌ๊ธฐ๋ฅผ ํค์ฐ๊ณ  ์ถ์๋ ๋ฃ๋ ๊ฐ์ด๋ค. 10px๋ฅผ ์๋ ฅํ๋ฉด, ๊ฐ๋ก์ธ๋ก ํฌ๊ธฐ๊ฐ ๋ฐ์ค๋ณด๋ค 10px ํฐ ๊ทธ๋ฆผ์๊ฐ ์์ฑ๋๋ค.

๋ค์ฏ๋ฒ์งธ ์ธ์๋, ๊ทธ๋ฆผ์์ ์์ ๊ฒฐ์ ํ๋ค. 

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017173756804.png" alt="image-20221017173756804" style="zoom:67%;" />
</p>

<br>

`box-shadow: 20px 20px 20px 10px red;` ๋ฅผ ์ ์ฉํ ๋ฐ์ค์ ์์์ด๋ค.





---



## html ํฐํธ ์ ์ฉํ๊ธฐ

<br>

๊ธฐ๋ณธ ํฐํธ๋ ๋๋ฌด ๋ฑ๋ฑํ๊ธฐ ๋๋ฌธ์, ํฐํธ๋ฅผ ์ ์ฉํด๋ณธ๋ค.



https://fonts.google.com/

์ ์ฌ์ดํธ์์ ์ํ๋ ํฐํธ๋ฅผ ์ฐพ์๋ค์์


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017174222064.png" alt="image-20221017174222064" style="zoom: 67%;" />
</p>


์ํ๋ ํฐํธ ์คํ์ผ์ ์ฐพ์ ๋ค, `+` ๋ฅผ ํด๋ฆญํ๊ณ , ์ด๋ฆฌ๋ ์ฐฝ์์ 

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017174519042.png" alt="image-20221017174519042" style="zoom:80%;" />
</p>

์ด ๋ถ๋ถ์ ๋ณต์ฌํด์ css ํ์ผ์ ์๋ ฅํ๊ณ 

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017174621132.png" alt="image-20221017174621132" style="zoom:80%;" />
</p>

์ ์ฌ์ง ์ฒ๋ผ, ์ํ๋ ๋ฐ์ค์ `font-family: 'Montserrat';` ๋ฅผ ์๋ ฅํ๋ฉด ๋๋ค. (์ด๋ฆ์ ํฐํธ๋ง๋ค ๋ค๋ฅด๋ค.)

`sans-serif` ๋ ๊ธ์ ์คํ์ผ์ธ๋ฐ, `cursive`,`fantasy` ๋ฑ์ด ์๋ค.



---

## float

<br>

ํ ๋ผ์ธ์์ ํน์  ๋ถ๋ถ์ ์ผ์ชฝ, ํน์  ๋ถ๋ถ์ ์ค๋ฅธ์ชฝ์ผ๋ก ์ ๋ ฌ์ํค๊ธฐ ์ํด์๋ `float : (right/left); ` ๋ฅผ ์ด์ฉํด์ ์ ๋ ฌํด์ผ ํ๋ค.

๋ํ, float๋ฅผ ์ด์ฉํด์ ์ ๋ ฌํ ๋ด์ฉ๋ค์ด ๊ฒน์ณ์ง์ง ์๊ฒ ํ๊ธฐ ์ํด์๋ 

๊ฒน์ณ์ง๋ ํ๊ทธ๋ฅผ div๋ก ๊ฐ์ผ ํ,`overflow: hidden` ์์ฑ์ ์ถ๊ฐํด์ฃผ์ด์ผ ํ๋ค.


{% capture some_var %}
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <link rel="stylesheet" href="codelion.css">
</head>
<body>
	</p> ์๋ํ์ธ์.   ์์ฑ์ </p>
</body>
</html>

```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


์์ ๊ฐ์ ์ฝ๋๋


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017192148774.png" alt="image-20221017192148774" style="zoom:80%;" />
</p>

์์ ๊ฐ์ด ๋ถ์ด์ ์ถ๋ ฅ๋  ๊ฒ์ด๋ค.

{% capture some_var %}
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="codelion.css">
  </head>
  <body>
        <p class="text1">์๋ํ์ธ์</p>
        <p class="text2">์์ฑ์</p>
  </body>
</html>
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}

{% capture some_var %}
```css
.text1 {
    float: left;
}

.text2 {
    float: right;
}
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


ํ์ง๋ง, ๊ฐ๊ฐ <p> ํ๊ทธ๋ก ๊ฐ์ผ ํ, float ์์ฑ์ css ์์ ์์ ๊ฐ์ด ๋ถ์ฌํ๋ฉด,


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017192328132.png" alt="image-20221017192328132" style="zoom:80%;" />
</p>


์ด๋ ๊ฒ, ์๋ํ์ธ์๋ ์ผ์ชฝ์ ๋ ฌ, ์์ฑ์๋ ์ค๋ฅธ์ชฝ ์ ๋ ฌ์ด ๋๋ค.


{% capture some_var %}
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="codelion.css">
  </head>
  <body>
        <p class="text1">์๋ํ์ธ์</p>
        <p class="text2">์์ฑ์</p>
        <p>์ ๋ html๊ณผ css๋ฅผ ๋ฐฐ์ฐ๊ณ  ์์ต๋๋ค.</p>
  </body>
</html>
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}

ํ์ง๋ง, ์๋์ ๋ฌธ์ฅ์ ํ๋ ์ถ๊ฐํ์๋,

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017192457676.png" alt="image-20221017192457676" style="zoom:80%;" />
</p>

์์ ๊ฐ์ด ์ถ๋ ฅ์ด ์ด์ํ๊ฒ ๋  ์ ์๋ค. ์ด๋ฐ ๊ฒฝ์ฐ๋ , float ์์ฑ์ ๋ถ์ฌํ ํ๊ทธ๋ค์ ๋ฌถ์ด์ `overflow : hidden;` ์์ฑ์ ๋ถ์ฌํด์ฃผ๋ฉด ๋๋ค.


{% capture some_var %}
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="codelion.css">
  </head>
  <body>
      <section class = "section1">
        <p class="text1">์๋ํ์ธ์</p>
        <p class="text2">์์ฑ์</p>
      </section>
        <p>์ ๋ html๊ณผ css๋ฅผ ๋ฐฐ์ฐ๊ณ  ์์ต๋๋ค.</p>
  </body>
</html>
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}

{% capture some_var %}
```css
.text1 {
    float: left;
}

.text2 {
    float: right;
}

.section1{
    overflow: hidden;
}
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


์์ ๊ฐ์ด section์ผ๋ก ๋ฌถ๊ณ , overflow ์์ฑ์ ๋ถ์ฌํ๋ฉด


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221017192713097.png" alt="image-20221017192713097" style="zoom:80%;" />
</p>


์ ์์ ์ผ๋ก ์ถ๋ ฅ์ด ๋๋ ๊ฒ์ ํ์ธํ  ์ ์๋ค.



---



## ํ์ดํผ๋งํฌ ๊ฑธ๊ธฐ

<br>

{% capture some_var %}
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="codelion.css">
  </head>
  <body>
        <a href ="http://www.naver.com/"> <p class="text1">๋ค์ด๋ฒ</p></a>
  </body>
</html>
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


์์ ๊ฐ์ด `<a href = "์ฃผ์"> ย ย </a>` a ํ๊ทธ์ href ๋ก ์ฃผ์๋ฅผ ์ฐธ์กฐํ๋ฉด ์์ ์๋ ๋ด์ฉ or ์ด๋ฏธ์ง๋ฅผ ํด๋ฆญํ์ ๋, ํด๋น ์ฃผ์๋ก ์ด๋ํ  ์ ์๋ค.

