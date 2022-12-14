---
layout: post
title: "Β· Security Chain antMatchers κ΄λ ¨ Exception Handling"
nav_order: 6
parent : SpringBoot
grand_parent: π©π»βπ»Language
permalink: docs/Language/SpringBoot/SecurityChainException
---

# Security Chain antMatchers κ΄λ ¨ Exception Handling
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

<br>

Security Chain μ€μ μμ, 

νΉμ  Roleλ§ Url μμ²­μ μ κ·Όν  μ μλλ‘ μ€μ ν λ (`.hasRole()` λμ΄μλ)  νΉμ `.authenticated()` λμ΄μλ urlμ `AUTHORIZATION` λ΄μ©μ΄ μμ μλ κ²½μ°

Chainμμ λ°μνλ μμΈλ₯Ό μ²λ¦¬νκΈ° μν΄μλ `AccessDeniedHandler` μ `AuthenticationEntryPoint` λ₯Ό μμλ°μ κ΅¬νν΄μΌνλ€.

μμλ‘ μλμ κ°μ΄ κ΅¬νν  μ μλ€.

<br>

---



## Error Response κ΅¬μ±

<br>



```java
@RestControllerAdvice
@Slf4j
public class ExceptionManager {

    public static void setErrorResponse(HttpServletResponse response, ErrorCode errorCode) throws IOException {

        // μλ¬ μλ΅μ½λ μ€μ 
        response.setStatus(errorCode.getHttpStatus().value());
        // μλ΅ body type JSON νμμΌλ‘ μ€μ 
        response.setContentType("application/json;charset=UTF-8");

        Response<ErrorDto> error = Response.error(new ErrorDto(errorCode.toString(), errorCode.getMessage()));

        //μμΈ λ°μ μ Error λ΄μ©μ JSONν ν ν μλ΅ bodyμ λ΄μμ λ³΄λΈλ€.
        Gson gson = new Gson();
        String responseBody = gson.toJson(error);

        response.getWriter().write(responseBody);
    }

}

@AllArgsConstructor
@Getter
public enum ErrorCode {

    TOKEN_NOT_FOUND(HttpStatus.UNAUTHORIZED, "ν ν°μ΄ μ‘΄μ¬νμ§ μμ΅λλ€."),
    FORBIDDEN_REQUEST(HttpStatus.FORBIDDEN, "ADMIN νμλ§ μ κ·Όν  μ μμ΅λλ€.");
    
    private HttpStatus httpStatus;
    private String message;
}
```

<br>

λ¨Όμ  μμ κ°μ λ©μλλ₯Ό κ΅¬ννλ€. μ¬λ¬κ³³μμ μ°μΌ μ μκΈ° λλ¬Έμ, static λ©μλλ‘ λ§λ€μλ€.

`HttpServletResponse` μ `status` μ `contentType` λ₯Ό μ€μ νκ³ 

`.getWriter.write()` λ©μλλ‘ μλ΅ν  bodyλ₯Ό JSONν ν΄μ μλ΅ν  λ΄μ©μ μ€μ νλ©΄ λλ€.

<br>

---

<br>

## AccessDeniedHandler κ΅¬ννκΈ°

<br>

```java
import likelion.sns.Exception.ErrorCode;
import likelion.sns.Exception.ExceptionManager;
import lombok.extern.slf4j.Slf4j;
import org.springframework.security.access.AccessDeniedException;
import org.springframework.security.web.access.AccessDeniedHandler;
import org.springframework.stereotype.Component;

import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@Component
@Slf4j
public class CustomAccessDeniedHandler implements AccessDeniedHandler {

    @Override
    public void handle(HttpServletRequest request, HttpServletResponse response, AccessDeniedException accessDeniedException) throws IOException {

        log.info("{}", accessDeniedException.getMessage());

        ErrorCode errorCode = ErrorCode.FORBIDDEN_REQUEST;

        ExceptionManager.setErrorResponse(response, errorCode);
    }
}
```

<br>

`handle` μ μ€λ²λΌμ΄λ©ν ν, μλ¬ λ°μμ μλ΅ν  μ½λλ₯Ό μ€μ νλ©΄ λλ€.

κ·Έλ¬λ©΄ `.hasRole` κ΄λ ¨ μμΈλ₯Ό νΈλ€λ§ν  μ μλ€.

<br>

---

<br>

## AuthenticationEntryPoint κ΅¬ννκΈ°

<br>

```java
import likelion.sns.Exception.ErrorCode;
import likelion.sns.Exception.ExceptionManager;
import lombok.extern.slf4j.Slf4j;
import org.springframework.http.HttpHeaders;
import org.springframework.security.core.AuthenticationException;
import org.springframework.security.web.AuthenticationEntryPoint;
import org.springframework.stereotype.Component;

import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@Component
@Slf4j
public class CustomAuthenticationEntryPointHandler implements AuthenticationEntryPoint {

    /**
     *  ν ν° μμ΄ Security Chain μμ autenticatedλ url μ κ·Ό μ, μλ¬ νΈλ€λ§
     */
    @Override
    public void commence(HttpServletRequest request, HttpServletResponse response, AuthenticationException authException) throws IOException {
        final String authorization = request.getHeader(HttpHeaders.AUTHORIZATION);

        if (authorization == null) {
            log.error("ν ν°μ΄ μ‘΄μ¬νμ§ μμ΅λλ€.");
            ErrorCode errorCode = ErrorCode.TOKEN_NOT_FOUND;

            ExceptionManager.setErrorResponse(response, errorCode);
        }
    }
}
```

<br>
`commence` λ₯Ό μ€λ²λΌμ΄λ©νλ©΄ λκ³ , authorizationμ΄ null μΈ μ‘°κ±΄λ¬Έμ μ¬μ©νμ¬, μμΈ μ²λ¦¬λ₯Ό νλ©΄ λλ€.

<br>

---
<br>

## νμΈ

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221228215114914.png" alt="image-20221228215114914" style="zoom:80%;" />
</p>

> ν ν° μμ΄ μμ²­ν  κ²½μ°

<br>

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221228214807777.png" alt="image-20221228214807777" style="zoom:80%;" />
</p>

> κΆν μλ μ¬μ©μκ° μμ²­ν  κ²½μ°



