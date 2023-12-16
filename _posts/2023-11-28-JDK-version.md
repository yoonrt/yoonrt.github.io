---
title:  "[JAVA] JDK 버전 전환하기"
excerpt: "JDK 버전을 환경에 따라 전환하기."
header:
  teaser: /assets/images/20231128/2023-11-28-1-teaser.jpg

categories:
  - JAVA
tags:
  - JAVA
  - JDK
last_modified_at: 2023-11-28T20:30:00-05:00
---
기존에 마인크래프트 라는 게임 때문에 자바 버전 17을 사용하고 있었는데, 집에서 자기계발 겸 개인 프로젝트를 시작하려고 스프링부트 2.7 버전을 기준으로 프로젝트를 생성하였다. 문제는 스프링부트 2.* 버전은 자바 버전 8밖에 지원을 하지 않는다.  

사실 스프링부트 3.* 버전을 사용하면 자바 버전 17을 사용하면 되지만 일단은 안정적인 버전을 기준으로 프로젝트를 진행 할 예정이기 때문에 스프링부트 2.7 버전으로 생성하였다.  
찾아보니 명령어를 생성해서 JDK 버전을 전환할 수 있는 방법이 있어 게시해 둔다.  
자바 환경변수를 설정했다는 가정 하에 진행한다.  
  
## 1. JDK 설치
https://www.oracle.com/java/technologies/downloads/archive/

위 사이트의 Java SE downloads에서 Java SE 8 (8u211 and later) 버전으로 설치 하였다.  

![20231128_JDK3](https://github.com/yoonrt/springapp_repo/assets/63996835/34ac8981-b721-4083-8cbe-41b0a041a4e6)

개발환경이 64비트 윈도우이기 때문에 Windows x64 Installer를 받아서 설치해준다.  
경로는 기존 자바 버전 17이 설치되어 있는 'C:\Program Files\Java'에 설치를 해 주었다.  

## 2. 명령어 파일을 생성할 폴더 생성
![20231128_JDK2](https://github.com/yoonrt/springapp_repo/assets/63996835/b3a218f2-1204-4b28-85e6-0769577e90c7)

JDK가 설치되어 있는 경로에 scripts 폴더를 생성해 주었다.  

## 3. 환경변수 추가
![20231128_JDK4](https://github.com/yoonrt/springapp_repo/assets/63996835/ad5bd55e-4e24-485d-83ad-da50054f6dd6)  

환경변수의 시스템 환경 변수에서 Path 변수에 위에서 생성한 폴더의 경로를 지정해준다.  

## 4. bat 파일에 명령어 생성
사용할 버전마다 bat 파일을 생성해야 한다.  
```
@echo off
set JAVA_HOME=C:\Program Files\Java\jdk-1.8
set Path=%JAVA_HOME%\bin;%Path%
echo Java 8 activated
```
<div style="text-align: center"> java8.bat </div>

```
@echo off
set JAVA_HOME=C:\Program Files\Java\jdk-17
set Path=%JAVA_HOME%\bin;%Path%
echo Java 17 activated
```
<div style="text-align: center"> java17.bat </div>

## 5. 생성한 bat 파일 실행
![20231128_JDK5](https://github.com/yoonrt/springapp_repo/assets/63996835/453baa0b-9ba5-4eec-a64e-1f5497e40356)
이제 명령 프롬프트 창에서 아까 생성했던 bat 파일의 이름을 입력해주면 버전을 전환할 수 있다.