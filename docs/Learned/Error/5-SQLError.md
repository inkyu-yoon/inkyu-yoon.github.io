---
layout: post
title: "Β· SQLException μλ¬"
nav_order: 5
parent : Error
grand_parent: πLearned
permalink: docs/Learned/Error/SQLError
---

# SQLException

<br>

```
java.sql.SQLException: Access denied for user 'root'@'218.155.35.113' (using password: YES)
```



gradleλ‘ λΉλν νμ€νΈ νμΌμ λλ¦¬λλ° μμ κ°μ μλ¬κ° λ°μνμλ€.

νμΈν΄λ³΄λ `application.yml` νμΌμ΄

```
server:
  servlet:
    encoding:
      force-response: true

spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: ${DB_HOST}
    username: root
    password: ${DB_PASSWORD}

  jpa:
    show-sql: true
    database-platform: org.hibernate.dialect.MySQL8Dialect
    database: mysql
    hibernate.ddl-auto: update



```

μμ κ°μ΄, datasourceκ° νκ²½λ³μλ‘ μλ ₯λ°κ²λ κ΅¬ννμκ³ , νμ€νΈ μμ€νμΌμμλ νκ²½λ³μκ° μ λ¬λμ§ μμμ λ°μν μ€λ₯μλ€.



λ°λΌμ, νμ€νΈ νμΌμ μ€ννλ μμ€ νμΌμμ νκ²½λ³μλ₯Ό μΆκ°ν΄μ€¬λλ, μ μμ μΌλ‘ μ€νλμλ€. (νΉμ, application νμΌμλ€ μ§μ  μλ ₯ν΄λ λλ€.)