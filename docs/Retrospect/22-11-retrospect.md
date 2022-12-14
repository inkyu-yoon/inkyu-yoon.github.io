---
layout: post
title: "· 22년 11월 회고"
nav_order: 4
parent : ✍🏻회고
permalink: docs/Retrospect/November22
---

# 11월 돌아보기
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---



## 알고리즘 공부 현황 👨🏻‍💻

<br>

백준 알고리즘을 꾸준히 공부한 결과로 목표하던 골드에 달성했다! 🥇

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221204010735995.png" alt="image-20221204010735995" style="zoom:80%;" />
</p>

물론, 등급은 등급일 뿐이지만, 알고리즘 공부를 하면서 세웠던 1차 목표인 골드 랭크를 달성하니 뿌듯했다.

그렇게 11월 중순까지 백준으로 열심히 공부하다가, 요즘에는 프로그래머스 사이트로 알고리즘 공부를 하기 시작했다.

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221204010614454.png" alt="image-20221204010614454" style="zoom:50%;" />
</p>

이유는, 나는 11월 12일에 프로그래머스에서 진행하는 LG CNS에서 주최하는 코딩테스트가 있었고, 자기소개서나 이력서 제출 없이 시험을 볼 수 있어서 시험을 치뤘었다.(물론 탈락했지만..)

나는 코딩 테스트를 한번도 경험해본 적이 없었고, 아직 코테 준비를 했다고 말할 만큼 알고리즘 문제를 많이 풀어보거나 깊이 있게 공부를 안했음에도 시험삼아 코테를 경험해보고 싶어서 지원해서 시험을 봤다.

역시나, 쉽고 간단한 기초 문제만 풀어보던 나에게는 코딩테스트가 엄청나게 어려웠다. (그래도 문자열 문제 1개는 풀어서 뿌듯했다..정답인지는 모르지만..)

그리고, 평소에는 인텔리제이 IDE의 자동 완성 기능을 통해서 문제를 스피디하게 풀다보니, IDE를 사용할 수 없었던 이번 시험이 특히나 어색하고 낯설고 어려웠다.

여러 문제를 풀어보면서, 이런 상황을 생각해보지 못했고, 시험 삼아 봤던 이번 시험이 큰 교훈을 준 것 같다.

결과적으로, 프로그래머스와 백준 문제 스타일이 굉장히 다르다고 느꼈고,  이번 시험을 보고나서 부터는 프로그래머스로 알고리즘 공부를 하고 있다.

또한 최대한 IDE는 사용하지 않고, 프로그래머스 사이트 화면으로만 문제를 풀어보고 있다.

IDE없이 문제를 풀어보면서 컬렉션을 초기화하는 과정과 컬렉션 메서드나 import하는 과정 등등을 그동안 너무 생각없이 자동 완성으로 사용했었구나 깨달았다...ㅎㅎ

11월 중순부터는 갑자기 어려워진 스프링 수업 내용과 JPA와 Querydsl 내용이 알고리즘 공부보다는 우선시 해야할 것 같아서 1일 1알고리즘은 지키지 못했지만,

12월 부터는 다시 꾸준하게 시간을 투자해서 문제를 풀어봐야겠다.

---

<br>

## 목표했던 인프런 강의 수료 🍃

<br>

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221204012039040.png" alt="image-20221204012039040" style="zoom:67%;" />
</p>

11월은 인프런으로 결제한 강의를 모두 완주했다는 점에서 스스로 뿌듯함을 느낀다.

스프링도 어색하고 낯설어하던 나인데...ㅎ 칭찬해~

특히, JPA 강의는 JPA 기본편, 실전, 활용 1/2 , Querydsl 총 6개의 강의를 모두 들으면서 JPA와 매우매우매우 친해질 수 있었다.

JPA 강의들을 완강해보고 나서 느낀점은,

김영한님이 추천한 야생형 로드맵은 활용 1/2 편을 먼저 듣고 JPA 기본편 강의를 들으라고 추천을 하셨지만, 나는 약간 생각이 다르다.

김영한님 말대로 '일단 부딪혀보자' 라고 생각해서 활용 1편을 들었는데, 진짜 무슨 말인지 하나도 모르겠고 의미없는 강의 시간만 채우는 느낌이 들었다.

그래서 '나는 야생형이 아니라 학자형인가...?' 생각이 들 정도였다.

일단은, 기본편 수업으로 다시 돌아가서 영속성 컨텍스트와 하이버네이트의 작동 원리를 대략적으로 파악하니, 활용편 수업 내용이 그제서야 이해가 가기 시작했다.

따라서, 나는 [ 기본편(~연관 관계 매핑까지) -> 활용 1/2 -> 실전 querydsl -> 실전 스프링 데이터 JPA -> 기본편 남은 강의 마무리 ] 순으로 수업을 듣는것이 베스트일 것 같다는 생각이 들었다.

아무튼 연관관계 매핑까지는 원리를 알아야, 활용 1/2 수업에서 시너지 효과를 느낄 수 있고,

EntityManager 의 createQuery 기능 보다 Querydsl의 queryfactory 로 쿼리문을 작성하는게 이점이 상당히 많기 때문에, querydsl 수업을 먼저 듣고 JPA의 createQuery 기능 방법을 배우는 것이 더 좋지 않았을까? 생각이 들었다.



Anyway! 11월에는 JPA 관련 강의를 1회독 했고, JPA 기본편은 2회독을 하면서 복습을 했다. 12월에는 Querydsl 수업을 한번 더 들어서 내용을 정리해볼 생각이다. (그 외 다른 JPA  강의는 여유가 있으면...? 할 생각이다.)

이 JPA 강의들을 모두 듣느라 11월에는 다른 공부에 치중을 잘 못했는데, 강의를 일단 다 끝냈으니 12월에는 JPA를 틈틈히 복습하면서 스프링부트 + 도커 공부에 힘을 써볼 생각이다.

---

<br>

## 스터디 그룹 👨‍👩‍👦‍👦

<br>

11월 20일에는 멋사 스터디원들과 오프라인 만남을 했다!

원래, 11월에 한번 보려고 시간을 맞추고 있던 와중 멋쟁이 사자처럼 측에서 오프라인 모임시 식사권 지원해주는 이벤트를 마침! 진행하여 타이밍이 좋았다!

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221204020521025.png" alt="image-20221204020521025" style="zoom:67%;" />
</p>

멋사에서 무려 7만원 식사권을 지원해줬지만, 4명이서 9만원이 나왔다는 사실...ㅎㅎ!

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221204020618110.png" alt="image-20221204020618110" style="zoom: 20%;" />
</p>

아쉽게, 스터디원 1명이 코로나 때문에 참석하지 못해 5명이서 만났지만, 좋은 시간을 보냈다~

공부 이야기 뿐만 아니라 이런 저런 사는 이야기 하면서..? 시간이 부족하다고 느낄 정도로 떠들었다.ㅎㅎ

스터디원들 모두 장점이 확실한 친구들이고 좋은 사람들 끼리 모이게 된 것 같아서 스터디 장으로서 다행이라고 생각했고 좋았다 👍🏻 (다들 인싸들임)

멋사 스쿨에 들어온 가장 큰 이유인 '지식보다 좋은 인연을 얻어가자' 를 어느정도 달성한 것 같다!

이번, 오프라인 모임을 계기로 더 가까워진 사이게 된 것 같아 좋고, 멋사 수료 이후까지 서로 도움이 되는 좋은 인연을 이어갔으면 좋겠다.

---
<br>

## 운동하기 🏃🏻‍♂️🧗🏻‍♂️

<br>

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221204021316801.png" alt="image-20221204021316801" style="zoom: 33%;" />
</p>

11월 매주 5km 이상 뛰기 완료했다!

체력 관리 겸 달리면 기분도 좋아지고 상쾌해서 재밌다. 🏃🏻‍♂️🏃🏻‍♂️

그리고 매주 클라이밍도 하러다녔다. ㅎ 실내 스포츠라서 요즘 같이 밖에서 운동하기 추운 날 하기 좋은 취미이다!!

단순 재미만 있는 것 뿐만 아니라 근력도 많이 사용하게 돼서, 운동 효과로도 매우 좋은 것 같다.

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/ESgoocPU4AARc_F.jpg" style="zoom:80%;" />
</p>

나는 운동을 좋아해서 거의 매일 운동하는데, 이 짤이 약간 이해가 되는 느낌...

너무 빡세게 운동하면 녹초가 되는.... 나 체력 좋아지고 있는거 맞....지...?


아무튼 최근, 갑자기 추워져서 5km 뛰러 나갔는데,

손 시립고 허벅지 얼어있고 귀 아프로 공기도 너무 차서 숨 쉴 때 불편하고 그렇다고 마스크를 끼고 뛰자니 마스크에 습기 차고... 등등....이유로 

날 풀릴때 까지 달리기는 일단 쉬기로 했다..ㅎ (건강이 악화되는 느낌...ㅎ)

얼른 날 풀려서 자전거도 타러 가고... 싶....다...🚴🏻‍♀️

---

<br>

## 마무리 😊

<br>

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20221204022150624.png" alt="image-20221204022150624" style="zoom:80%;" /></p>

벌써 50% 진행한 것 실화...?

11월을 돌이켜보니, 놀기도 열심히 논 것 같고 공부도 나름? 열심히 한 것 같다.

원래는 개발 공부 시작하면, 친구도 안 만나고 공부만 하려고 했는데... 성격 상 쉽지 않다...ㅎ

놀 때 스트레스도 풀고 재충전 한 덕분에 공부에 더 집중할 수 있었다고 스스로 합리화를 해본다...ㅎ

<br>

아 그리고, 최근에 멋사 측에서 프로젝트 팀 구성을 위해서 설문조사를 실시했다.

12월 14일에 멋사에서 진행하는 수업이 마무리가 된다. 그리고 개인 프로젝트와 팀프로젝트가 시작된다.

특히, 팀 프로젝트가 어떻게 진행될 지, 그동안 궁금했었는데 팀을 배정해주나보다.

그래서 더욱 앞으로 다가올 12월이 어떻게 흘러가게 될지 어떤 일이 펼쳐질지.. 모르겠다.

사실 지금까지 배운 내용으로 어떻게 접목시켜서 어떤 결과물을 만들 수 있을지 모르겠고, 특히 완성도를 어느정도로 채울 수 있을까도 걱정이 된다.

일단 나부터 열심히 내 할 것 하면서, 충실하게 내 시간을 잘 사용하면 12월도 잘 보낼 수 있지 않을까 싶다.

2023년을 앞두고 보내는, 2022년 마지막 1달을 후회없이 보내야겠다.



+한국 월드컵 16강 진출!!!🎉(16강전 봐야해서 또 공부할 시간 줄어들겠네..ㅎ)



