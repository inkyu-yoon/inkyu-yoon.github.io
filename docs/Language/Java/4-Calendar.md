---
layout: post
title: "ยท Calendar class ์ ๋ฆฌ"
nav_order: 4
parent : Java
grand_parent: ๐ฉ๐ปโ๐ปLanguage
permalink: docs/Language/Java/Calendar
---

# Calendar class ์ ๋ฆฌ
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---



## Calendar ํด๋์ค

<br>

- Calendar ํด๋์ค๋ ์ถ์ ํด๋์ค์ด๋ฏ๋ก ์ธ์คํด์ค๋ฅผ ์์ฑํ  ์ ์๊ณ , `getInstance()`๋ฅผ ์ฌ์ฉํด์ ๊ฐ์ฒด๋ฅผ ์์ฑํด์ผ ํ๋ค.


```
Calendar cal = Calendar.getInstance();
```




- ์๋ ๋ ์ง์ ์๊ฐ์ ๋ค๋ฃฐ ๋ชฉ์ ์ผ๋ก ์ ๊ณต๋์๋ Date ํด๋์ค๋ ์ ์ฌ์ฉ๋์ง ์์ง๋ง, Calendar๋ก ๋ณํํ๊ฑฐ๋ Calendar๋ฅผ Date๋ก ๋ณํํ  ์ค ์์์ผ ํ๋ค.



### 1. Calendar๋ฅผ Date๋ก ๋ณํ


```
Calendar cal = Calendar.getInstance(); // Calendar ํด๋์ค ํธ์ถ
Date day = cal.getTime(); // Date ํด๋์ค๋ก ๋ณํ
```


### 2. Date๋ฅผ Calendar๋ก ๋ณํ


```
Date d = new Date(); //Date ํด๋์ค ๊ฐ์ฒด ์์ฑ
Calendar cal = Calendar.getInstance(); // Calendar ํด๋์ค ํธ์ถ
cal.setTime(d); // Calendar์ ์๊ฐ์ d๋ก ๋ง์ถค
```



------

## Calendar ํด๋์ค์ ์ฌ์ฉ

<br>

{% capture some_var %}
```java
import java.util.Calendar;

class Main{
    public static void main(String[] args){

    Calendar cal = Calendar.getInstance(); 

    //๋จผ์  Calendar ํด๋์ค๋ฅผ cal ์ด๋ผ๋ ์ด๋ฆ์ผ๋ก ํธ์ถํ๊ณ 

    System.out.println(cal.get(Calendar.(static ์์)));
    //์์ ๊ฐ์ ๋ฐฉ์์ผ๋ก ์ฌ์ฉํ๋ฉด ๋๊ณ , static ์์ ์๋ฆฌ์ ๋ค์ด๊ฐ๋ ์ข๋ฅ๋ ๋งค์ฐ ๋ค์ํ๋ค.

    System.out.println(cal.get(Calendar.YEAR)); 
    //๋๋ 
    System.out.println(cal.get(Calendar.MONTH)); 
    //์ : 0~ 11 (11=12์)
    System.out.println(cal.get(Calendar.WEEK_OF_YEAR)); 
    //์ด ํด์ ๋ช์งธ ์ฃผ์ธ์ง
    System.out.println(cal.get(Calendar.WEEK_OF_MONTH)); 
    //์ด ๋ฌ์ ๋ช์งธ ์ฃผ์ธ์ง
    System.out.println(cal.get(Calendar.DATE)); 
    //๋ช ์ผ์ธ์ง
    System.out.println(cal.get(Calendar.DAY_OF_MONTH)); 
    //์ด ๋ฌ์ ๋ช์ผ์ธ์ง
    System.out.println(cal.get(Calendar.DAY_OF_YEAR)); 
    //์ด ํด์ ๋ช์ผ์ธ์ง 
    System.out.println(cal.get(Calendar.DAY_OF_WEEK)); 
    //์์ผ 1~7 (1:์ผ์์ผ)
    System.out.println(cal.get(Calendar.HOUR)); 
    //์๊ฐ (0~11)
    System.out.println(cal.get(Calendar.HOUR_OF_DAY)); 
    //์๊ฐ(0~23)
    System.out.println(cal.get(Calendar.MINUTE)); 
    //๋ถ
    System.out.println(cal.get(Calendar.SECOND)); 
    //์ด
    System.out.println(cal.getActualMaximunm(Calendar.DATE)); 
    //์ด ๋ฌ์ ๋ง์ง๋ง ์ผ
    }
}
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


Calendar ํด๋์ค๋ฅผ ์์ฑํ๋ฉด ๊ธฐ๋ณธ๊ฐ์ผ๋ก ์ค๋ ๋ ์ง์ ์๊ฐ์ด ์ ์ฅ๋๋ค.



`cal.get()`์ด ๋ฐ์ดํฐ๋ฅผ ์ฝ์ด์ค๋ ๊ฒ์ด๋ผ๋ฉด,



`cal.set()`์ผ๋ก ๋ฐ์ดํฐ๋ฅผ ์ ์ฅํ  ์ ์๋ค.



๋ง์ฝ 2022-03-01์ ๋ ์ง๋ฅผ ๊ฐ์ง Calendar ํด๋์ค๋ฅผ ์์ฑํ๊ณ  ์ถ๋ค๋ฉด ์๋์ ๊ฐ์ด ํ๋ฉด ๋๋ค. (Month ํ๋๋ 1์์ด 0)

{% capture some_var %}
```java
import java.util.Calendar;

class Main{
    public static void main(String[] args){

    Calendar cal = Calendar.getInstance();

    cal.set(2022,2,1);

    System.out.println(cal.get(Calendar.YEAR));
    //2022์ด ์ถ๋ ฅ๋  ๊ฒ
    System.out.println(cal.get(Calendar.MONTH));
    //2์ด ์ถ๋ ฅ๋  ๊ฒ
    System.out.println(cal.get(Calendar.DATE));
    //1์ด ์ถ๋ ฅ๋  ๊ฒ
    }
}
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


`cal.add()` ์ `cal.roll()`์ ์ฌ์ฉํ๋ฉด ์ํ๋ ํ๋์ ๋ฐ์ดํฐ๋ฅผ ์ถ๊ฐํ๊ฑฐ๋ ๋บ ์ ์๋ค.


{% capture some_var %}
```java
import java.util.Calendar;

class Main{
    public static void main(String[] args){
    Calendar cal = Calendar.getInstance();
    cal.set(2022,0,31);//2022๋ 1์ 31์ผ๋ก ์ง์ ํ์๋ (MONTH ํ๋๋ 0๋ถํฐ ์์ํ๋ฏ๋ก 0์ด 1์์ด๋ค.)

    cal.add(Calendar.YEAR,1);
    //YEAR์ +1 ์ ํด์ค๋ค.
    cal.add(Calendar.MONTH,-1);
    //MONTH ์ -1 ์ ํด์ค๋ค.

    cal.roll(Calendar.DATE,1);
    //roll์ด๋ฏ๋ก MONTH์๋ ์ํฅ์ ์ฃผ์ง ์๊ณ  DATE๋ง 1๋ก ๋ณํ  ๊ฒ
    }
}
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}

add๋ ์๋ฅผ ๋ค์ด 7์31์ผ ์ธ ์ํฉ์์ DATEํ๋์ +1์ ํด์ฃผ๋ฉด MONTH ํ๋์๋ ์ํฅ์ ์ฃผ์ด 8์1์ผ์ด ๋์ง๋ง,



rollํ๋๋ ๋ค๋ฅธ ํ๋์๋ ์ํฅ์ ์ฃผ์ง ์์์ 7์1์ผ์ด ๋๋ค.