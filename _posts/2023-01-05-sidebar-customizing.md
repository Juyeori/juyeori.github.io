---
title: github 블로그 커스터마이징
layout: post
description: github page, blog, 커스터마이징
tags: github, github-page, 커스터마이징

categories: [Blog]
---

# sidebar 커스터마이징
chirpy 테마에 한정하여, sidebar 커스터마이징 방법을 소개하겠습니다!

### 1. sidebar 이미지 삽입
1. _sass/addon/commons.scss 파일에 들어가서 `#sidebar`를 찾는다.
1. `background: `를 아래와 같이 수정한다.
> 저는 영롱한걸 좋아해서 우주로 했습니다!

```scss
#sidebar {
  //...중략

  //background: var(--sidebar-bg);
  background-image: url('/assets/img/cosmos.jpg');
  background-size: cover;
  background-repeat: no-repeat;

  //...중략
}
```

> 배경에 이미지 삽입이 아니라 색깔만 바꾸고 싶다면 background: rgba(*,*,*,*) 이나 #ffffff 등, 원하는 색깔의 css 코드를 넣으면 됩니다.

### 2. sidebar title, subtitle 글자색 바꾸기
2. _sass/addon/commons.scss 파일에 들어가서 `.site-title`과 `.site-subtitle` 을 찾는다.
2. `color: `를 원하는 색상 코드로 바꾼다.
>저 같은 경우, 우주 배경이 어두워서 `#ffffff`(흰색)으로 하였습니다.

### 3. sidebar 메뉴 글자색 바꾸기
3. _sass/addon/module.scss 파일에 들어가서 `%sidebar-links` 를 찾는다.
3. `color: `를 원하는 색상 코드로 바꾼다.
>title, subtitle이 흰색이기도 하고, hover 이벤트로 흰색을 주기 위해 저는 흰색에 가까운 회색으로 하였습니다.
```scss
%sidebar-links {
    color: rgba(170, 170, 170, 0.9);
    //중략...
}
```

### 4. sidebar 메뉴 hover 및 옆에 작은 커서 바 색 바꾸기
4. _sass/colors/light-typography.scss 와 _sass/colors/dark-typography.scss 파일에 들어가서 `sidebar-active-color`를 찾는다.
4. `--sidebar-active-color:` (마우스 올렸을 때 색깔)와 `--nav-cursor-color:`(오른쪽 커서 색)를 색상 코드로 바꾼다.
> 저는 흰색이므로 `#ffffff` 했습니다.
