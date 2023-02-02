---
layout: post
title: "· CPU의 구성과 버스의 종류"
nav_order: 2
parent : 운영체제
grand_parent: 📚Learned
permalink: docs/Learned/OS/OSCPUandBus
---

# CPU의 구성과 버스의 종류
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---





<br>

## 1. CPU의 구성

<br>

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20230117004319232.png" alt="image-20230117004319232"  />
</p>

- 제어장치 : 작업을 지시한다. 명령 레지스터에서 읽어들인 명령어를 해석하고, 해당하는 장치에 제어 신호를 보낸다.
    - fetch : 연산을 하기 위해, 메모리에서 데이터를 로드하여 CPU에 있는 레지스터(연산에 필요한 데이터 임시 저장소)에 적재한다.
    - indirect : 메모리에서 가져온 데이터가, 데이터가 존재하는 것이 아닌 주소값이라면, 그 주소를 이용해서 데이터를 얻는 과정을 한번 더 진행한다.
    - decode : 명령어를 해석한다.
    - execute : **해석한 명령**과 가져온 **데이터**로 CPU는 산술 연산 장치에게 어떤 기능을 수행하라고 지시한다.
- 산술 연산 장치 : 제어장치의 명령에 따라 실제로 연산(산술, 논리, 관계, 이동 등)을 수행한다.



## 2. 폰노이만 구조

<br>

프로그램 저장 방식이 고안되기 이전의 **모든 기계들은 하나의 목적 혹은 역할**을 하도록 고안되었다. 따라서, 새로운 작업을 할때마다, 회로를 물리적으로 바꿔야 했다.

하지만, 폰 노이만 구조는 어떤 프로그램을 메모리 영역에 저장해서 실행하느냐에 따라 그 기능이 달라지며 컴퓨터의 범용성의 원천이 되었다.

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20230117000405675.png" alt="image-20230117000405675" style="zoom:67%;" />
</p>

**모든 프로그램(모든 음식 재료는)은 저장장치(냉장고)에서 가져와서 메모리(도마)에 올라와야 CPU가(요리사가) 실행(요리)할 수 있다.**

-> 즉, CPU는 메모리 영역이 없으면, 저장장치에 어떤 프로그램이 있던 실행시킬 수 없고, 저장장치에 있는 프로그램이 메모리 영역에 올라와야 실행시킬 수 있다.
왜냐하면, 메모리 영역에 프로그램을 실행시킬 수 있는 명령어나 데이터가 있기 때문이다.

> 메모리가 크면 한번에 처리할 수 있는 작업량이 많아져서, 작업 속도가 빨라진다. => 도마가 크면 재료를 한번에 많이 손질할 수 있어 요리를 빨리할 수 있다.
>
> CPU 성능이 좋으면 작업속도가 빨라진다. => 요리사가 능숙해서 요리를 빨리한다.





## 3. 버스의 종류

<p align="center">
<img src="https://raw.githubusercontent.com/buinq/imageServer/main/img/image-20230117010712393.png" alt="image-20230117010712393" style="zoom: 67%;" />
</p>

<br>

버스는 CPU와 메모리, 주변장치 간에 데이터를 주고받을 때 사용한다.

1. 제어 버스 : 어떤 작업을 할지 **지시하는 신호**가 이용 (지시한 신호가 잘 도착했는지, 오류는 없는지 결과 신호를 받는다.)
2. 주소 버스 : 메모리의 데이터를 읽거나 쓸 때 어느 위치에서 작업할 것인지 **알려주는 위치 정보**가 이용

> 주소 버스가 대표적인 단방향 버스인데, CPU에 있는 메모리 주소 레지스터는 주소버스로 어느 위치에서 작업하라고 신호를 보내기만하는데, 이 신호를 메모리나 주변장치는 받아서 어디서 작업할지 알게된다.
>
> 즉, 신호를 보내기만하고 다시 받지 않으므로 단방향 버스이다.

3. 데이터 버스 : 제어 버스가 **어떤 작업**을 할지 신호를 보내고, 주소 버스가 **위치 정보**를 전달하면 **데이터가 데이터 버스를 이용**하여 목적지로 이동 (연산에 필요한 데이터를 가져올때도 있고, 연산이 끝난 데이터를 보내는 경우도 있다.)





