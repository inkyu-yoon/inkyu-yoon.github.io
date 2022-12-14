---
layout: post
title: "Β· Getter and Setter / Optional.ofNullable / Assertions / AfterEach / assertThrows"
nav_order: 2
parent : Spring
grand_parent: π©π»βπ»Language
permalink: docs/Language/Spring/SpringMethod
---

# Getter and Setter / Optional.ofNullable / Assertions / Extract Method μμ± / AfterEach / assertThrows
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## ν΄λμ€ μΈμ€ν΄μ€ λ³μ μλ ₯ λ° μΆλ ₯ λ©μλ κ΅¬ννκΈ°

<br>


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180104514.png" alt="image-20221018180104514" style="zoom:80%;" />
</p>

μμ κ°μ `Member` ν΄λμ€κ° μμ λ, κ° μΈμ€ν΄μ€ λ³μμ λ°μ΄ν° κ°μ μ μ₯νκ³  λ°ννλ `get` κ³Ό `set` λ©μλλ₯Ό κ΅¬ννλ λ°©λ²μ λ§€μ° κ°λ¨νλ€.



μλμ° κΈ°μ€ μΈνλ¦¬ μ μ΄ λ¨μΆν€ `ctrl + shift + n` μ μλ ₯νκ³  `Action` λΆλΆμμ `getter and setter` λ₯Ό κ²μνλ©΄ λλ€.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180156346.png" alt="image-20221018180156346"  />
</p>


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180217568.png" alt="image-20221018180217568" style="zoom:80%;" />
</p>

get, set λ©μλλ₯Ό μμ±ν  λ³μλ₯Ό μ νν ν ok λ²νΌμ λλ₯΄λ©΄


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180234985.png" alt="image-20221018180234985" style="zoom:80%;" />
</p>



μ΄μ κ°μ΄ μλμΌλ‘ μμ±λλ€!





------

## Optional μ μ¬μ©νλ μ΄μ 

<br>

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180301802.png" alt="image-20221018180301802" style="zoom:80%;" />
</p>

λ¨Όμ , νμ κ΄λ¦¬λ₯Ό μν ν΄λμ€λ₯Ό κ΄λ¦¬νκΈ° μν λ©μλλ€μ΄ μλ μΈν°νμ΄μ€λ₯Ό μμ±νλ€.



`findById()` μ `findByName()` λ©μλλ `Optional<Member>` λ‘ λ°νμ΄ λκ²λ μμ±μ΄ λμ΄μλ€.



`Optional<T>` λ μ§λ€λ¦­ ν΄λμ€λ‘ 'T νμμ κ°μ²΄'λ₯Ό κ°μΈλ λνΌ ν΄λμ€μ΄λ€.

`Optional` νμμ κ°μ²΄μλ λͺ¨λ  νμμ μ°Έμ‘°λ³μλ₯Ό λ΄μ μ μλ€.



**μ΄λ κ² νλ©΄, μ΅μ’ μ°μ°μ κ²°κ³Όλ₯Ό `Optional` κ°μ²΄μ λ΄μμ λ°νμ νλλ°, μ΄μ²λΌ κ°μ²΄μ λ΄μμ λ°νμ νλ©΄ λ°νλ κ²°κ³Όκ° nullμΈμ§ λ§€λ² ifλ¬ΈμΌλ‘ μ²΄ν¬νλ λμ **



**`Optional`μ μ μλ λ©μλλ₯Ό ν΅ν΄μ κ°λ¨ν μ²λ¦¬ν  μ μμ΄ μλ¬κ° λ°μνμ§ μλ κ°κ²°νκ³  μμ ν μ½λλ₯Ό μμ±ν  μ μλ€.**



μ¦, κ°μ μ μΌλ‘ `Null`μ λ€λ£° μ μλ€.



κ΅¬νλΆλ₯Ό μ΄ν΄λ³΄μ.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180316899.png" alt="image-20221018180316899"  />
</p>



λ°νν  λ, κ·Έλ₯ `return store.get(id);` μλ€λ©΄ null κ°μ΄ λ°νλμμ λ μλ¬κ° λ°μν  μ μλ€.



νμ§λ§, μ μ½λμ κ°μ΄ `Optional<Member>` λ‘ λ°νλλ κ²½μ°μλ μλ¬κ° λ°μνμ§ μλλ€.



**`Optional.ofNullable()` λ©μλλ₯Ό νμ©ν΄μΌνλ€.**



`findById` λ `id`λ₯Ό ν΅ν΄μ `Member` κ°μ²΄λ₯Ό κΊΌλ΄μ€λ λ©μλμ΄κ³  `store` μ κ²½μ° `id`κ° ν€κ°μΌλ‘ μ§μ λμ΄μμΌλ―λ‘



`store.get(id)` λ₯Ό ν΅ν΄μ ν΄λΉ `id`μ μνλ `member` κ°μ²΄λ₯Ό λΆλ¬μ€κ³  μ΄λ₯Ό `Optional.ofNullable`λ‘ κ°μΈμ£Όλ©΄ λλ€!


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180338387.png" alt="image-20221018180338387"  />
</p>



`findByName`μ κ²½μ° μ½κ°μ λ³΅μ‘νλ€.



λ¨Όμ  `store.values()`λ₯Ό ν΅ν΄ `store`μ μ μ₯λ λͺ¨λ  `member` κ°μ²΄λ₯Ό λΆλ¬μ¨λ€.



κ·Έ λ€μ, `filter()` λ©μλλ₯Ό μ°κΈ° μν΄μ `.stream()` μ λΆμ¬μ€λ€.



`.filter(μ‘°κ±΄ λλ€μ)` μ ν΄λΉ μ‘°κ±΄μ λ§μ‘±νμ§ μλ κ²λ€μ κ±Έλ¬μ€λ€.

`.filter(member -> member.getName().equals(name))` μ ν΅ν΄μ `store`μ μ μ₯λ `member`μ `name` λ€ μ€ μλ ₯ν nameκ³Ό κ°μ memberλ§ λ¨κ²λλ€.



`.findAny()` λ `stream`μ ν΅ν΄ κ±Έλ¬μ§ κ°μ μλ¬΄κ±°λ λ°ννλλ°, 
μμ κ°μ κ²½μ° μ€λ³΅λ μ΄λ¦μ΄ μλ€κ³  κ°μ λμ΄ μμΌλ―λ‘, μλ ₯ν `name`μ κ°μ§ `member`κ° μλ€λ©΄ λ°νν  κ²μ΄λ€.



------

## Test Case μμ±

<br>

μλμ° μΈνλ¦¬ μ μ΄μ κ²½μ°



νμ€νΈ μΌμ΄μ€λ₯Ό μμ±νκ³  μΆμ classμ μ΄λ¦μ ν΄λ¦­ν ν `ctrl + shift + t` λ₯Ό μλ ₯νλ©΄ μ½κ² test μμ€νμΌμ μμ±ν  μ μλ€.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180424603.png" alt="image-20221018180424603" style="zoom:80%;" />
</p>

create New Test λ₯Ό ν΄λ¦­νλ©΄ λλ€.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180439521.png" alt="image-20221018180439521" style="zoom:80%;" />
</p>

κ·Έλ¦¬κ³  νμ€νΈλ₯Ό ν΄λ³Ό λ©μλλ₯Ό μ νν ν ok λ²νΌμ λλ₯΄λ©΄ μμ€νμΌμ΄ μμ±λλ€.




------



νμ€νΈ νμΌ μμ± μ `Assertions` λ₯Ό λ§μ΄ μ¬μ©νκ² λλ€.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180511334.png" alt="image-20221018180511334"  />
</p>

`Assertions`μ μ μ©ν λ©μλλ₯Ό μ¬μ©νλ €λ©΄ import μμΌμΌ νλλ°, `junit`μ΄ μλ `assertj` λ₯Ό importν΄μΌνλ€!


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180530350.png" alt="image-20221018180530350" style="zoom:80%;" />
</p>

`Member result = repository.findById(member.getId()).get();`



μμ λ§μ§λ§μ `get()`μ΄ λΆλ μ΄μ λ, `findById`μ λ°νκ°μ΄ `optional`λ‘ κ°μΈμ Έ μκΈ° λλ¬Έμ, `get()` λ©μλλ₯Ό ν΅ν΄ κ°μ²΄λ§ κΊΌλΌ μ μλ€.



`Assertions.assertThat(κ°μ²΄1).isEqualTo(κ°μ²΄2);`



μ ν΅ν΄μ κ°μ²΄ 1κ³Ό κ°μ²΄ 2 κ° κ°μμ§ νμΈν  μ μλ€.







------

## AfterEach

<br>

νμ€νΈλ₯Ό νλ κ³Όμ μμ μ¬λ¬ λ©μλλ₯Ό νλ²μ νμ€νΈ νλ€λ³΄λ©΄, λ°μ΄ν°κ° κ²Ήμ³μ λ€λ₯Έ λ©μλ νμ€νΈμ μν₯μ μ€ μ μλ€. κ·Έλ¬λ―λ‘ νμ€νΈ λ©μλκ° λλ  λλ§λ€ λ©λͺ¨λ¦¬λ₯Ό λΉμμ£Όλ κ²μ΄ μ€μνλ€.



μ΄ μ­ν μ ν  μ μλ μλνμ΄μμ΄ `@AfterEach`μ΄λ€.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180601104.png" alt="image-20221018180601104"  />
</p>

`clearStrore()` λ©μλ μμλ κ°λ¨νκ² μ»¬λμ λ΄ λ°μ΄ν°λ₯Ό λͺ¨λ μ§μμ£Όλ `store.clear();` λ₯Ό κ΅¬ννλ©΄ λλ€.





------

## Extract Method μμ±

<br>

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180622550.png" alt="image-20221018180622550" style="zoom:80%;" />
</p>

`.ifPresent()` λ₯Ό ν΅ν΄μ λ§μ½ μ μ₯νλ €λ `member`μ `name`κ°μ΄ μ΄λ―Έ μ‘΄μ¬νλ `member`κ° `repository`μ μ΄λ―Έ μ‘΄μ¬νλ€λ©΄,



`IllegalStateException`μ΄λΌλ μλ¬λ₯Ό μΌμΌν€κ³  "μ΄λ―Έ μ‘΄μ¬νλ νμμλλ€." λΌλ μλ¬λ©μΈμ§λ₯Ό λμ°κ²λ κ΅¬ννμλ€.







λν, μ μ½λμμ μ€λ³΅νμμ κ°μμ΄ μλλλ‘ νλ λΆλΆμ λ©μλλ‘μ¨ λ°λ‘ μΆμΆνλ λ¨μΆν€κ° μλ€.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180636071.png" alt="image-20221018180636071" style="zoom:80%;" />
</p>



ν΄λΉ λΆλΆμ λλκ·Ένκ³ , μλμ° κΈ°μ€ `ctrl + alt + shift + t` λ₯Ό λμμ λλ₯΄λ©΄ μμ κ°μ μ°½μ΄ λμ€κ³ 



Extract Methodλ₯Ό ν΄λ¦­νκ³  λ©μλ μ΄λ¦μ μ§μ ν΄μ£Όλ©΄ λλ€.


<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180711445.png" alt="image-20221018180711445" style="zoom:80%;" />
</p>



νΈνκ² λ©μλλ‘μ μΆμΆν΄λ΄μλ€.



------

## assertThrows

<br>

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221018180728385.png" alt="image-20221018180728385" style="zoom:80%;" />
</p>



μ΄μ μ, μ€λ³΅λ νμμ΄ μλ€λ©΄, `IllegalStateException` μλ¬λ₯Ό μΌμΌν€κ³  "μ΄λ―Έ μ‘΄μ¬νλ νμμλλ€." λΌλ μλ¬λ©μΈμ§λ₯Ό λμ°κ²λ κ΅¬ννμλ€.



**`assertThrows`λ₯Ό μ¬μ©νλ©΄ try-catch λ¬Έμ μ­ν μ κ°κ²°νκ² ν  μ μλ€.**



λ¨Όμ  `IllegalStateException e = assertThrows(IllegalStateException .class, () -> memberService.join(member2))` λ₯Ό μ΄ν΄λ³΄μ.



`member1`κ³Ό `member2`μ μ΄λ¦μ λμΌνκ³  `member1`μ μ΄λ―Έ λ±λ‘μ΄ λμ΄μλ μν©μ΄λ€.



`assertThrows(μλ¬,μ‘°κ±΄μ) `μ μ‘°κ±΄μμ΄ μ€νλμμ λ μλ¬κ° λ°μνλμ§ νμΈν΄μ€λ€.





μ¦, μμ κ²½μ°μλ` ()-> memberService.join(member2)` λλ€μμ΄ μ€νλμμλ



`IllegalStateException `μλ¬κ° λ°μνλμ§ νμΈν΄μ€λ€.



μλ¬λ `e`μ μ μ₯μ΄ λκ³ ` getMessage()`λ₯Ό ν΅ν΄ μλ¬λ©μΈμ§λ₯Ό μΆμΆν  μ μκ³ 



μ΄λ₯Ό ν΅ν΄μ μ€λ³΅λ νμμ΄ κ°μμ μλν  κ²½μ°, μλ¬κ° λ°μνλμ§ μνλμ§ νμΈμ ν  μ μλ€.