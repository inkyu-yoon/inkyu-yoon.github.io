---
layout: post
title: "Β· JPA BaseEntity Auditing μ μ©"
nav_order: 9
parent : JPA
grand_parent: π©π»βπ»Language
permalink: docs/Language/JPA/JpaAuditing
---
# JPA BaseEntity Auditing μ μ©
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

<br>

## @EnableJpaAuditing μ μ©

<br>

'μμ±μΌμ', 'λ³κ²½μΌμ' μ κ°μ λκ°, μΈμ  λ°μ΄ν°λ₯Ό μμ±νκ³  λ³κ²½νλμ§μ λν λ°μ΄ν°λ μν°ν°μ κ³΅ν΅μ μΌλ‘ λ§μ΄ μ¬μ©λλ€.

μ΄λ¬ν κ°μ μλμΌλ‘ λ£μ΄μ£Όλ κΈ°λ₯μ JPAλ μ κ³΅νλ€.

<br>

```
@SpringBootApplication
@EnableJpaAuditing
```

`@SpringBootApplication` μ΄ μλ ν΄λμ€μ `@EnableJpaAuditing` μ΄λΈνμ΄μμ μΆκ°νλ©΄ λλ€.

μμ κ°μ λ°©λ²μ νμ€νΈ μ½λ μμ± μ, μ νλ¦¬μΌμ΄μ ν΄λμ€λ₯Ό νΈμΆνλ κ³Όμ μμ μμΈκ° λ°μν  μ μλ€λ λ¨μ μ΄ μλ€.

<br>

```java
@Configuration
@EnableJpaAuditing
public class JpaAuditingConfiguration{

}
```

μμ κ°μ΄ Configuration ν΄λμ€λ₯Ό νλ λ§λλ λ°©λ²μ΄ μλ€.

<br>



## BaseEntity μμ±

```java
@Getter
@MappedSuperclass
@EntityListeners(AuditingEntityListener.class)
public class BaseEntity {

    @CreatedDate
    @Column(updatable = false)
    private LocalDateTime createdAt;

    @LastModifiedDate
    private LocalDateTime updatedAt;
            
}
```

> - `@MappedSuperclass` : μμλ°λ μν°ν° ν΄λμ€μ λ§€ν μ λ³΄λ₯Ό μ λ¬
>
> - `@EntityListeners` : λ°μ΄ν°λ² μ΄μ€μ μ μ©νκΈ° μ  νλ‘ μ½λ°±μ μμ²­
>
> - `AuditingEntityListener` : μν°ν°μ Auditing μ λ³΄λ₯Ό μ£Όμνλ JPA μν°ν° λ¦¬μ€λ ν΄λμ€
>
> - `@CreatedDate` : λ°μ΄ν° μμ± λ μ§ μλμΌλ‘ μ£Όμ
>
> - `@LastModifiedDate` : λ°μ΄ν° μμ  λ μ§ μλμΌλ‘ μ£Όμ

<br>

## λ¦¬λ·° Entityμ μ μ©

```java
@Entity
@Getter
@NoArgsConstructor(access = AccessLevel.PROTECTED)
@ToString(callSuper = true)
public class Review extends BaseEntity {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    @Column(name = "review_id")
    private Long id;

    @Column(nullable = false)
    private String title;
    @Column(nullable = false, length = 500)
    private String content;
    @Column(name = "user_id", nullable = false)
    private String userId;

    @ManyToOne(fetch = FetchType.LAZY, cascade = CascadeType.ALL)
    @JoinColumn(name = "hospital_id")
    private Hospital hospital;

    public Review(ReviewCreateRequest reviewCreateRequest,Hospital hospital) {
        this.title = reviewCreateRequest.getTitle();
        this.content = reviewCreateRequest.getContent();
        this.userId = reviewCreateRequest.getUserId();
        this.hospital = hospital;
    }
}
```

> - `callSuper = true` λΆλͺ¨ ν΄λμ€ νλ ν¬ν¨νλ μ­ν  μν

<br>

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221208114816833.png" alt="image-20221208114816833" style="zoom:80%;" />
</p>

λ¦¬λ·° DB λ±λ‘ μ μ μ μ©λλ κ²μ λ³Ό μ μλ€.