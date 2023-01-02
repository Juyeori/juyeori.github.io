---
title: React-Native 개발환경 설정
layout: post
description: Android Studio 설치 
tags: React-Native, Android-Studio, 앱개발, Android-Studio 설치

categories: [React, React-Native]
---

## 윈도우에서 React-Native 개발 환경 설정
저는 윈도우 사용자이므로, 윈도우 개발 환경에서 React-Native를 사용하기 위해 해야하는 설정들에 대해서 포스팅해보려고 합니다.
<br/>
<br/>
윈도우의 경우, 앱 개발에 필요한 소프트웨어를 각 웹 사이트에서 내려받은 다음 설치해야 하지만, 이러한 과정은 번거롭죠..그런데 Scoop이라는 설치 프로그램을 사용해서 개발을 하면 scoop으로 설치한 프로그램들의 업데이트를 scoop update * 명령으로 일괄적으로 앱 개발에 필요한 업데이트를 할 수 있습니다!
<br/>
그리하여...
1. Scoop 설치
1. node.js 설치
1. 자바 8 jdk 설치
1. 비주얼 스튜디오 코드 설치
1. 안드로이드 스튜디오 설치

<br/>
들을 설치해주면 앱 개발에 필요한 프로그램의 기본적인 설치는 다 끝나는겁니다.
<br/>
저같은 경우, node.js와 비주얼 스튜디오 코드는 이미 설치 되어있기 때문에, scoop과 자바 8 jdk, 안드로이드 스튜디오만 설치하였습니당

### 1. Scoop 설치
Scoop 설치는 관리자 모드로 실행한 powershell에서 진행합니다.

먼저
```ps
Set-ExecutionPolicy RemoteSigned -scope CurrentUser
```
의 명령어를 실행하면 질문이 나오는데, A를 입력해주면 됩니다.
<br/>
<br/>
그 후, 'SCOOP'이라는 이름의 파워셸 환경 변수를 다음 명령어처럼 설정해줍니다. 
이 명령어는 Scoop으로 설치한 모든 프로그램은 C:\Scoop 디렉터리에 위치시키기 위한 명령어입니다.
```ps
$env:SCOOP='C:/Scoop'
```

### 3. 자바 8 jdk 설치
굳이 자바 8 jdk를 설치하는 이유는, 안드로이드폰의 운영체제가 자바 버전 8 이기 때문입니다.

```ps
scoop install bucket add java
scoop install temurin8-jdk
```

### 5. 안드로이드 스튜디오 설치
리액트 네이티브로 안드로이드 앱을 만들려면, 안드로이드 스튜디오로 빌드해야하기 때문에 안드로이드 스튜디오도 설치해줍니다!
```ps
scoop install android-studio android-sdk
```
<br/>
<br/>

이렇게 설치하면 설치해야할 것 들은 모두 끝이 난겁니다!


