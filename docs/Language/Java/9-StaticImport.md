---
layout: post
title: "Β· Static import"
nav_order: 9
parent : Java
grand_parent: π©π»βπ»Language
permalink: docs/Language/Java/StaticImport
---

# Static importλ¬Έμ μ΄μ©ν μ½λ κ°κ²°ν

<br>

{% capture some_var %}
```java
class Main{
    public static void main(String[] args) {
        System.out.println("Hello World");
        System.out.println("Hello World");
        System.out.println("Hello World");
        System.out.println("Hello World");
        System.out.println("Hello World");
        System.out.println("Hello World");
    }
}
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


λ¨Όμ , import λ¬Έμ κ΅¬μ±μ



`import java.ν¨ν€μ§λͺ.ν΄λμ€λͺ.λ©μλλͺ;` μΌλ‘ μ μΈμ νλ€.



μμ κ°μ μ½λκ° μλ€κ³  κ°μ ν  λ,



System.out.println μ μ¬μ©μ΄ λ§€μ° λΉλ²νλ°, μ΄λ₯Ό static import λ¬Έμ ν΅ν΄ κ°κ²°ν μμΌμ€ μ μλ€.



`import static java.ν¨ν€μ§λͺ.ν΄λμ€λͺ.*;` μ μΈμ νλ©΄,



νΉμ  ν΄λμ€μ λ©μλλ₯Ό μ¬μ©ν  λ, ν΄λμ€μ μ΄λ¦μ μλ΅ν  μ μλ€.

{% capture some_var %}
```java
import static java.lang.System.*; //static import λ¬Έ
class Main{
    public static void main(String[] args) {
        out.println("Hello World");
        out.println("Hello World");
        out.println("Hello World");
        out.println("Hello World");
        out.println("Hello World");
        out.println("Hello World"); // μλλ System.outμ΄μ§λ§, System μλ΅ κ°λ₯
    }
}
```
{% endcapture %}
{% assign some_var = some_var | markdownify %}
{% include fix_linenos.html code=some_var %}


μ½λκ° λλ¬΄ λ³΅μ‘ν΄μ§κ±°λ κ°κ²°νκ° νμν  κ²½μ°μ static import λ¬Έμ μ¬μ©νλ©΄ μ μ©ν  κ² κ°λ€.