---
title:  "[Spring 기본] IoC, DI, 컨테이너"
excerpt: "스프링의 기본 개념"
header:
  teaser: ../assets/images/20231225/spring.png
  
categories:
  - Spring
tags:
  - Spring
last_modified_at: 2023-01-23 T18:30:00-05:00
---

## 1. 제어의 역전 IoC(Inversion of Control)
  + 제어권이 뒤바뀐다는 의미이다.
  + 기존에는 클라이언트 구현 객체가 스스로 필요한 서버 구현 객체를 생성하고, 연결하고 실행했다.
  + 반면 AppConfig가 등장한 이후에 구현 객체는 자신의 로직을 실행하는 **역할**만 담당한다. 제어 흐름은 이제 AppConfig가 가져간다.
  + 프로그램의 제어 흐름을 직접 제어하는 것이 아닌 외부에서 관리하는 것을 제어의 역전(IoC)라고 한다.

    + 프레임워크 vs 라이브러리
      + 프레임워크가 내가 작성한 코드를 제어하고 대신 실행하면 프레임워크
      + 반면 내가 작성한 코드가 직접 제어의 흐름을 담당한다면 라이브러리

## 2. 의존관계 주입 DI (Dependency Injection)
  + ServiceImpl은 인터페이스에 의존한다. 실제 어떤 구현 객체가 사용될지는 모른다.
  + 의존관계는 정적인 클래스 의존 관계와, 실행 시점에 결정되는 동적인 객체(인스턴스) 의존 관계, 둘을 분리해서 생각해야 한다.
  + 애플리케이션 실행 시점(런타임)에 외부에서 실제 구현 객체를 생성하고 클라이언트에 전달해서 클라이언트와 서버의 실제 의존 관계가 연결되는 것을 **의존관계 주입**이라고 한다.
  + 의존관계 주입을 사용하면 클라이언트 코드를 변경하지 않고 클라이언트가 호출하는 대상의 타입 인스턴스를 변경할 수 있다.

## 3. IoC 컨테이너, DI 컨테이너
  + AppConfig처럼 객체를 생성하고 관리하면서 의존관계를 연결해 주는 것을 IoC컨테이너 또는 DI컨테이너라고 한다.
  + 어셈블러, 오브젝트 팩토리 라고 불리기도 한다.