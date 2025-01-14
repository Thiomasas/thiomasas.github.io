---
published: true
layout: single
title: ""
classes: wide
category: Skript
sidebar:
    nav: "skript" 
tags: 
  - skript
---

## 스크립트를 시작해보자

자 지금부터 스크립트 강좌를 시작하겠다. 저번은 일종의 오리엔테이션이었다고 생각하고, 이번에는 스크립트를 만들고, 개발하려면 반드시 필요한 스크립트의 매커니즘에 대하여 알아봅시다. 그러나 스크립트의 특성상 자바의 문법과 마인크래프트 커맨드, 영문법이 간략히 섞여있는 언어이기에, 비전공자 또는 코딩에 관심이 없는 사람도 쉽게 응용하는 자신의 모습을 바라볼 수 있을 것입니다.




## 스크립트란 무엇인가

스크립트란, 마인크래프트의 대부분의 요소들을 서버의 관리자가 직접적인 간섭을 통해 조작할 수 있게 환경을 구축해주는 일종의 API 격 미니 플러그인입니다. 또한 기본적인 언어적 구조가 Java 또는 kotlin 과 같은 커리큘럼식 개발 언어와 다른, Javascript 나 HTML 과 같은 스크립팅 언어이기 때문에 초보자의 접근이 매우 쉽습니다. 그러나 자바를 기반으로 한 마인크래프트를 기반으러 한 스크립트 API를 기반으로 한 스크립트 개별 파일의 연산 속도는 앞서 말했듯, 자바, 마인크래프트, 스크립트 API에 모두 선언해야 하기에, 연산속도 및 처리속도가 매우 느립니다. 그리하여 필자는 왠만해선, 플러그인 개발을 추천하지만, 자바를 기반으로 한 플러그인 개발은 매우 어렵고 접근 난이도가 매우 높기에 자신의 친구들과 놀기위한 서버라면 스크립트 개발을 추천합니다.



## 스크립트의 매커니즘 및 작동방식

스크립트의 매커니즘에는 크게 2가지 작동방식이 있습니다.
  
 ~~~diff
 + 이벤트 스크립트
 
 + 커맨드 스크립트
 ~~~
 
 
 
## 이벤트 스크립트

 코드가 실행되려면, 게임이나 서버에서 어떤 일이 발생해야합니다. 이렇게 서버또는 게임내에서 발생하는 이벤트를 가지고 코드를 작동시키는 구문을 이벤트 스크립트 또는 이벤트 트리거라고 합니다. 이벤트 스크립트의 예시적인 구문을 봅시다.
 
 ~~~js
 
 on join:
    send "Welcome to world of Skript" to player
 ~~~

라는 구문이 있다고 가정합시다. 위를 해석해본다면,

~~~js
# 플레이어가 서버에 입장헸을때
on join:
    # "Welcome to world of Skript" 라는 메세지를 플레이어에서 보낸다
    send "Welcome to world of Skript" to player
~~~

라고 할 수 있습니다. 위처럼 특정 이벤트가 발생했을 시 코드를 작동시키는 구문을 이벤트 스크립트라고 합니다.



## 커맨드 스크립트

그러나 모든 행동에서 코드를 발동한다면, 가만히 있는 상태에서 코드를 발동시킬 수 없다는 큰 한계가 있습니다. 또한 커맨드의 경우 [ on command ] 의 이벤트 구문으로 해결 할 수 있겠지만, 커맨드 인자를 하나하나 지정하는 것은 매우 비요율적일 수 밖에 없습니다. 그래서 커맨드를 등록하고 객체로 지정해 커맨드를 발동시킬 시 해딩 구문을 작동시키는 구문을 커맨드 스크립트 라고 합니다. 예시 코드를 봅시다.

~~~js

command /test.command:
    trigger:
        send "Welcome to world of Skript" to player
~~~
라는 구문이 있다고 가정합시다. 위를 해석해본다면,

~~~js

# /test.command 라는 커맨드를 등록하고, 실핼했을 때
command /test.command:
    # 커맨드 실행 트리거
    trigger:
        # "Welcome to world of Skript" 라는 메세지를 플레이어에게 보낸다.
        send "Welcome to world of Skript" to player
~~~
라고 해석할 수 있습니다. 위처럼 특정 커맨드를 등록하고, 실행했을 때 아래 구문을 발동시키는 것을 커맨드 스크립트라고 합니다.

## 기타 팁들

스크립트가 물론 다른 개발 언어에 비해 매우 쉽고, 영문법이 섞여 있는 것은 사실입니다. 그러나 스크립트도 엄연한 개발언어의 한부분이다보니 개발할때 주의해야 할 점 또는 기타 팁들이 있습니다.


다른 사람에게 자신의 코드를 이해하기 위해, 디버깅을 조금 더 쉽게 하기 위해 쓰는 주석또한 스크립트에서 사용할 수 있습니다. 대부분의 개발언어의 주석 접두어는 // 이지만, 스크립트의 주석 접두어는 # 입니다.

또한 스크립트의 색코드는 Chatcolor.RED 등과 같이 마인크래프트 API 를 사용하는 것이 아닌, 마이크래프트 Json 문법에서 사용하는 & 접두어 색코드를 사용합니다. 그에대한 참고는 아래첨부되어 있는 사진을 참고 해주세요.

![색코드](https://blog.kakaocdn.net/dn/cpHVPO/btqGUdFL5rz/RkkI65NDxR5d1L61KEx8t0/img.jpg)

또한 스크립트는 서버가 켜져있을 때에도 수정및 저장이 가능합니다. 그러나 매번 새로 리로드를 해주어야 합니다. 만약 당신이 서버를 실행하는 도중 오류를 발견하여 즉석에서 개발툴을 켰다고 가정합시다. 개발툴에서 수정을 했다면 절대 그냥 다음작업으로 넘어가지 말고, Ctrl + s 또는 <저장 - 저장하기> 버튼을 눌러 파일을 저장 및 새로고침 주세요. 그런다음, 서버의 게임화면으로 넘어오거나, 콘솔을 켜서, /sk reload 파일명.sk 를 입력해주세요. 그렇게 한다면 성공적으로 새로 저장된 스크립트 파일이 리로드 될 것입니다.



## 마치며

이번 강좌에서는 스크립트의 매커니즘에 대해 알아보았습니다. 다음 강좌부턴 본격적인 개발 강좌로 넘어가도록 하겠습니다.
