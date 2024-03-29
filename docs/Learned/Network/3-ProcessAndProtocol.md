---
layout: post
title: "· 도메인 접속시 과정과 TCP/UDP의 특징"
nav_order: 3
parent : Network
grand_parent: 📚Learned
permalink: docs/Learned/Network/ProcessAndProtocol
---

# 도메인 접속시 과정과 TCP/UDP의 특징
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---


## https://www.google.com/ 을 접속할 때 일어나는 일

<br>

입력한 도메인 주소로 웹 사이트를 호스팅하는 서버의 IP 주소를 조회해야합니다.

IP 주소를 조회하는 과정은 매우 빨라야 하므로, 웹 브라우저는 도메인 주소 정보가 **①캐싱되어** 있는지 먼저 확인합니다.

캐싱된 기록이 없다면 ISP가 구축한 **②DNS**서버에 DNS 쿼리를 사용해서 해당 도메인 주소와 일치하는 IP주소를 전달받습니다.

찾은 IP주소에 **③TCP/IP 프로토콜**을 이용해 연결을 요청합니다. 신뢰할 수 있는 연결을 하기위해 TCP 3-way HandShake를 진행합니다.

연결이 된 후, 브라우저는 GET 요청으로 웹페이지를 요구합니다.

서버는 웹 브라우저에게 HTML파일로 응답하고 브라우저는 HTML을 랜더링하여 사용자에게 구글 화면을 보여줍니다.



### ① DNS 정보 캐싱

> CPU와 RAM 사이에 용량은 작지만 속도가 빠른 작은 메모리가 있는데, 이를 캐시라고 한다.
>
> 브라우저 캐시(DNS쿼리 사용) -> OS 캐시(systemcall 사용) -> 라우터 캐시 -> ISP 캐시 순으로 접근하려는 URL과 일치하는 정보가 저장되어 있는지 확인한다.
>
> DNS 서버에 요청하는 과정을 생략할 수 있게 된다.

<br>

### ② DNS

> 웹사이트의 도메인 주소와 IP주소를 알고 있는 서버이다.
>
> 브라우저가 DNS서버에 특정 도메인 주소를 전달하면, DNS 서버는 IP주소를 브라우저에게 알려준다.
>
> 브라우저는 전달받은 IP주소로 요청한다.

<br>

### ③TCP/IP 연결

> 1. 클라이언트는 요청 서버에 SYN 패킷을 보내 연결을 요청한다.
> 2. 요청을 수락한다면, 서버는 클라이언트에게 SYN 패킷과 ACK 패킷으로 응답한다.
> 3. 클라이언트는 ACK 패킷을 보내 연결 확립 응답을 보낸다.



<br>



## TCP와 UDP의 특징

<br>

TCP와 UDP는 전송계층에서 사용되는 프로토콜입니다.

포트 번호를 이용해 주소를 지정하고 데이터 오류검사를 위한 체크섬이 존재한다는 공통점이 있습니다.

<br>

TCP는 연결 지향적 프로토콜로서, 클라이언트와 서버가 연결된 상태에서 데이터를 주고받는 통신 방식입니다.(3-way handshake로 연결, 4-way handshake로 연결 해제)

고정된 네트워크 경로로 통신하기 떄문에

데이터 처리 속도를 조절하여 수신자의 버퍼 오버플로우를 방지, 네트워크 내의 패킷 수가 과도하게 증가하지 않도록 조절할 수 있습니다.

신뢰성 향상을 위한 연결과정 때문에, UDP보다 속도는 느리고 1:1 통신만 가능하며, 패킷 순서 보장 때문에 중간에 패킷이 유실되면 재전송해야해서 통신 속도가 저하될 수 있습니다.



UDP는 비연결형 프로토콜입니다.

패킷의 전송 순서가 바뀔 수 있고 데이터 수신 여부를 확인하지 않아 신뢰성이 낮다. 하지만 속도가 빠르다는 이점이 있어 동영상 스트리밍 서비스와 같은 곳에 사용됩니다.

참고로, 헤더 설정을 추가하면 커스터마이징이 가능하기 때문에 신뢰성을 보장받도록 할 수 있습니다. HTTP/3가 UDP기반 통신을 적용한 이유중에 하나로 볼 수 있습니다.

> HTTP/3 (웹 상 정보 전달 프로토콜) 는 QUIC(Quick UDP Internet Connection)이라는 프로토콜 기반이다.

<br>

## TCP 3-way / 4-way handshake

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20230222220547314.png" alt="image-20230222220547314" style="zoom:125%;" />
</p>

TCP는 연결 지향형 프로토콜이기 때문에, 송신측과 수신측이 연결되어야 합니다.

이를 위해서, TCP 헤더에 TCP 플래그가 있고, TCP 플래그에는 ACK · SYN · FIN 가 사용됩니다.

초기값은 0이고, 이 플래그로 3-way / 4-way handshake를 진행합니다.

1. 연결을 요청할 때, SYN 플래그로 요청을 보냅니다.

2. 연결을 받은 쪽은, 받은 SYN 플래그에 대한 응답으로 ACK 플래그와 연결 확립 요청을 위해 SYN 플래그를 보냅니다.

3. 연결을 처음에 요청했던 쪽은, 확립에 대한 응답으로 ACK 플래그를 보내는 것으로 3-way handshake는 마무리 됩니다.



연결을 종료하는 과정인 4-way handshake 에서는 FIN 플래그와 ACK 플래그를 사용합니다.

1. 연결 종료 요청을 FIN 플래그와 함께 보냅니다.

2. 종료 요청을 받은 쪽은 ACK 플래그로 응답합니다.

3. 요청 받은 쪽도 FIN 플래그로 연결 종료 확립 요청을 보냅니다.

4. 처음에 연결 종료 요청을 했던 쪽은, ACK 플래그로 연결 종료 확립 응답을 보내는 것으로 마무리 됩니다.