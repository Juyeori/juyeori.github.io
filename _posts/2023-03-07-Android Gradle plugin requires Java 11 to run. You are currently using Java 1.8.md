---
title: Android Gradle plugin requires Java 11 to run. You are currently using Java 1.8., 리액트 네이티브 에러
layout: post
description: 자바 버전, 환경 변수, 리액트 네이티브 에러
tags: React-Native, Android-Studio, 앱개발, 자바버전, 환경변수

categories: [React, React-Native]
---

## 아래와 같은 에러 처리 방법이다!
Android Gradle plugin requires Java 11 to run. You are currently using Java 1.8. <br/>
Your current JDK is located in C:\Scoop\apps\temurin8-jdk\current\jre <br/>
You can try some of the following options:
- changing the IDE settings. 
- changing the JAVA_HOME environment variable. 
- changing `org.gradle.java.home` in `gradle.properties`.

> 이 내용을 구글링하면, 안드로이드 스튜디오에서 아래 사진과 같은 그래들 관련 jdk를 11로 설정하라는 포스팅이 되게 많았다.
![그래들오류](/assets/img/%EA%B7%B8%EB%9E%98%EB%93%A4%EC%98%A4%EB%A5%98.png)
![그래들오류](/assets/img/%EA%B7%B8%EB%9E%98%EB%93%A4%EC%98%A4%EB%A5%982.png)
그래서 똑같이 해봤는데, 계속 똑같은 에러가 나온다.

~~또 나만 안되는거다!!!!!~~

<br/>
이리저리 찾아봤지만, 결국엔 환경변수 문제였다.
<br/>

## 해결 방안

아래 사진과 같이 사용자 변수의 `JAVA_HOME` 과 시스템 변수의 `JAVA_HOME`의 디렉토리를 같게 해주면 된다. <br/>
그리고 이 변수 경로에 들어가는 jdk는 11버전이여야 하는 것 같다!

![그래들오류](/assets/img/%EA%B7%B8%EB%9E%98%EB%93%A4%EC%98%A4%EB%A5%98_%ED%99%98%EA%B2%BD%EB%B3%80%EC%88%98.png)

이렇게 설정하면, jdk의 버전이 맨처음 사진과 같이 18로 나오는데도 정상적으로 리액트 네이티브 빌드가 된다....!
![그래들오류](/assets/img/%EA%B7%B8%EB%9E%98%EB%93%A4%EC%98%A4%EB%A5%98_%EB%B9%8C%EB%93%9C%EC%84%B1%EA%B3%B5.png)

~~이상하다~~