---
layout: post
title: "ยท @Controller ์ @GetMapping"
nav_order: 1
parent : Spring
grand_parent: ๐ฉ๐ปโ๐ปLanguage
permalink: docs/Language/Spring/ControllerAndMapping
---

# @Controller ์ @GetMapping์ ์ด์ฉํด์ htmlํ์ผ ๋์ฐ๊ธฐ

<br>



์คํ๋ง๋ถํธ๋ static ํด๋์ `index.html` ํ์ผ์ ์์ฑํ๋ฉด, `index.html` ํ์ผ์ ์ด๊ธฐ ํ๋ฉด์ผ๋ก ๋์ด์ค๋ค.



๊ทธ๋ฆฌ๊ณ  `index.html` ํ์ผ์ `<body>` ๋ถ๋ถ์



`<a href = "/randomname">Click</a>` ๋ฅผ ์๋ ฅํด์ฃผ๊ณ  (randomname ๋ถ๋ถ์๋ ์ํ๋ ์ด๋ฆ์ ๋ฃ๋๋ค.)



, ์น์๋ฒ๋ฅผ ์์ํ๊ณ  localhost์ ๋ค์ด๊ฐ๋ณด๋ฉด,


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018175255522.png" alt="image-20221018175255522" style="zoom:80%;" />
</p>

Click์ด๋ผ๋ ํ์ดํผ๋งํฌ๊ฐ ์์ฑ๋๊ณ  ํด๋ฆญํ๋ฉด



http://localhost:8080/randomname ์ผ๋ก ์ด๋ํ๊ฒ ๋๋ค.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018175313796.png" alt="image-20221018175313796" style="zoom:80%;" />
</p>



ํ์ง๋ง, ์์ง ์์ฑํด ๋์๊ฒ ์๊ธฐ ๋๋ฌธ์, error page๊ฐ ๋์จ๋ค.



------



๋จผ์  `templates` ํด๋์ `randomname.html` ํ์ผ์ ๋ง๋ ๋ค.

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018175333496.png" alt="image-20221018175333496" style="zoom:80%;" />
</p>



body ๋ถ๋ถ์ `This is randomname html` ์ด๋ผ๋ ๋ฌธ๊ตฌ๋ฅผ ์์ฑํ์๋ค.



์ด์  ์ด `randomname.html` ํ์ผ์ ๋์์ฃผ๊ธฐ ์ํด `Controller`๋ผ๋ ๊ฒ์ ๋ง๋ค์ด์ผ ํ๋ค.



------


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018175353342.png" alt="image-20221018175353342"  />
</p>

java ํด๋์ `MakeController` ๋ผ๋ javaํ์ผ์ ์์ฑํ๋ค.



`@Controller` ์๋ํ์ด์์ ๊ผญ ํด์ฃผ์ด์ผ ํ๋ค.



๊ทธ๋ฆฌ๊ณ 



`@GetMapping("randomname")` ์ ํด์ฃผ์ด์ผ `randomname` ๋ฉ์๋๋ฅผ ์คํ์์ผ์ค๋ค.



์ฌ์ค `GetMapping()` ๊ธฐ์ค์ผ๋ก ๋ฉ์๋๊ฐ ์คํ๋๋ ๊ฒ์ด๊ธฐ ๋๋ฌธ์, ๋ฉ์๋์ ์ด๋ฆ์ ๊ผญ `randomname`์ด ์๋์ฌ๋ ๋๋ค.



๋์  return ๊ฐ์ ๊ผญ ์ฐ๊ฒฐํ  htmlํ์ผ๋ช์ผ๋ก ํด์ผํ๋ค.



randomname ๋ฉ์๋์ ๋ด์ฉ์ "randomname" ์ ๋ฐํํ๋ ๊ฐ๋จํ ์ฝ๋๋ฅผ ์์ฑํ์๋ค.



randomname ์ ๋ฐํํ๊ธฐ ๋๋ฌธ์, randomname ์ด๋ผ๋ ์ด๋ฆ์ html ํ์ผ์ด ์๋ ํ์ธ์ ํด๋ณด๊ณ  ์๋ค๋ฉด html ํ์ผ์ ๋ถ๋ฌ์ค๊ฒ ๋๋ ๊ฒ์ด๋ค.



------

์๋ฒ๋ฅผ ๋ค์ ์์ํ๊ณ  Click์ ๋๋ฌ์ฃผ๋ฉด


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018175409072.png" alt="image-20221018175409072" style="zoom:80%;" />
</p>

์ด์ ๊ฐ์ด, `randomname.html` body ๋ถ๋ถ์ ์๋ ฅํ๋ ๋ฌธ๊ตฌ๊ฐ ๋์ค๋ ๊ฒ์ ํ์ธํ  ์ ์๋ค.



------

{: .note-title }
> ์ ๋ฆฌ
>
> 1. <a href="/**์ํ๋์ด๋ฆ**"> Click</a>๋ฅผ ์ฌ์ฉํ๋, url ์ ์๋ ฅํด์ localhost:8080/**์ํ๋์ด๋ฆ** ์ผ๋ก ๋ค์ด๊ฐ๋, htmlํ์ผ์ ๋์ฐ๊ณ  ์ถ๋ค๋ฉด ๋จผ์ , resource/templates ํด๋์ [html์ด๋ฆ].html ํ์ผ์ ์์ฑํ๋ค. ์ฐธ๊ณ ๋ก **์ํ๋์ด๋ฆ**์ GetMapping์ผ๋ก ๋ฃ์ ์ธ์์ ๋์ผํด์ผ ์์คํ์ด ์บ์นํ  ์ ์๋ค. ์ฆ, GetMapping("**์ํ๋์ด๋ฆ**") ๊ณผ ๋์ผํด์ผ ์บ์นํ  ์ ์๋ค.
>
> 
> 2. html ํ์ผ์ ์์ฑํ๋ค๋ฉด, ์ด๋ฅผ ์ฐ๊ฒฐ์์ผ์ค Controller ์๋ฐ ํ์ผ์ ์์ฑํ๋ค.
>
> 
> 3. @Controller ์๋ํ์ด์์ ๋ฃ์ด์ฃผ์ด์ผ ํ๋ค.
>
> 
> 4. @GetMapping("**์ํ๋์ด๋ฆ**") ์ ์์ฑํ๊ณ  return ๊ฐ์ผ๋ก "[html์ด๋ฆ]" ์ ๋ฐํํ๋ค.
>
> 
> 5. [html์ด๋ฆ]์ด ๋ฐํ๋๋ฉด์, resource/templates ํด๋์์ html์ ์ฐพ๊ณ , ์์ฑํด๋, [html์ด๋ฆ].html ์ด ๋์์ง๋ค.
>
>
> โป templates ํด๋์ ๊ผญ ์ ์ฅ์ ํด์ฃผ์ด์ผ controller๊ฐ ์ฐพ์ ์ ์๋ค. ๋ง์ฝ static ํด๋์ htmlํ์ผ์ ์ ์ฅํ๋ค๋ฉด, Controller๊ฐ ์๋ index.html์์ ์ฐธ์กฐ๋ฅผ <a href = "[html์ด๋ฆ].html"> ๋ก ํด์ฃผ๋ฉด ๋ฐ๋ก ์ด๋ํ  ์ ์๋ค. ํ์ง๋ง static ํด๋์ ์ ์ฅํ html์ ์ปจํธ๋กค๋ฌ๋ก ์ฐ๊ฒฐ์์ผ์ค ์ ์๋ค.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018175430151.png" alt="image-20221018175430151" style="zoom:80%;" />
</p>
