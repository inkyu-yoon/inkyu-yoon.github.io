---
layout: post
title: "Β· JavaScript κΈ°μ΄"
nav_order: 2
parent : FrontEnd
grand_parent: π©π»βπ»Language
permalink: docs/Language/FrontEnd/JavaScript
---

# JavaScript κΈ°μ΄

<br>

## JavaScript μ κΈ°λ³Έ

<br>

JavaScript μ½λλ λ³΄ν΅ `<body>`  νκ·Έ μμ λ£κ³ , `<script>` νκ·Έλ‘ κ°μΈμΌ μΈμμ΄ λλ€.

{% capture some_var %}
```html
<body>
	<script>
	
	</script>
</body>
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}



<br>



`.js` νμΌμ `css` νμΌμ λ§λ€μλ―μ΄, μμ±ν λ€ HTMLμ μ μ©μν€κΈ° μν΄μλ, μλ₯Ό λ€μ΄ `test.js` νμΌμ΄ μλ€κ³  ν λ, μ΄ νμΌ μμ λ΄μ©μ μ μ©μν€κΈΈ μνλ λΆλΆμ `<script src = "test.js"> </script>` λ₯Ό μλ ₯νλ©΄ λλ€.



{% capture some_var %}
```html
<body>
	<script src = "test.js">	</script>
</body>
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}



<br>



JavaScriptμμ λ³μ μ μΈμ λ€μκ³Ό κ°μ΄ νλ€.


```
<script>
var name = 'κΉμ² μ';
var num = 1;
var power = false;
var num2 = 1.2;
var array = [1,2,3,4,5,6];

document.write(typeof name);
//typeof λ λ³μμ λ°μ΄ν° νμμ λ°ννλ€. (String,int,float,bool λ±λ±)

array.push(7);
</script>

```


`doucument.write()` λ μνλ λ¬Έμμ΄μ μΆλ ₯ν΄μ£Όλ λ©μλμ΄λ€. HTML μ `<p>` νκ·Έμ μ μ¬ν κΈ°λ₯μ΄λ€.



`document.write("μλ")`  μ κ°μ΄ μ¬μ©νλ©΄ λλ€.



<br>



`.push()` λ λ°°μ΄ λ§μ§λ§ κ°μ μΆκ°νλ λ©μλμ΄λ€. μλ° λ¬Έλ²μμ list ν΄λμ€μ `add`μ μ μ¬ν κΈ°λ₯μ΄λ€.



<br>



κ·Έλ¦¬κ³ , JavaScriptλ λ°°μ΄μ `.indexOf()` λ§€μλλ₯Ό μ¬μ©ν  μ μλ€.

λν`.sort()` λ©μλλ₯Ό λ°°μ΄μ μ¬μ©νμ¬ μ λ ¬ν  μ μκ³ ,



<br>



`.sort((a,b)=>a-b)` μ κ°μ΄ μλ°μ λλ€μκ³Ό λΉμ·ν λ°©λ²μΌλ‘ μ‘°κ±΄μ μΆκ°ν μ μλ€.

μμ μλ μ‘°κ±΄μμ΄ μμλ©΄ μμΉλ₯Ό λ°κΎΈλ μλ°μ Comparator μ μ μ¬νλ€.