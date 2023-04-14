---
title: AxiosError Network Error, 리액트 네이티브 에러, 로컬 서버 연동 안됨
layout: post
description: 로컬 서버, axios, 리액트 네이티브 에러
tags: React-Native, Android-Studio, 앱개발, axois, 로컬 서버

categories: [React, React-Native]
---

## 아래와 같은 에러 처리 방법이다!

![axios오류](/assets/img/axios_2.png)
<br/>

![axios오류](/assets/img/axios_1.png)

<br/>
이 오류가 나오기 전에 확인할 것은, 자신이 정말 코드를 잘 짰는가!이다.<br/>
___코드를 정말 잘 짰는데도, 문제가 없는데도, 이러한 axios에러가 나는 것은 안드로이드 시뮬레이터가 pc에서 호스팅하는 로컬 서버에 접근할 수 없기 때문이다.___ <br/>
이걸 확인하는 방법은 안드로이드 시뮬레이터로 크롬에 들어가서 지금 호스팅하고 있는 로컬 서버 주소(localhost)를 직접 접속해보면 된다. 안될 것이다. <br/>
~~될 수도 있나?~~
<br/>

## 해결 방안

1. cmd창을 열어서 `ipconfig` 를 쳐준다.(경로는 상관없다)<br/>
   ![ipconfig](/assets/img/ipconfig.png)
   <br/>이런 결과가 나올텐데, 여기서 ipv4 주소를 react-native에서 작성한 아래와 같은 axios 코드 `localhost` 대신에 넣으면 된다.

<br/>

```javascript
//ipconfig 값 넣기
axios
  .post("http://localhost:3001/User", data)
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.error(error);
  });
```
