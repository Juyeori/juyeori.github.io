---
title: github 페이지 빌드 오류
layout: post
description: github error, ruby 버전 오류, tainted?
tags: github, github-page, ruby, 버전 오류, tainted?

categories: [Blog]
---

# github 페이지 빌드 오류

<br/>
글을 엇그제까지 무리없이 포스팅했는데, 갑작스럽게 깃허브 페이지 빌드 오류가 나버렸습니다...! <br/>
그래서 이리저리 구글링하면서 찾아보는데 원하는 결과를 찾기가 쉽지 않았습니다..

![ruby-version-error](/assets/img/ruby-version-error.png)
오류 요약 : 'Liquid Exception: undefined method `tainted?' for'

<https://github.com/jekyll/jekyll/issues/9231>
이 글 보면서 일단 깃허브와 로컬 루비 사이에서의 버전 오류라는 것을 알았습니다!!<br/>
그 후, <https://github.com/cotes2020/jekyll-theme-chirpy/issues/812#issuecomment-1365208215>에서 chirpy 테마 사용자들에게 최근에 일어나는 일임을 확인!
<br/>

### **_결론 : 루비 버전을 업데이트하는 과정에서 생긴 오류!! 즉, 우리의 잘못이 아니다!_**

# 해결

저는 루비 버전이 원래 3이였는데 이 오류를 해결해가는 과정에서 3.1.3을 깔았습니다...!<br/>
그래서 루비 버전이 3.1.\*이면 코드 한줄만 바꿔주면 됩니다!<br/>
~~다른 버전은 안해봤지만, 비슷하게 하면 되지 않을까요?~~ 근데 저랑 같은 오류라면 그냥 3.1.3깔고 저랑 똑같이 코드 한줄 바꿔보세요!!

1. /github/workflows/pages-deploy.yml 파일로 들어갑니다.
1. 스크롤해서 아래 사진과 같은 곳을 찾습니다.
   ![error-solve](/assets/img/ruby-version-error0.png)
1. 위 사진의 코드에서 버전을 아래와 같이 3.1로 바꿔줍니다!
   ![error-solve1](/assets/img/ruby-version-error1.png)
1. 성공<br/>
   ![success](/assets/img/ruby-version-success.png)
