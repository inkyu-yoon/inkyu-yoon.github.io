---
layout: post
title: "Β· WebMvcTest μ€ NoSuchBeanDefinitionException μλ¬"
nav_order: 6
parent : Error
grand_parent: πLearned
permalink: docs/Learned/Error/WebMvcError
---

# WebMvcTest μ€ NoSuchBeanDefinitionException μλ¬ ν΄κ²°

<br>

```
java.lang.IllegalStateException: Failed to load ApplicationContext

	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContext(DefaultCacheAwareContextLoaderDelegate.java:98)
    ...
Caused by: org.springframework.beans.factory.UnsatisfiedDependencyException: Error creating bean with name 'hospitalController' defined in file [C:\Users\ikyoo\Desktop\λ©μμ΄μ¬μμ²λΌ λ°±μλ μ€μΏ¨\λ³μμΉμ¬μ΄νΈνλ‘μ νΈ\web\out\production\classes\hospital\web\controller\HospitalController.class]: Unsatisfied dependency expressed through constructor parameter 0; nested exception is org.springframework.beans.factory.NoSuchBeanDefinitionException: No qualifying bean of type 'hospital.web.service.HospitalService' available: expected at least 1 bean which qualifies as autowire candidate. Dependency annotations: {}
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContext(DefaultCacheAwareContextLoaderDelegate.java:90)
	... 72 more
Caused by: org.springframework.beans.factory.NoSuchBeanDefinitionException: No qualifying bean of type 'hospital.web.service.HospitalService' available: expected at least 1 bean which qualifies as autowire candidate. Dependency annotations: {}
	at org.springframework.beans.factory.support.ConstructorResolver.createArgumentArray(ConstructorResolver.java:791)
	... 90 more
```

<br>

WebMvc νμ€νΈ μ½λμμ μμ κ°μ μλ¬κ° κ³μν΄μ λ°μνλ€.

κ·Όλ°, μμνμ μ΄ λλ UserController λΌλ νμΌ νμ€νΈλ₯Ό μ€νμ€μ΄μλλ°, μκΎΈ, hospital κ΄λ ¨ μμ€ μ½λμμ μλ¬λ₯Ό λ°μμν€λ μν©μ΄μλ€.

ν΄κ²°μ±μ, `@WebMvcTest(νμ€νΈνκΈ°λ₯Ό μνλ ν΄λμ€.class)` λ₯Ό λͺμν΄μ£Όμ΄μΌ μλ¬λ₯Ό λ°μμν€μ§ μλλ€.

`@WebMvcTest(UserController.class)` μ΄μ²λΌ νμ€νΈ νκΈ°λ₯Ό μνλ ν΄λμ€λ₯Ό λͺμνλ μλ¬κ° λ°μνμ§ μκ² λμλ€.
